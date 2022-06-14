# Manipulando arquivos

### Introdução arquivos

- O C# nos apresenta algumas classes estáticas que facilitam o trabalho com arquivos, dentre elas:
    - File
    - Directory
    - Path

### Listar Diretórios

```csharp
public void ListarDiretorios(string caminho)
{
    var retornoCaminho = Directory.GetDirectories(caminho, "*", SearchOption.AllDirectories);// retorna array de diretórios

    foreach (var retorno in retornoCaminho)
    {
        System.Console.WriteLine(retorno);
    }
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

var caminho = "C:\\TrabalhandoComArquivos";

FileHelper helper = new FileHelper();
helper.ListarDiretorios(caminho);
```

### Listar arquivos

```csharp
public void ListarArquivosDiretorios(string caminho)
{
    //var retornoArquivos = Directory.GetFiles(caminho, "*.txt", SearchOption.AllDirectories);
                                                // retorna array de arquivos terminados com .txt
    //var retornoArquivos = Directory.GetFiles(caminho, "*2*", SearchOption.AllDirectories);
                                                // retorna array de arquivos com um 2 no meio
    var retornoArquivos = Directory.GetFiles(caminho, "*", SearchOption.AllDirectories);// retorna array de arquivos

    foreach (var retorno in retornoArquivos)
    {
        System.Console.WriteLine(retorno);
    }
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

var caminho = "C:\\TrabalhandoComArquivos";

FileHelper helper = new FileHelper();
helper.ListarArquivosDiretorios(caminho);
```

### Criar diretório

```csharp
public void CriarDiretorio(string caminho)
{
    var retorno = Directory.CreateDirectory(caminho);
    System.Console.WriteLine(retorno.FullName);
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoPathCombine = Path.Combine(caminho, "Pasta Teste 3", "SubPasta Teste 3");

System.Console.WriteLine("Criando diretório: " + caminhoPathCombine);
helper.CriarDiretorio(caminhoPathCombine);
```

### Apagar diretório

```csharp
public void ApagarDiretorio(string caminho, bool apagarArquivos)
{
    Directory.Delete(caminho, apagarArquivos);
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoPathCombine = Path.Combine(caminho, "Pasta Teste 1");

helper.ApagarDiretorio(caminhoPathCombine, true);
```

### Criar arquivo de texto

```csharp
public void CriarArquivoTexto(string caminho, string conteudo)
{
    if(!File.Exists(caminho))
        File.WriteAllText(caminho, conteudo);
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoPathCombine = Path.Combine(caminho, "Pasta Teste 1");
var caminhoArquivo = Path.Combine(caminho, "arquivo-teste.txt");

helper.CriarArquivoTexto(caminhoArquivo, "Olá! Esse é um teste de escrita de arquivo.");
```

### Criar arquivo texto com stream

```csharp
public void CriarArquivoTextoStream(string caminho, List<string> conteudo)
{
    using (var stream = File.CreateText(caminho)) // using - libera memória quando stream termina
    {
        foreach (var linha in conteudo)
        {
            stream.WriteLine(linha);
        }
    }
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoArquivo = Path.Combine(caminho, "arquivo-teste-stream.txt");
var listaString = new List<string> {"Linha 1", "Linha 2", "Linha 3"};

helper.CriarArquivoTextoStream(caminhoArquivo, listaString);
```

### Adicionar novas linhas em um arquivo

```csharp
public void AdicionarTextoStream(string caminho, List<string> conteudo)
{
    using (var stream = File.AppendText(caminho)) // using - libera memória quando stream termina
    {
        foreach (var linha in conteudo)
        {
            stream.WriteLine(linha);
        }
    }
}

public void AdicionarTexto(string caminho, string conteudo)
{
    File.AppendAllText(caminho, conteudo);
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoArquivo = Path.Combine(caminho, "arquivo-teste-stream.txt");
var listaString = new List<string> {"Linha 1", "Linha 2", "Linha 3"};
var listaStringCont = new List<string> {"Linha 4", "Linha 5", "Linha 6"};

helper.AdicionarTexto(caminhoArquivo, "Teste escrita");
helper.AdicionarTextoStream(caminhoArquivo, listaStringCont);
```

### Lendo arquivos

```csharp
public void LerArquivoStream(string caminho)
{
    string linha = string.Empty;

    using (var stream = File.OpenText(caminho))
    {
        while ((linha = stream.ReadLine()) != null)
        {
            System.Console.WriteLine(linha);
        }
    }
}

public void LerArquivo(string caminho)
{
    var conteudo = File.ReadAllLines(caminho);

    foreach (var linha in conteudo)
    {
        System.Console.WriteLine(linha);
    }
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoArquivo = Path.Combine(caminho, "arquivo-teste-stream.txt");

helper.LerArquivo(caminhoArquivo);
helper.LerArquivoStream(caminhoArquivo);
```

### Movendo arquivo

```csharp
public void MoverArquivo(string caminho, string novoCaminho)
{
    File.Move(caminho, novoCaminho);
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoArquivo = Path.Combine(caminho, "arquivo-teste-stream.txt");
var novoCaminhoArquivo = Path.Combine(caminho, "Pasta Teste 2", "arquivo-teste-stream.txt");

helper.MoverArquivo(caminhoArquivo, novoCaminhoArquivo);
```

### Copiando arquivo

```csharp
public void CopiarArquivo(string caminho, string novoCaminho, bool sobrescrever)
{
    File.Copy(caminho, novoCaminho, sobrescrever);
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoArquivoTeste = Path.Combine(caminho, "arquivo-teste.txt");
var caminhoArquivoTesteCopia = Path.Combine(caminho, "arquivo-teste-bkp.txt");

helper.CopiarArquivo(caminhoArquivoTeste, caminhoArquivoTesteCopia, false);
```

### Deletando arquivo

```csharp
public void DeletarArquivo(string caminho)
{
    File.Delete(caminho);
}
```

- Programa:

```csharp
using ExemploPOO.Helper;

FileHelper helper = new FileHelper();

var caminho = "C:\\TrabalhandoComArquivos";
var caminhoArquivoTesteCopia = Path.Combine(caminho, "arquivo-teste-bkp.txt");

helper.DeletarArquivo(caminhoArquivoTesteCopia);
```