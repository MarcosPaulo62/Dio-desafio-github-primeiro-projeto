# Comandos de repetição, FOR, FOREACH, DO e WHILE

### Comandos de repetição, FOR, FOREACH, DO e WHILE

- **WHILE**

```csharp
Boolean condicao = true;
int valor;

while (condicao == true)
{
    WriteLine("Digite um valor, 0 para sair");
    valor = int.Parse(ReadLine());

    if (valor == 0)
    {
        WriteLine("Você saiu.");
        condicao = false;
    }
    else
        WriteLine("Você digitou "+ valor);
}
```

- **DO**

```csharp
Boolean condicao = true;
int valor;

do {
    WriteLine("Digite um valor, 0 para sair");
    valor = int.Parse(ReadLine());

    if (valor == 0)
    {
        WriteLine("Você saiu.");
        condicao = false;
    }
    else
        WriteLine("Você digitou "+ valor);
} while (condicao == true);
```

- **FOR**

```csharp
WriteLine("Digite um valor");
int valor = int.Parse(ReadLine());

for (int i = valor; i <= 10; i++)
{
    WriteLine(i);
}
```

- **FOREACH**

```csharp
int[] lista = {1, 2, 3, 4, 5, 6};

foreach(int numero in lista)
{
    WriteLine(numero);
}
```