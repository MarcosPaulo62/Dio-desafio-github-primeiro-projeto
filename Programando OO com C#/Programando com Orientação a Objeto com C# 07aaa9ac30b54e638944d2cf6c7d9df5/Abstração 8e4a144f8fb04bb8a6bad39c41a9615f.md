# Abstração

### Entendendo o que é abstração

- Abstrair um objeto do mundo real para um contexto específico, considerando apenas os atributos importantes
    
    ![Untitled](Abstrac%CC%A7a%CC%83o%208e4a144f8fb04bb8a6bad39c41a9615f/Untitled.png)
    

### Abstração na prática

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

- Programa

```csharp
using ExemploPOO.Models;

Pessoa p1 = new Pessoa();

p1.Nome = "Steve";
p1.Idade = 20;

p1.Apresentar();
```