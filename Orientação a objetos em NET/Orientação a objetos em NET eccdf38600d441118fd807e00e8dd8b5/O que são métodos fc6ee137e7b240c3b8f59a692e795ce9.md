# O que são métodos

### Métodos e tipos de métodos

- **Métodos**
    - Os métodos determinam o comportamento dos objetos de uma classe e são capazes de controlar o estado da instância. São funções que realizam tarefas. Eles podem ou não retornar valores, e podem ou não receber parâmetros.
    - O envio de mensagens (chamada de métodos) pode alterar o estado de um objeto. Esses métodos temos como difundidos os Getters, os Setters e o Construct
- **Métodos acessores**
    - Os **Getters** ou **métodos acessores** solicitam o acesso a informações de um determinado produto sem dar acesso diretamente a ele, colocando ali uma barreira de proteção para os dados.
    - No exemplo abaixo o **get** retorna o atributo correspondente:
        
        ![Untitled](O%20que%20sa%CC%83o%20me%CC%81todos%20fc6ee137e7b240c3b8f59a692e795ce9/Untitled.png)
        
- **Métodos modificadores**
    - Os **Setters** ou **métodos modificadores** enviam o pedido de alteração de uma determinada informação de um objeto sem que se altere diretamente o mesmo
    - No exemplo abaixo o **set** recebe um valor e o repassa para o atributo:
        
        ![Untitled](O%20que%20sa%CC%83o%20me%CC%81todos%20fc6ee137e7b240c3b8f59a692e795ce9/Untitled%201.png)
        
- **Métodos construtores**
    - A função do **construct** ou método construtor é inicializar ou dar forma à classe. É nele que indicamos os valores dos campos de uma classe. Esses valores podem ser internos (no código) ou externos (passados por parâmetros)
    - As regras para definição de um construtor são:
        - o construtor deve ter o mesmo nome da classe
        - não tem tipo de retorno
        - é executado apenas um, apenas uma vez, no momento da criação do objeto
        - não pode ser chamado diretamente
        - deve ser “public”