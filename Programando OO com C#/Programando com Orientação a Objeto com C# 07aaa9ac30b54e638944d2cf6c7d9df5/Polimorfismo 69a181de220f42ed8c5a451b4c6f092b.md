# Polimorfismo

### Introdução polimorfismo

- O polimorfismo vem do grego e significa “muitas formas”
- Com polimorfismo, podemos sobrescrever métodos das classes filhas para que se comportem de maneira diferente e ter sua própria implementação

![Untitled](Polimorfismo%2069a181de220f42ed8c5a451b4c6f092b/Untitled.png)

- Polimorfismo em tempo de compilação (Overload/Early Binding)
    
    ![Untitled](Polimorfismo%2069a181de220f42ed8c5a451b4c6f092b/Untitled%201.png)
    
- Polimorfismo em tempo de execução (Override/Late Binding)
    
    ![Untitled](Polimorfismo%2069a181de220f42ed8c5a451b4c6f092b/Untitled%202.png)
    

### Polimorfismo em tempo de execução

- Classe Pessoa

```csharp
namespace ExemploPOO.Models
{
    public class Pessoa
    {
        public string Nome { get; set; }
        public int Idade { get; set; }

        public virtual void Apresentar()
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

        public override void Apresentar()
        {
            System.Console.WriteLine($"Olá, meu nome é {Nome}, sou um aluno e minha nota é {Nota}");
        }
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

        public override void Apresentar()
        {
            System.Console.WriteLine($"Olá, meu nome é {Nome}, sou um professor e meu salário é {Salario}");
        }
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

### Polimorfismo em tempo de compilação

- Classe Calculadora

```csharp
namespace ExemploPOO.Models
{
    public class Calculadora
    {
        public int Somar(int num1, int num2)
        {
            return num1 + num2;
        }
        public int Somar(int num1, int num2, int num3)
        {
            return num1 + num2 + num3;
        }
    }
}
```

- Programa

```csharp
using ExemploPOO.Models;

Calculadora calc= new Calculadora();

System.Console.WriteLine("Resultado da primeira soma: " + calc.Somar(20, 30));

System.Console.WriteLine("Resultado da segunda soma: " + calc.Somar(20, 30, 50));
```