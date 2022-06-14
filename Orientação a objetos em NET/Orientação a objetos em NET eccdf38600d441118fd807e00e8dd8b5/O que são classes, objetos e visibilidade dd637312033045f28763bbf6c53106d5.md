# O que são classes, objetos e visibilidade

### Principais conceitos de classes, objetos e visibilidade

- **Classes**
    - Pode ser considerado como se fosse um molde para o objeto, contendo dentro de si as principais informações para a sua criação. Define os atributos e métodos comuns que serão compartilhados por um objeto.
        
        ![Untitled](O%20que%20sa%CC%83o%20classes,%20objetos%20e%20visibilidade%20dd637312033045f28763bbf6c53106d5/Untitled.png)
        
        ![Untitled](O%20que%20sa%CC%83o%20classes,%20objetos%20e%20visibilidade%20dd637312033045f28763bbf6c53106d5/Untitled%201.png)
        
- **Objetos**
    - Considera-se um objeto tudo aquilo que em geral possui atributos, comportamentais e um estado. A classe em si é um conceito abstrato, como um molde, que se torna concreto e palpável através da criação de um objeto.
    - Na programação o objeto é uma instanciação (criação a partir) de uma classe. Para criarmos ou “instanciarmos” objetos de uma determinada classe, utilizamos o operador **new.**
        
        ![Untitled](O%20que%20sa%CC%83o%20classes,%20objetos%20e%20visibilidade%20dd637312033045f28763bbf6c53106d5/Untitled%202.png)
        
- **Visibilidade**
    - A visibilidade é importante para a proteção do código e suas funcionalidades, define quem pode alterar cada dado dos trechos de código em três principais níveis:
        - **Pública**
        - **Privada**
        - **Protegida**
        
        ![Untitled](O%20que%20sa%CC%83o%20classes,%20objetos%20e%20visibilidade%20dd637312033045f28763bbf6c53106d5/Untitled%203.png)
        
    - Esse encapsulamento de atributos e métodos impede o chamado vazamento de escopo, onde um atributo ou método é visível por alguém que não deveria vê-lo, como outro objeto ou classe.
    - Isso evita a confusão do uso de variáveis globais no programa, deixando mais fácil de identificar em qual estado cada variável vai estar a cada momento do programa, já que a restrição de acesso nos permite identificar quem consegue modificá-la.