# Importar dados

### **Importação Arquivos - teoria**

- Necessidade
    - Sistemas precisam se comunicar e isso pode ocorrer de diversas formas, como por exemplo: APIs Rest, Mensageria e até mesmo de troca de arquivo
- Formatos
    - O formato mais utilizado na atualidade é o Json - **J**ava **S**cript **O**bject **N**otation
    - Mas temos outros como: XML, Positional, Tab Delimited e CSV
- **CSV →** Comma-separated Values
    - Os dados são separados por vírgula
    - Podem ou não conter aspas para ajudar na identificação do formato contido em cada coluna
    - Podem ou não possuir cabeçalho
    - Podem utilizar outro tipo de delimitador

### csvStreamReader

```csharp
var path = Path.Combine(Environment.CurrentDirectory,
                         "Entrada", "usuarios-exportacao.csv");

if(File.Exists(path))
{
    using var sr = new StreamReader(path);

    var cabecalho = sr.ReadLine()?.Split(','); // paga os cabeçalhos separados por virguala e adiciona no array cabecalho

    while (true)
    {
        var registro = sr.ReadLine()?.Split(','); // vai pegando os registros
        if(registro == null)
            break;

        for (int i = 0; i < registro.Length; i++) // navega nos campos do registro
        {
            System.Console.WriteLine($"{cabecalho?[i]}: {registro[i]}"); // imprime o campo do cabeçalho e o campo do registro correspondente
        }

        System.Console.WriteLine("=================================");
    }
}
else
{
    System.Console.WriteLine($"O arquivo {path} não existe");
}

System.Console.WriteLine("\nPressione uma tecla para finalizar...");
Console.ReadKey();
```

### csvStreamWriter

```csharp
CriarCsv();

System.Console.WriteLine("\nPressione uma tecla para finalizar...");
Console.ReadKey();

static void CriarCsv()
{
    var path = Path.Combine(Environment.CurrentDirectory,
                         "Saida");

    var pessoas = new List<Pessoa>()
    {
        new Pessoa()
        {
            Nome = "Marcos",
            Email = "m@gmail.com",
            Telefone = 111111
        },
        new Pessoa()
        {
            Nome = "Antonio",
            Email = "a@gmail.com",
            Telefone = 222222
        },
        new Pessoa()
        {
            Nome = "José",
            Email = "j@gmail.com",
            Telefone = 333333
        }
    };

    var di = new DirectoryInfo(path);

    if (!di.Exists)
    {
        di.Create();
        path = Path.Combine(path, "usuarios.csv");
    }

    using var sw = new StreamWriter(path);

    sw.WriteLine("nome,email,telefone");

    foreach (var pessoa in pessoas)
    {
        var linha = $"{pessoa.Nome},{pessoa.Email},{pessoa.Telefone}";
        sw.WriteLine(linha);
    }
}
```

### csvHelperReader - dynamic

```csharp
using System.Globalization;
using CsvHelper.Configuration;
using CsvHelper;

var path = Path.Combine(Environment.CurrentDirectory,
                        "Entrada", "Produtos.csv");

var fi = new FileInfo(path);

if(!fi.Exists)
    throw new FileNotFoundException($"O arquivo {path} não existe!");

using var sr = new StreamReader(fi.FullName);
var csvConfig = new CsvConfiguration(CultureInfo.InvariantCulture);
using var csvReader = new CsvReader(sr, csvConfig);

var registros = csvReader.GetRecords<dynamic>();

foreach (var registro in registros)
{
    System.Console.WriteLine($"nome: {registro.Produto}");
    System.Console.WriteLine($"marca: {registro.Marca}");
    System.Console.WriteLine($"preço: {registro.Preco}");
    System.Console.WriteLine("===============================");
}
```

### csvReader - classe

```csharp
using System.Globalization;
using CsvHelper.Configuration;
using CsvHelper;

LerCsvComClasse();

System.Console.WriteLine("Pressione qualquer tecla para finalizar");
Console.ReadKey();

static void LerCsvComClasse()
{
    var path = Path.Combine(Environment.CurrentDirectory,
                        "Entrada", "usuarios-exportacao.csv");

    var fi = new FileInfo(path);

    if(!fi.Exists)
        throw new FileNotFoundException($"O arquivo {path} não existe!");

    using var sr = new StreamReader(fi.FullName);
    var csvConfig = new CsvConfiguration(CultureInfo.InvariantCulture);
    using var csvReader = new CsvReader(sr, csvConfig);

    var registros = csvReader.GetRecords<Usuario>();

    foreach (var registro in registros)
    {
        System.Console.WriteLine($"nome: {registro.Nome}");
        System.Console.WriteLine($"email: {registro.Email}");
        System.Console.WriteLine($"telefone: {registro.Telefone}");
        System.Console.WriteLine("===============================");
    }
}
```

### csvReader - delimiter

```csharp
using System.Globalization;
using CsvHelper.Configuration;
using CsvHelper;

LerCsvComOutroDelimitador();

System.Console.WriteLine("Pressione qualquer tecla para finalizar");
Console.ReadKey();

static void LerCsvComOutroDelimitador()
{
    var path = Path.Combine(Environment.CurrentDirectory,
                        "Entrada", "Livros-preco-com-virgula.csv");

    var fi = new FileInfo(path);

    if(!fi.Exists)
        throw new FileNotFoundException($"O arquivo {path} não existe!");

    using var sr = new StreamReader(fi.FullName);
    var csvConfig = new CsvConfiguration(CultureInfo.InvariantCulture)
    {
        Delimiter = ";"
    };
    using var csvReader = new CsvReader(sr, csvConfig);

    var registros = csvReader.GetRecords<Livro>();

    foreach (var registro in registros)
    {
        System.Console.WriteLine($"Titulo: {registro.Titulo}");
        System.Console.WriteLine($"Preco: {registro.Preco}");
        System.Console.WriteLine($"Autor: {registro.Autor}");
        System.Console.WriteLine("===============================");
    }
}
```

### csvHelper header - configuration

- Classe Livro:

```csharp
using CsvHelper.Configuration.Attributes;

public class Livro
{
    [Name("titulo")]
    public string Titulo { get; set; }
    [Name("autor")]
    public string Autor { get; set; }
    [Name("preço")]
    [CultureInfo("pt-BR")]
    public string Preco { get; set; }
    [Name("lançamento")]
    [Format("dd/MM/yyyy")]
    public DateOnly Lancamento { get; set; }
}
```

- Programa:

```csharp
using System.Globalization;
using CsvHelper.Configuration;
using CsvHelper;

LerCsvComOutroDelimitador();

System.Console.WriteLine("Pressione qualquer tecla para finalizar");
Console.ReadKey();

static void LerCsvComOutroDelimitador()
{
    var path = Path.Combine(Environment.CurrentDirectory,
                        "Entrada", "Livros-preco-com-virgula.csv");

    var fi = new FileInfo(path);

    if(!fi.Exists)
        throw new FileNotFoundException($"O arquivo {path} não existe!");

    using var sr = new StreamReader(fi.FullName);
    var csvConfig = new CsvConfiguration(CultureInfo.InvariantCulture)
    {
        Delimiter = ";"
    };
    using var csvReader = new CsvReader(sr, csvConfig);

    var registros = csvReader.GetRecords<Livro>().ToList();

    foreach (var registro in registros)
    {
        System.Console.WriteLine($"Titulo: {registro.Titulo}");
        System.Console.WriteLine($"Preco: {registro.Preco}");
        System.Console.WriteLine($"Autor: {registro.Autor}");
        System.Console.WriteLine($"Lancamento: {registro.Lancamento}");
        System.Console.WriteLine("===============================");
    }
}
```

### csvHeader - sem cabeçalho

É recomendado fazer da próxima maneira - **csvHelperMapping**

- Classe Livro:

```csharp
using CsvHelper.Configuration.Attributes;

public class Livro
{
    [Index(0)]
    public string Titulo { get; set; }
    [Index(2)]
    public string Autor { get; set; }
    [Index(1)]
    [CultureInfo("pt-BR")]
    public string Preco { get; set; }
    [Index(3)]
    [Format("dd/MM/yyyy")]
    public DateOnly Lancamento { get; set; }
}
```

- Programa:

```csharp
using System.Globalization;
using CsvHelper.Configuration;
using CsvHelper;

LerCsvComOutroDelimitador();

System.Console.WriteLine("Pressione qualquer tecla para finalizar");
Console.ReadKey();

static void LerCsvComOutroDelimitador()
{
    var path = Path.Combine(Environment.CurrentDirectory,
                        "Entrada", "Livros-preco-com-virgula.csv");

    var fi = new FileInfo(path);

    if(!fi.Exists)
        throw new FileNotFoundException($"O arquivo {path} não existe!");

    using var sr = new StreamReader(fi.FullName);
    var csvConfig = new CsvConfiguration(CultureInfo.InvariantCulture)
    {
        Delimiter = ";"
    };
    using var csvReader = new CsvReader(sr, csvConfig);

    var registros = csvReader.GetRecords<Livro>().ToList();

    foreach (var registro in registros)
    {
        System.Console.WriteLine($"Titulo: {registro.Titulo}");
        System.Console.WriteLine($"Preco: {registro.Preco}");
        System.Console.WriteLine($"Autor: {registro.Autor}");
        System.Console.WriteLine($"Lancamento: {registro.Lancamento}");
        System.Console.WriteLine("===============================");
    }
}
```

### csvHelperMapping

- Classe LivroMap

```csharp
using System.Globalization;
using CsvHelper.Configuration;
public class LivroMap : ClassMap<Livro>
{
    public LivroMap()
    {
        Map(x => x.Titulo).Name("titulo");
        Map(x => x.Preco).Name("preço");
        Map(x => x.Autor)
            .Name("autor")
            .TypeConverterOption
            .CultureInfo(CultureInfo.GetCultureInfo("pt-br"));
        Map(x => x.Lancamento)
        .Name("lançamento")
        .TypeConverterOption
        .Format(new [] {"dd/MM/yyyy"});
    }
}
```

- Classe Livro:

```csharp
using CsvHelper.Configuration.Attributes;

public class Livro
{
    public string Titulo { get; set; }
    public string Autor { get; set; }
    public string Preco { get; set; }
    public DateOnly Lancamento { get; set; }
}
```

- Programa:

```csharp
using System.Globalization;
using CsvHelper.Configuration;
using CsvHelper;

LerCsvComOutroDelimitador();

System.Console.WriteLine("Pressione qualquer tecla para finalizar");
Console.ReadKey();

static void LerCsvComOutroDelimitador()
{
    var path = Path.Combine(Environment.CurrentDirectory,
                        "Entrada", "Livros-preco-com-virgula.csv");

    var fi = new FileInfo(path);

    if(!fi.Exists)
        throw new FileNotFoundException($"O arquivo {path} não existe!");

    using var sr = new StreamReader(fi.FullName);
    var csvConfig = new CsvConfiguration(CultureInfo.InvariantCulture)
    {
        Delimiter = ";"
    };
    using var csvReader = new CsvReader(sr, csvConfig);

    csvReader.Context.RegisterClassMap<LivroMap>();

    var registros = csvReader.GetRecords<Livro>().ToList();

    foreach (var registro in registros)
    {
        System.Console.WriteLine($"Titulo: {registro.Titulo}");
        System.Console.WriteLine($"Preco: {registro.Preco}");
        System.Console.WriteLine($"Autor: {registro.Autor}");
        System.Console.WriteLine($"Lancamento: {registro.Lancamento}");
        System.Console.WriteLine("===============================");
    }
}
```

### csvWriter

```csharp
using System.Globalization;
using CsvHelper.Configuration;
using CsvHelper;

EscreverCsv();

System.Console.WriteLine("Pressione qualquer tecla para finalizar");
Console.ReadKey();

static void EscreverCsv()
{
    var path = Path.Combine(Environment.CurrentDirectory,
                        "Saida");

    var di = new DirectoryInfo(path);

    if (!di.Exists)
        di.Create();

    path = Path.Combine(path, "usuarios.csv");

    var pessoas = new List<Pessoa>()
    {
        new Pessoa()
        {
            Nome = "José",
            Email = "j@gmail.com",
            Telefone = 111111
        },
        new Pessoa()
        {
            Nome = "Antonio",
            Email = "a@gmail.com",
            Telefone = 212121
        },
        new Pessoa()
        {
            Nome = "Célia",
            Email = "c@gmail.com",
            Telefone = 332211
        }
    };

    using var sw = new StreamWriter(path);
    var csvConfig = new CsvConfiguration(CultureInfo.InvariantCulture)
    {
        Delimiter = "|"
    };
    using var csvWriter = new CsvWriter(sw, csvConfig);
    csvWriter.WriteRecords(pessoas);
}
```