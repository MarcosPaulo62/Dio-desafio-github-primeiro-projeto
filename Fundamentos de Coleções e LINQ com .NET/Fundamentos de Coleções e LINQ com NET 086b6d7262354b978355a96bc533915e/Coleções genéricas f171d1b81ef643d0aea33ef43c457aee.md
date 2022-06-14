# Coleções genéricas

### Etapa 1 - Introdução coleções genéricas

- No C#, existem classes de coleções que agrupam valores, e essas classes são padronizadas para as operações mais comuns, como:
    - Ordenação
    - Obter valor por índice
    - Obter valor com expressões
    - Trabalhar com tamanhos dinâmicos

### Etapa 2 - Declarando e acessando uma lista

```csharp
List<string> estados = new List<string>();

estados.Add("SP");
estados.Add("MG");
estados.Add("BA");

WriteLine($"Quantidade de elementos na lista: {estados.Count}");

foreach (var item in estados)
{
    WriteLine(item);
}

for (int i = 0; i < estados.Count; i++)
{
    WriteLine($"Índice {i}, Valor: {estados[i]}");
}
```

### Etapa 3 - Removendo elemento da lista

```csharp
OperacoesLista opLista = new OperacoesLista();

List<string> estados = new List<string>();

estados.Add("SP");
estados.Add("MG");
estados.Add("BA");

WriteLine($"Quantidade de elementos na lista: {estados.Count}");

opLista.ImprimeListaString(estados);

WriteLine("Removendo o elemento");
estados.Remove("MG");

opLista.ImprimeListaString(estados);
```

### Etapa 4 - Adicionando coleções na lista

```csharp
OperacoesLista opLista = new OperacoesLista();

List<string> estados = new List<string>{"SP", "MG", "BA"};
string[] estadosArray = new string[]{"RJ", "SC"};

WriteLine($"Quantidade de elementos na lista: {estados.Count}");

opLista.ImprimeListaString(estados);

WriteLine("");

estados.AddRange(estadosArray);

opLista.ImprimeListaString(estados);
```

### Etapa 5 - Adicionando elemento por índice

```csharp
OperacoesLista opLista = new OperacoesLista();

List<string> estados = new List<string>{"SP", "MG", "BA"};

WriteLine($"Quantidade de elementos na lista: {estados.Count}");

opLista.ImprimeListaString(estados);

WriteLine("");

estados.Insert(1, "RJ");

opLista.ImprimeListaString(estados);
```