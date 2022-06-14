# Manipulando Arrays

### Etapa 1 - Algoritmos de ordenação

- Para ordenar um array, existem diversos algoritmos de ordenação, diferentes técnicas e casos a serem consideradoss
    
    ![Untitled](Manipulando%20Arrays%20693daefd7ac345228ef26a359bbcbca7/Untitled.png)
    

### Etapa 2 - Ordenando via bubble sort

```csharp
public class OperacoesArray
    {
        public void OrdenarBubbleSort(ref int[] array)
        {
            int temp = 0;

            for (int i = 0; i < array.Length; i++)
            {
                for (int j = 0; j < array.Length - 1; j++)
                {
                    if(array[j] > array[j + 1])
                    {
                        temp = array[j + 1];
                        array[j + 1] = array[j];
                        array[j] = temp; 
                    }
                }
            }
        }
        public void ImprimirArray(int[] array)
        {
            foreach (var item in array)
            {
                System.Console.Write(item + " ");
            }
            System.Console.WriteLine("");
        }
    }
```

```csharp
OperacoesArray op = new OperacoesArray();
int[] array = new int[]{5, 4, 3, 1, 2};

WriteLine("Array original:");
op.ImprimirArray(array);

op.OrdenarBubbleSort(ref array);

WriteLine("Array ordenado:");
op.ImprimirArray(array);
```

### Etapa 4 - A classe Array

- A classe Array é uma classe do C# que nos oferece diversos métodos que nos auxiliam a trabalhar com arrays.

### Etapa 5 - Ordenando pela classe Array

```csharp
public void Ordenar(ref int[] array)
{
    Array.Sort(array);
}
```

```csharp
OperacoesArray op = new OperacoesArray();
int[] array = new int[]{5, 4, 3, 1, 2};

WriteLine("Array original:");
op.ImprimirArray(array);

op.Ordenar(ref array);

WriteLine("Array ordenado:");
op.ImprimirArray(array);
```

### Etapa 6 - Copiando um Array

```csharp
public void Copiar(ref int[] array, ref int[] arrayDestino)
{
    Array.Copy(array, arrayDestino, array.Length);
}
```

```csharp
OperacoesArray op = new OperacoesArray();

int[] array = new int[]{5, 3, 4, 1, 2};
int[] arrayCopia = new int[10];

WriteLine("Array antes da cópia:");
op.ImprimirArray(arrayCopia);

op.Copiar(ref array, ref arrayCopia);

WriteLine("Array após a cópia:");
op.ImprimirArray(arrayCopia);
```

### Etapa 7 - Verificando um elemento existente

```csharp
public bool Existe(int[] array, int valor)
{
    return Array.Exists(array, elemento => elemento == valor);
}
public bool ExisteMaior(int[] array, int valor)
{
    return Array.Exists(array, elemento => elemento > valor);
}
```

```csharp
int[] array = new int[]{5, 3, 4, 1, 2};

int valor = 5;

bool existe = op.Existe(array, valor);

if (existe)
    WriteLine("Encontrei o valor {0}", valor);
else
    WriteLine("Não encontrei o valor " + valor);

bool existeMaior = op.ExisteMaior(array, valor);

if (existeMaior)
    WriteLine("Encontrei um valor maior que {0}", valor);
else
    WriteLine("Não encontrei um valor maior que " + valor);
```

### Etapa 8 - Verificando todos os elementos do array

```csharp
public bool TodosMaiorQue(int[] array, int valor)
{
    return Array.TrueForAll(array, elemento => elemento > valor);
}
```

```csharp
OperacoesArray op = new OperacoesArray();

int[] array = new int[]{5, 7, 4, 6, 9};

int valor = 3;

bool todosMaiorQue = op.TodosMaiorQue(array, valor);

if (todosMaiorQue)
    WriteLine("Todos os valores são maiores que " + valor);
else
    WriteLine("Existem valores que não são maiores que " + valor);
```

### Etapa 9 - Encontrando um elemento no array

```csharp
public int ObterValor(int[] array, int valor)
{
    return Array.Find(array, elemento => elemento == valor);
}
```

```csharp
OperacoesArray op = new OperacoesArray();

int[] array = new int[]{5, 7, 4, 6, 9};

int valor = 7;

int valorAchado = op.ObterValor(array, valor);

if (valorAchado > 0)
    WriteLine("Encontrei o valor " + valorAchado);
else
    WriteLine("Não encontrei o valor");
```

### Etapa 10 - Encontrando o índice de um valor

```csharp
public int ObterIndice(int[] array, int valor)
{
    return Array.IndexOf(array, valor);
}
```

```csharp
OperacoesArray op = new OperacoesArray();

int[] array = new int[]{5, 7, 4, 6, 9};

int valor = 4;

int indice = op.ObterIndice(array, valor);

if (indice > -1)
    WriteLine($"O índice do elemento {valor} é {indice}");
else
    WriteLine("O elemento não existe no array");
```

### Etapa 11 - Redimensionando um array

```csharp
public void RedimensionarArray(ref int[] array, int novoTamanho)
{
    Array.Resize(ref array, novoTamanho);
}
```

```csharp
OperacoesArray op = new OperacoesArray();

int[] array = new int[]{5, 7, 4, 6, 9};

WriteLine($"Capacidade atual do array: {array.Length}");

op.RedimensionarArray(ref array, array.Length * 2);

WriteLine($"Capacidade array redimensionado: {array.Length}");
```

### Etapa 12 - Convertendo um array

```csharp
public string[] ConverterParaArrayString(int[] array)
{
    return Array.ConvertAll(array, elemento => elemento.ToString());
}
```

```csharp
OperacoesArray op = new OperacoesArray();

int[] array = new int[]{5, 7, 4, 6, 9};

string[] arrayString = op.ConverterParaArrayString(array);
```