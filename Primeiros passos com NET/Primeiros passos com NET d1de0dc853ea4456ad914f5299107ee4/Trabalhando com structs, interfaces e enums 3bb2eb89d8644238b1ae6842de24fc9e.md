# Trabalhando com structs, interfaces e enums

### O que são Structs

- Como as classes, as structs são estruturas de dados que podem conter membros de dados e membros de ação, mas diferentemente das classes, as structs são tipos de valor e não requerem alocação de heap
- Uma variável de um tipo de struct armazena diretamente os dados da estrutura, enquanto uma variável de um tipo de classe armazena uma referência a um objeto alocado na memória
- Structs não aceitam herança determinada pelo desenvolvedor
- São úteis para pequenas estruturas de dados que possuem semântica de valor: números complexos, pontos em um sistema de coordenadas ou pares de chave-valor em um dicionário são bons exemplos de utilização
- O uso de structs em vez de classes para pequenas estruturas de dados pode fazer uma grande diferença no número de alocações de memória

![Untitled](Trabalhando%20com%20structs,%20interfaces%20e%20enums%203bb2eb89d8644238b1ae6842de24fc9e/Untitled.png)

- Construtores de structs são chamados com o operador new, semelhante a um construtor de classe, mas em vez de alocar dinamicamente um objeto no heap gerenciado e retornar uma referência a ele, um construtor struct simplesmente retorna o próprio valor struct (normalmente em um local temporário na stack), e esse valor é copiado conforme necessário

### Entendendo a função de interfaces e enums

- **Interfaces**
    - Uma interface define um contrato que pode ser implementado por classes e structs
    - Uma interface pode conter métodos, propriedades, eventos e indexadores
    - Uma interface não fornece implementações dos membros que define - apenas suas “assinaturas”
    - As interfaces podem empregar herança múltipla
    
    ![Untitled](Trabalhando%20com%20structs,%20interfaces%20e%20enums%203bb2eb89d8644238b1ae6842de24fc9e/Untitled%201.png)
    
    ![Untitled](Trabalhando%20com%20structs,%20interfaces%20e%20enums%203bb2eb89d8644238b1ae6842de24fc9e/Untitled%202.png)
    
- **Enums**
    - Um enum é um tipo de valor distinto com um conjunto de constantes nomeadas
    - Você define enumerações quando precisa definir um tipo que pode ter um conjunto de valores discretos. Eles usam um dos tipos de valor integral como armazenamento subjacente. Eles fornecem significado semântico aos valores discretos
    
    ![Untitled](Trabalhando%20com%20structs,%20interfaces%20e%20enums%203bb2eb89d8644238b1ae6842de24fc9e/Untitled%203.png)
    
    ![Untitled](Trabalhando%20com%20structs,%20interfaces%20e%20enums%203bb2eb89d8644238b1ae6842de24fc9e/Untitled%204.png)
    
    - Cada tipo de enum possui um tipo integral correspondente chamado tipo subjacente do tipo de enum
    - Um tipo de enumeração que não declara explicitamente um tipo subjacente tem um tipo subjacente int
    
    ![Untitled](Trabalhando%20com%20structs,%20interfaces%20e%20enums%203bb2eb89d8644238b1ae6842de24fc9e/Untitled%205.png)