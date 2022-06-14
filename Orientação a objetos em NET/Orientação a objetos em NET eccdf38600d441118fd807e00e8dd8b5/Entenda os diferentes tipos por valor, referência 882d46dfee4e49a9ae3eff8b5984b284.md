# Entenda os diferentes tipos por valor, referência e ponteiro

### Valor, referência e ponteiro

### **Tipos por Valor**

- O C# tem duas grandes categorias de tipos: por valor e por referência. Os tipos por valor são gerenciados diretamente e têm as seguintes características principais:
    - Todos os tipos de dados numéricos
    - Não precisam ser inicializados com o operador **new**
    - A variável armazena o valor diretamente
    - A atribuição de uma variável a outra copia o conteúdo, criando efetivamente outra cópia da variável
    - Não podem conter o valor null
    - Exemplos de variáveis desse tipo são: integers, doubles, floats e char
- **Inteiros**
    - Os tipos inteiros (Integers) têm sempre o mesmo significado, independentemente da implementação
        
        ![Untitled](Entenda%20os%20diferentes%20tipos%20por%20valor,%20refere%CC%82ncia%20882d46dfee4e49a9ae3eff8b5984b284/Untitled.png)
        
- **Double e Float**
    - Os números de ponto flutuante são bastante convencionais, as operações de ponto flutuante não geram erros
        
        ![Untitled](Entenda%20os%20diferentes%20tipos%20por%20valor,%20refere%CC%82ncia%20882d46dfee4e49a9ae3eff8b5984b284/Untitled%201.png)
        
- **Caracteres**
    - Em C#, todos os caracteres (char) são armazenados no padrão Unicode e usam 16 bits por caractere. O Unicode permite armazenar os caracteres de todas as línguas vivas (como grego, japonês, chinês e coreano) e algumas mortas (como sânscrito
        
        ![Untitled](Entenda%20os%20diferentes%20tipos%20por%20valor,%20refere%CC%82ncia%20882d46dfee4e49a9ae3eff8b5984b284/Untitled%202.png)
        

### Tipos por referência

- Um tipo por referência armazena uma referência a seus dados. Os tipos de referência incluem o seguinte:
    - Duas variáveis poderem conter a referência a um mesmo objeto
    - Operações em uma afetam a outra
    - Todas as matrizes, mesmo que seus elementos sejam de tipos de valor
    - Exemplos de tipos de referência: Strings, classes e arrays
- **Strings**
    - Semelhante ao char, strings são variáveis do tipo texto. São uma sequência de caracteres, geralmente utilizada para representar palavras, frases ou textos de um programa.
        
        ![Untitled](Entenda%20os%20diferentes%20tipos%20por%20valor,%20refere%CC%82ncia%20882d46dfee4e49a9ae3eff8b5984b284/Untitled%203.png)
        
    - As strings são consideradas imutáveis e não podem ser alteradas depois de criadas. Quando você efetua uma operação qualquer, como por exemplo, concatenar um caractere, você na verdade está criando outra string e descartando a anterior.
- **Classes**
    - Como visto anteriormente é um tipo definido pelo usuário e correspondem a uma class. As classes são sempre derivadas de object e podem conter campos, métodos e propriedades. Uma classe pode derivar de uma única outra classe, e também de várias intefaces
- Um **array** (matriz) é uma lista de valores onde todos os valores no grupo são referenciados pelo nome da matriz e o índice atribuído ao valor específico na matriz.

### Tipo Ponteiro

- Um **ponteiro** ou **apontador** é um tipo de dado de cujo valor se refere diretamente a um outro valor alocado em outra área da memória, através de seu endereço.