# Construtores

### Introdução Construtores

- Um construtor é um método especial, que contém o mesmo nome do seu tipo classe, e tem o objetivo de definir valores padrão, limitar uma instância e facilitar a instanciação de um objeto
- Um construtor não possui retorno
- Um construtor padrão é sempre definido quando não declaramos nenhum para sua classe
- Uma classe pode ter mais de um construtor

![Untitled](Construtores%201a230835bca74f1dabcda717f142fb9d/Untitled.png)

### Construtor na prática

- Classe Pessoa:

```csharp
namespace ExemploConstrutores.Models
{
    public class Pessoa
    {
        private string nome;
        private string sobrenome;

        public Pessoa()
        {
            nome = string.Empty;
            sobrenome = string.Empty;
        }

        public Pessoa(string nome, string sobrenome)
        {
            this.nome = nome;
            this.sobrenome = sobrenome;
        }

        public void Apresentar()
        {
            System.Console.WriteLine($"Meu nome é {nome} {sobrenome}");
        }
    }
}
```

- Programa:

```csharp
using ExemploConstrutores.Models;

Pessoa p1 = new Pessoa("Marcos", "Paulo");
p1.Apresentar();
```

### Construtor padrão

- Classe Pessoa:

```csharp
namespace ExemploConstrutores.Models
{
    public class Pessoa
    {
        private string nome;
        private string sobrenome;

        // Se não for definido nenhum construtor o c# cria implicitamente um construtor vazio
        // Se for definido um construtor com parâmetros, quando for instanciar é obrigado a passa-los
        // A não ser que crie um construtor vazio

        public void Apresentar()
        {
            System.Console.WriteLine($"Meu nome é {nome} {sobrenome}");
        }
    }
}
```

### Constritor privado

- Classe Log:

```csharp
namespace ExemploConstrutores.Models
{
    public class Log
    {
        private static Log _log;
        public string PropriedadeLog { get; set; }
        private Log() // evita que a classe seja instanciada diretamente
        {
            
        }

        public static Log GetInstance()
        {
            if(_log == null) // se _log for null a classe Log é instanciada
            {
                _log = new Log();
            }
            return _log; // se não for null só é retornado
        }
    }
}
```

- Programa:

```csharp
using ExemploConstrutores.Models;

Log log = Log.GetInstance(); // Instancia a classe log
log.PropriedadeLog = "Teste instância"; // Passa string para PropriedadeLog

Log log2 = Log.GetInstance(); // Reutiliza instância da classe log criada
System.Console.WriteLine(log2.PropriedadeLog); // Imprime "Teste instância" contida na PropriedadeLog
```

### Chamando o construtor da herança

- Classe Pessoa:

```csharp
public class Pessoa
{
    private string nome;
    private string sobrenome;

    // public Pessoa()
    // {
    //     nome = string.Empty;
    //     sobrenome = string.Empty;
    // }

    public Pessoa(string nome, string sobrenome)
    {
        this.nome = nome;
        this.sobrenome = sobrenome;
    }

    public void Apresentar()
    {
        System.Console.WriteLine($"Meu nome é {nome} {sobrenome}");
    }
}
```

- Classe herdeira Aluno:

```csharp
public class Aluno : Pessoa
{
    public Aluno(string nome, string sobrenome, string disciplina) : base(nome, sobrenome)
    {
        
    }
}
```