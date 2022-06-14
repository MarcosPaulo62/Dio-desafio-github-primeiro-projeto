# Herança

### Introdução herança

- A herança nos permite reutilizar atributos, métodos e comportamentos de uma classe em outras classes
- Serve para agrupar objetos que são do mesmo tipo, porém com características diferentes

![Untitled](Heranc%CC%A7a%20c4c6844b10fa42afb61a1b4638d432cc/Untitled.png)

### Herança na prática

- Classe Pessoa

```csharp
namespace ExemploPOO.Models
{
    public class Pessoa
    {
        public string Nome { get; set; }
        public int Idade { get; set; }

        public void Apresentar()
        {
            System.Console.WriteLine($"Olá, meu nome é {Nome} e tenho {Idade} anos.");
        }
    }
}
```

- Classe Aluno

```csharp
namespace ExemploPOO.Models
{
    public class Aluno : Pessoa
    {
        public int Nota { get; set; }
    }
}
```

- Classe Professor

```csharp
namespace ExemploPOO.Models
{
    public class Professor : Pessoa
    {
        public double Salario { get; set; }
    }
}
```

- Programa

```csharp
using ExemploPOO.Models;

Aluno a1 = new Aluno();
a1.Nome = "Bruno";
a1.Idade = 15;
a1.Nota = 10;
a1.Apresentar();

Professor p1 = new Professor();
p1.Nome = "André";
p1.Idade = 45;
p1.Salario = 3000;
p1.Apresentar();
```