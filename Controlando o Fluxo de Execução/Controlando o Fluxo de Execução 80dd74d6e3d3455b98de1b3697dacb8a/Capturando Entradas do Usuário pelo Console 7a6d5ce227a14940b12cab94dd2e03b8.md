# Capturando Entradas do Usuário pelo Console

### Capturando Entradas do Usuário pelo Console

```csharp
using static System.Console;

int valor1;
int valor2;

WriteLine("Digite o primeiro valor");
valor1 = int.Parse(ReadLine());
WriteLine("O primeiro valor é: " + valor1);

WriteLine("Digite o segundo valor");
valor2 = int.Parse(ReadLine());
WriteLine("O segundo valor é: " + valor2);

int total = valor1 + valor2;

WriteLine("A soma dos dois valores é: " + total);
```