# Lendo e escrevendo arquivos com Streams

### stringWriterReader - teoria

- Stream é uma classe abstrata que fornece uma visão genérica de uma sequência de bytes.
- Existe uma grande vantagem de se utilizar Streams, pois os dados são escritos, lidos ou modificados através de um **Buffer**
- Buffer - Espécie de reservatório onde podemos armazenar uma grande quantidade de dados em pequenos pedaços. O famoso dividir para conquistar

![Untitled](Lendo%20e%20escrevendo%20arquivos%20com%20Streams%201f4cd554f6554bea8a8d4c541568ee62/Untitled.png)

### stringReader - prática

```csharp
using System.Text;

var sb = new StringBuilder();

sb.AppendLine("Primeira linha do texto");
sb.AppendLine("Segunda linha");
sb.AppendLine("Última");

using var sr = new StringReader(sb.ToString());

var buffer = new char[10];
var tamanho = 0;

do
{
    System.Console.WriteLine(sr.ReadLine()); // vai ler uma linha do texto

} while (sr.Peek() >= 0); // sr.Peek retorna -1 quando não tiver mais linhas

// do
// {
//     buffer = new char[10]; // limpar o buffer
//     tamanho = sr.Read(buffer); // Passa os caracteres pro buffer e retorna a quantidade, no caso 10
//     System.Console.Write(string.Join("", buffer)); // Imprime os caracteres do buffer

// } while (tamanho >= buffer.Length);

System.Console.WriteLine("[enter] para finalizar...");
Console.ReadKey();
```

### stringWriter - prática

```csharp
string textReaderText = "Cristiano Ronaldo dos Santos Aveiro é " +
                        "um futebolista português que atua como " +
                        "extremo-esquerdo ou ponta de lança.\n" +

                        "Atualmente joga pelo Manchester United e " +
                        "pela Seleção Portuguesa. É o jogador com " +
                        "mais golos na história do futebol em jogos " +
                        "oficiais.\n\n";

System.Console.WriteLine($"Texto original: {textReaderText}");

string linha, paragrafo = null;

var sr = new StringReader(textReaderText);

while(true)
{
    linha = sr.ReadLine();
    if (linha != null)
        paragrafo += linha + " ";
    else
    {
        paragrafo += "\n";
        break;
    }
}

System.Console.WriteLine($"Texto modificado: {paragrafo}");
int caractereLido;
char caractereConvertido;

var sw = new StringWriter();
sr = new StringReader(paragrafo);

while(true)
{
    caractereLido = sr.Read(); // recebe um decimal referente ao caractere
    if(caractereLido == -1) // quando acabar os caracteres é retornado -1
        break;

    caractereConvertido = Convert.ToChar(caractereLido); // converte o decimal em caractere

    if(caractereConvertido == '.')
    {
        sw.Write("\n\n");
    }
    else 
    {
        sw.Write(caractereConvertido);
    }
}

System.Console.WriteLine($"Texto armazenado no StreamWriter: {sw.ToString()}\n\n");
System.Console.WriteLine("Pressione [enter] para sair");
Console.ReadKey();
```