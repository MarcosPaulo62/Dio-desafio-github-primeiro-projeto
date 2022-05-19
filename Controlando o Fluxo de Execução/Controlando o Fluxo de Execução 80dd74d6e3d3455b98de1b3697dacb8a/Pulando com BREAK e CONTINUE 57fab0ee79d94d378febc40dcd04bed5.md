# Pulando com BREAK e CONTINUE

### Pulando com BREAK e CONTINUE

```csharp
Boolean condicao = true;
int valor;

do {
    WriteLine("Digite um valor, 0 para sair");
    valor = int.Parse(ReadLine());

    if (valor == 0)
    {
        WriteLine("Você saiu.");
        break;
    }
    else
    {
        WriteLine("Você digitou "+ valor);
        continue;
    }
} while (condicao == true);
```