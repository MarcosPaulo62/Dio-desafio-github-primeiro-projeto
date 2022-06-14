# System.IO

### Introdução e Teoria System IO

- Objetivo do curso
    - Aprender como manipular arquivos e pastas
    - Como navegar pela estrutura de diretórios do SO
    - Modificar arquivos existentes
    - Criar novos arquivos em memória e salvá-los
    - Diferentes técnicas de importação de dados
    - Criar, Validar e consumir arquivos CSV
- **System.IO**
    - Namespace que agrega um conjunto de classes, estruturas, enumeradores e delegates, relativos a operações de Entrada e Saída de dados (Input/Output)
- Principais classes:
    - **File e FileInfo →** fornece suporte para criar, copiar, apagar, mover, renomear e abrir arquivos de forma individual
    - **Directory e DirectoryInfo →** fornece suporte para criar, mover e percorrer diretórios e subdiretórios
    - **FileSystemWatcher** → monitora mudança no sistema de arquivos, através de disparo de eventos quando um arquivo ou diretório muda.
    - **FileStream MemoryStream, StreamReader**

### Demo criar Arquivo

```csharp
var path = Path.Combine(Environment.CurrentDirectory, "teste.txt"); // Cria teste.txt no diretório atual

// File.Create(path); // Cria o arquivo

using var sw = File.CreateText(path); // Cria ou abre o arquivo para escrita
// using faz com que quando o programa encerre as linhas escritas sejam descarregadas no arquivo

sw.WriteLine("Linha 1 do arquivo");
sw.WriteLine("Linha 2 do arquivo");
sw.WriteLine("Linha 3 do arquivo");
sw.WriteLine("Linha 4 do arquivo");
sw.WriteLine("Linha 5 do arquivo");

// sw.Flush(); // Empurra as linhas escritas para o arquivo
```

### Tratamento de Erros

```csharp
using static System.Console;

WriteLine("Digite o nome do arquivo:");

var nome = ReadLine();

nome = LimparNome(nome);

var path = Path.Combine(Environment.CurrentDirectory, $"{nome}.txt");

CriarArquivo(path);

WriteLine("Digite Enter para finalizar...");
ReadKey();

static string LimparNome(string nome)
{
    foreach (var @char in Path.GetInvalidFileNameChars()) // rodando array de caracteres inválidos
    {
        nome = nome.Replace(@char, '-'); // substituindo caracteres inválidos por "-"
    }
    return nome;
}

static void CriarArquivo(string path)
{
    try
    {
        using var sw = File.CreateText(path);

        sw.WriteLine("Linha 1 do arquivo");
        sw.WriteLine("Linha 2 do arquivo");
        sw.WriteLine("Linha 3 do arquivo");
        sw.WriteLine("Linha 4 do arquivo");
        sw.WriteLine("Linha 5 do arquivo");
    }
    catch (System.Exception)
    {
       WriteLine("Nome de arquivo inválido!");
    }
    
}
```

### Diretórios

```csharp
var path = Path.Combine(Environment.CurrentDirectory, "globo"); // faz o caminho até o diretórioAtual/globo

var dirGlobo = Directory.CreateDirectory(path); // Cria um diretório globo no diretório atual

var dirAmSul = dirGlobo.CreateSubdirectory("América do Sul"); // Cria um subdiretório América do sul dentro do diretório globo
var dirAsia = dirGlobo.CreateSubdirectory("Ásia");
var dirAfrica = dirGlobo.CreateSubdirectory("África");

dirAmSul.CreateSubdirectory("Argentina");
dirAmSul.CreateSubdirectory("Brasil");
dirAmSul.CreateSubdirectory("Paraguai");

dirAsia.CreateSubdirectory("Japão");
dirAsia.CreateSubdirectory("China");

dirAfrica.CreateSubdirectory("Angola");
dirAfrica.CreateSubdirectory("África do Sul");
```

### File Move Copy

```csharp
using static System.Console;

CriarDiretoriosGlobo();
CriarArquivo();

var origem = Path.Combine(Environment.CurrentDirectory, "brasil.txt");
var destino = Path.Combine(Environment.CurrentDirectory,
                             "globo", "América do Sul",
                             "Brasil", "brasil.txt");

//MoverArquivo(origem, destino);

CopiarArquivo(origem, destino);

static void CopiarArquivo(string pathOrigem, string pathDestino)
{
    if(!File.Exists(pathOrigem))
    {
        WriteLine("Arquivo de origem não existe");
        return;
    }

    if(File.Exists(pathDestino))
    {
        WriteLine("Arquivo já existe na pasta de destino");
        return;
    }

    File.Copy(pathOrigem, pathDestino);
}

static void MoverArquivo(string pathOrigem, string pathDestino)
{
    if(!File.Exists(pathOrigem))
    {
        WriteLine("Arquivo de origem não existe");
        return;
    }

    if(File.Exists(pathDestino))
    {
        WriteLine("Arquivo já existe na pasta de destino");
        return;
    }

    File.Move(pathOrigem, pathDestino);
}
```

### DirectoryInfo

```csharp
var path = @"C:\workspace\CSharp-estudos\Trabalhando com Arquivos e Streams em C#\Directory_And_DirectoryInfo\globo";

LerDiretorios(path);

System.Console.WriteLine("Digite [enter] para finalizar");
Console.ReadKey();

static void LerDiretorios(string path)
{
    if(Directory.Exists(path))
    {
        var diretorios = Directory.GetDirectories(path, "*", SearchOption.AllDirectories);
        
        // vai retornar um array com todos diretórios e subdiretórios no caminho->path indicado
    
        foreach (var dir in diretorios)
        {
            var dirInfo = new DirectoryInfo(dir);
            System.Console.WriteLine($"[Nome]: {dirInfo.Name}"); // retorna nome do diretório
            System.Console.WriteLine($"[Raiz]: {dirInfo.Root}"); // retorna raiz do diretório
            if (dirInfo.Parent != null)
                System.Console.WriteLine($"[Pai]: {dirInfo.Parent.Name}"); // retorna nome do pai do diretório
            
            System.Console.WriteLine("=====================================");
        }
    }    
    else
        System.Console.WriteLine($"{path} não existe");
}
```

### FileInfo

```csharp
var path = @"C:\workspace\CSharp-estudos\Trabalhando com Arquivos e Streams em C#\Directory_And_DirectoryInfo\globo";

// LerDiretorios(path);

LerArquivos(path);

static void LerArquivos(string path)
{
    var arquivos = Directory.GetFiles(path, "*", SearchOption.AllDirectories);
    // vai retornar um array com todos arquivos no caminho->path indicado

    foreach (var arquivo in arquivos)
    {
        var fileInfo = new FileInfo(arquivo);

        System.Console.WriteLine($"[Nome]: {fileInfo.Name}");
        System.Console.WriteLine($"[Tamanho]: {fileInfo.Length}");
        System.Console.WriteLine($"[Último acesso]: {fileInfo.LastAccessTime}");
        System.Console.WriteLine($"[Pasta]: {fileInfo.DirectoryName}");

        System.Console.WriteLine("===================================");
    }
}
```