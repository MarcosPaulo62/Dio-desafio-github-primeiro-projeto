# Classes abstratas

### Introdução classes abstratas

- Uma classe abstrata tem como objetivo ser exclusivamente um modelo para ser herdado, portanto não pode ser instanciada
- Você pode implementar métodos ou deixa-los a cargo de quem herdar

![Untitled](Classes%20abstratas%2013f41f568dcd46e0a363d4ad8713e4fc/Untitled.png)

### Classes abstratas na prática

- Classe Conta

```csharp
namespace ExemploPOO.Models
{
    public abstract class Conta
    {
        protected double saldo;
        public abstract void Creditar(double valor); // classe filha é obrigada a sobrescrever

        public void ExibirSaldo()
        {
            System.Console.WriteLine("Seu saldo é: " + saldo);
        }
    }
}
```

- Classe Corrente

```csharp
namespace ExemploPOO.Models
{
    public class Corrente : Conta
    {
        public override void Creditar(double valor)
        {
            base.saldo += valor;
        }
    }
}
```

- Programa

```csharp
using ExemploPOO.Models;

Corrente c = new Corrente();
c.Creditar(100);
c.Creditar(100);

c.ExibirSaldo();
```

### Introdução a métodos selados

- Uma classe selada tem como objetivo de impedir que outras classes façam um herança dela, ou seja, nenhuma classe pode ser sua derivada
- Também existem métodos e propriedades seladas

![Untitled](Classes%20abstratas%2013f41f568dcd46e0a363d4ad8713e4fc/Untitled%201.png)

![Untitled](Classes%20abstratas%2013f41f568dcd46e0a363d4ad8713e4fc/Untitled%202.png)

### Métodos selados na prática

- Classe Professor selada

```csharp
namespace ExemploPOO.Models
{
    public sealed class Professor : Pessoa // sealed - outra classe não pode herdar Professor
    {
        public double Salario { get; set; }

        public override void Apresentar()
        {
            System.Console.WriteLine($"Olá, meu nome é {Nome}, sou um professor e meu salário é {Salario}");
        }
    }
}
```

- Classe Professor com método Apresentar selado

```csharp
namespace ExemploPOO.Models
{
    public class Professor : Pessoa
    {
        public double Salario { get; set; }

        public sealed override void Apresentar() // sealed - outra classe não pode herdar esse método
        {
            System.Console.WriteLine($"Olá, meu nome é {Nome}, sou um professor e meu salário é {Salario}");
        }
    }
}
```

### Introdução classe object

- A classe System.Object é a mãe de todas as classes na hierarquia do .NET
- Todas as classes derivam, direta ou indiretamente da classe Object, e ela tem como objetivo prover serviços de baixo nível para suas classes filhas

![Untitled](Classes%20abstratas%2013f41f568dcd46e0a363d4ad8713e4fc/Untitled%203.png)

### Classe object na prática

- Classe Computador (criada por mim)

```csharp
namespace ExemploPOO.Models
{
    public class Computador // : System.Object <- isso é implicito, as classes já herdam de Object automaticamente
    {
        public override string ToString() // sobrescrevendo classe herdada
        {
            return "Sou uma classe computador";
        }
    }
}
```

- Programa

```csharp
using ExemploPOO.Models;

Computador comp = new Computador();
System.Console.WriteLine(comp.ToString());
```