# Coleções específicas

### Etapa 1 - Introdução coleções específicas

- As coleções específicas implementam regras para sua ordem de acesso e manipulação de seus elementos, são elas:
    - **Queue** **(Fila):** Obedece a ordem FIFO (First In First Out)
    - **Stack (Pilha):** Obedece a ordem LIFO (Last In First Out)

### Etapa 2 - Introdução a Fila

![Untitled](Colec%CC%A7o%CC%83es%20especi%CC%81ficas%200f7fdbba48554fa2a65d7cde9caa6cac/Untitled.png)

### Etapa 3 - Filas na prática

```csharp
Queue<string> fila = new Queue<string>();

fila.Enqueue("Marcos");
fila.Enqueue("Paulo");
fila.Enqueue("Giulia");
fila.Enqueue("André");

WriteLine($"Pessoas na fila {fila.Count}");
while(fila.Count > 0)
{
    WriteLine($"Vez de: {fila.Peek()}");
    WriteLine($"{fila.Dequeue()} atendido");
}
WriteLine($"Pessoas na fila {fila.Count}");
```

### Etapa 4 - Introdução a Pilha

![Untitled](Colec%CC%A7o%CC%83es%20especi%CC%81ficas%200f7fdbba48554fa2a65d7cde9caa6cac/Untitled%201.png)

### Etapa 5 - Pilha na prática

```csharp
Stack<string> pilhaLivros = new Stack<string>();

pilhaLivros.Push("Código Limpo");
pilhaLivros.Push("1984");
pilhaLivros.Push("Do Mil ao Milhão");

WriteLine($"Livros na pilha {pilhaLivros.Count}");
while (pilhaLivros.Count > 0)
{
    WriteLine($"Próximo livro para leitura: {pilhaLivros.Peek()}");
    WriteLine($"{pilhaLivros.Pop()} lido");
}
WriteLine($"Livros na pilha {pilhaLivros.Count}");
```