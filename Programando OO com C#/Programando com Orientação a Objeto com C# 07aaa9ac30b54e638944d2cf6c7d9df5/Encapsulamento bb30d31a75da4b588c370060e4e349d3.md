# Encapsulamento

### Introdução encapsulamento

- O encapsulamento serve para proteger uma classe e definir limites para alteração de suas propriedades.
- Serve para ocultar seu comportamento e expor somente o necessário

![Untitled](Encapsulamento%20bb30d31a75da4b588c370060e4e349d3/Untitled.png)

![Untitled](Encapsulamento%20bb30d31a75da4b588c370060e4e349d3/Untitled%201.png)

### Encapsulamento na prática

- Classe Retangulo

```csharp
namespace ExemploPOO.Models
{
    public class Retangulo
    {
        private double comprimento;
        private double largura;
        private bool valido;

        public void DefinirMedidas(double comprimento, double largura)
        {
            if (comprimento > 0 && largura > 0)
            {
                this.comprimento = comprimento;
                this.largura = largura;
                valido = true;
            }
            else
            {
                System.Console.WriteLine("Valores inválidos!");
            }
        }

        public double ObterArea()
        {
            if (valido)
                return comprimento * largura;
            else
                System.Console.WriteLine("Preencha valores válidos!");
                return 0;
        }
    }
}
```

- Programa

```csharp
using ExemploPOO.Models;

// Valores válidos
Retangulo r = new Retangulo();
r.DefinirMedidas(30, 30);
System.Console.WriteLine($"Área: {r.ObterArea()}");

// Valores inválidos
Retangulo r2 = new Retangulo();
r2.DefinirMedidas(30, -30);
System.Console.WriteLine($"Área: {r2.ObterArea()}");
```