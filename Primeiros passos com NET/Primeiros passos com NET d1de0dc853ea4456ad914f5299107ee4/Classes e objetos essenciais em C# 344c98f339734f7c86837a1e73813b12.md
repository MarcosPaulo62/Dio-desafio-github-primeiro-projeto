# Classes e objetos essenciais em C#

### O que são Classes e Objetos em C#

- Classes são os tipos mais fundamentais de C#
- Uma classe é uma estrutura de dados que combina estado (campos) e ações (métodos)
- Objetos são instâncias de uma classe
- As classes suportam herança e polimorfismo, mecanismos pelos quais as classes derivadas podem estender e especializar as classes base

![Untitled](Classes%20e%20objetos%20essenciais%20em%20C#%20344c98f339734f7c86837a1e73813b12/Untitled.png)

- Instâncias de classes (objetos) são criadas usando o operador new, que aloca memória para uma nova instância, chama um construtor para inicializar a instância e retorna uma referência à instância
    
    ```csharp
    Ponto p1 = new Ponto(0, 0);
    ```
    
    ```csharp
    Ponto p2 = new Ponto(10, 20);
    ```
    
- A memória ocupada por um objeto é recuperada automaticamente quando o objeto não está mais acessível. Não é necessário nem possível desalocar explicitamente objetos em C#
- **Membros**
    - Os membros de uma classe podem ser estáticos ou membros da instância
    - Membros estáticos pertencem a classe e membros de instância pertencem ao objeto
    - Constantes, variáveis, métodos, propriedades, construtores, etc...
- **Acessibilidade**
    - Cada membro de uma classe tem uma acessibilidade associada, que controla as regiões do texto do programa que podem acessar o membro
    - Podem ser:
        - public
        - protected
        - internal
        - private
- **Herança**
    - Uma declaração de classe pode especificar uma classe base, herdando os membros public, internal e protected da classe base
    - Omitir uma especificação de classe base é o mesmo que derivar do tipo object
- **Métodos**
    - Um método é um membro que implementa uma computação ou ação que pode ser executada por um objeto ou classe
    - Os métodos podem ter uma lista de parâmetros, que representam valores ou referências de variáveis passados para o método, e um tipo de retorno, que especifica o tipo do valor calculado e retornado pelo método
    

### Como aplicar classes e objetos em projetos

- <instruções em código explicadas → ‣>