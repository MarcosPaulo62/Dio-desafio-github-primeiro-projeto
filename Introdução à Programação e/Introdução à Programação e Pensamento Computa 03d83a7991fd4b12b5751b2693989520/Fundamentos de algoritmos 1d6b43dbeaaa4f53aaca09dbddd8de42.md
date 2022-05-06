# Fundamentos de algoritmos

### Tipologia e variáveis

Computador segue instruções para transformar dados em informações

**Tipos de dados**

- Numéricos
    - Inteiros → -2, -1, 0, 1, 2
    - Reais → 5.95, 9.54, -0.555, 0, 1, 2, -5
- Caracteres
    - #, A, ?, !, e
- Lógicos
    - Booleano
        - Verdadeiro - 1
        - Falso - 0

**Variável**

- Mutável
- Possui variações
- Inconstante
- Instável
- Pode assumir qualquer um dos valores de determinado conjunto de valores

**Nome da variável**

- Atribuição de um ou mais caracteres
- Primeira letra - não número
- Sem espaços em branco
- Vedado
    - Utilização de palavras reservadas
- Caracteres e números

**Constante**

- Inalterável
- Invariável
- Tudo aquilo que é fixo ou estável
- Ex.: pi = 3,14

### Instruções primitivas

![Untitled](Fundamentos%20de%20algoritmos%201d6b43dbeaaa4f53aaca09dbddd8de42/Untitled.png)

Ex.: Area = pi*raio²

Instruções são **palavras-chave** (vocabulário) de uma determinada linguagens de programação que tem por finalidade comandar um computador que irá **tratar os dados**

### Estruturas condicionais e operadores

**Condição** → Estado de uma pessoa ou coisa

**Condicional** → Que expressa uma condição ou suposição, Contém ou implica uma suposição ou hipótese

Dada uma **condição**, sendo **satisfeita**, é executada uma **operação** 

**Estrutura condicional:**

- **Simples**
    - Condição
    - ⬇️
    - Operação
- **Composta**
    - Condição   ➡️   Exceção
    - ⬇️
    - Operação
- **Encadeada**
    - Condição   ➡️   Condição   ➡️   Exceção
    - ⬇️                     ⬇️
    - Operação          Operação

**Operadores Relacionais**

![Untitled](Fundamentos%20de%20algoritmos%201d6b43dbeaaa4f53aaca09dbddd8de42/Untitled%201.png)

**Operadores lógicos** 

- AND
- OR
- NOT

### Estruturas de repetição

Laços, Controle de fluxo, Malhas de repetição, Loop

![Untitled](Fundamentos%20de%20algoritmos%201d6b43dbeaaa4f53aaca09dbddd8de42/Untitled%202.png)

Condição de parada

- Número de repetições pré-fixada
- Condição a ser satisfeita

Mas não é só repetir o código? Qual a vantagem?

- Redução de linhas
- Compreensão facilitada
- Redução de erro

Tipos de estruturas 

- Enquanto **...** faça
- Repita **...** até
- Para **...** de **...** até **...** faça

### Vetores e matrizes

- “Um vetor é caracterizado por uma variável dimensionada com tamanho pré-fixado.”
- “Matriz é uma tabela organizada em linhas e colunas no formato **m x n**, onde **m** representa o número de linhas (horizontal) e **n** o número de colunas (vertical)”
- vetor[15] → vetor de 15 posições
- matriz[6][6] → matriz de 6 colunas e 6 linhas

### O que são funções?

- Função, Subprograma, Subalgoritmo, Bloco, Sub-rotina, Método
- Similar ao conceito de função matemática
- As funções, ou sub-rotinas são blocos de instruções que realizam tarefas específicas
- Modularização do programa
- Código mais claro e conciso
- Reutilização de instruções
- “São blocos de instruções (código), identificados por **nomes e parâmetros”**
    - Definição
    - Nome
    - Invocação
    - Variável local → São destruídas ao encerrar a função
- Dados ➡️ Função ➡️ Resultado

![Untitled](Fundamentos%20de%20algoritmos%201d6b43dbeaaa4f53aaca09dbddd8de42/Untitled%203.png)

### Instruções de entrada/saída

- **Entrada** → Consiste na inserção e recebimento de dados do mundo real por meio de ação de alguma interface, seja teclado, mouse, arquivos, entre outros.
- **Saída →** Consiste na impressão dos dados do mundo abstrato, digital por meio de ação de alguma interface.
Os formatos podem variar desde simples arquivos binários até complexas querys de banco de dados.
    - Saída por interrupção → Definida pelos periféricos
    - Saída programada → Condicional ou Incondicional
    - Casos de saída
        - Bem sucedida
        - Erro de sintaxe ou outro
        - Erros de programação
        - Problemas com a interface