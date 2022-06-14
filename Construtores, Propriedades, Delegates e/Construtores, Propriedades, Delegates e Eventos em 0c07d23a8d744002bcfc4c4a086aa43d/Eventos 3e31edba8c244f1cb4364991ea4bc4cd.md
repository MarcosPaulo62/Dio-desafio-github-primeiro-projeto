# Eventos

### Introdução eventos

- Eventos é um mecanismo de comunicação entre objetos, onde existe um publisher, que realiza o evento e o subscriber, que se inscreve em um evento

![Untitled](Eventos%203e31edba8c244f1cb4364991ea4bc4cd/Untitled.png)

### Eventos na prática

- Classe Calculadora com evento:

```csharp
namespace ExemploConstrutores.Models
{
    public class Calculadora
    {
        // Delegate
        public delegate void DelegateCalculadora();

        // Evento
        public static event DelegateCalculadora EventoCalculadora; // Evento que outros objetos podem se inscrever

        public static void Somar(int x, int y)
        {
            if (EventoCalculadora != null) // verifica se tem inscritos no evento
            {
		            System.Console.WriteLine($"Adição: {x + y}");
		            EventoCalculadora(); // Executa o evento - métodos inscritos
            }
            else
            {
                System.Console.WriteLine("Nenhum inscrito");
            }
        }
        public static void Subtrair(int x, int y)
        {
            System.Console.WriteLine($"Subtração: {x - y}");
        }
    }
}
```

- Classe Matematica com método inscrito no evento:

```csharp
namespace ExemploConstrutores.Models
{
    public class Matematica
    {
        public int X { get; set; }
        public int Y { get; set; }

        public Matematica(int x, int y)
        {
            X = x;
            Y = y;

            Calculadora.EventoCalculadora += EventHandler; 
            // EventHandler passa a ser inscrito do EventoCalculadora
        }

        public void Somar()
        {
            Calculadora.Somar(X, Y);
        }

        public void EventHandler()
        {
            System.Console.WriteLine("Método executado");
        }
    }
}
```

- Programa:

```csharp
using ExemploConstrutores.Models;

Matematica a = new Matematica(10, 20);
a.Somar();
```

- Saída:

```csharp
Adição: 30
Método executado
```