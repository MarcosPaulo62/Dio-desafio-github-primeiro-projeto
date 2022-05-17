# Conhecendo variáveis e instruções

### Tipos de valor

- **Tipos de valor**
    - Variáveis de tipo de valor contêm diretamente seus dados
    - As variáveis têm sua própria cópia dos dados e não é possível que as operações afetem outra variável (exceto no caso das variáveis de parâmetro ref e out)
    - Númericos: **sbyte, short, int, long, byte, ushort, uint, ulong**
    - Caracteres Unicode: **char**
    - Pontos flutuantes: **float, double, decimal**
    - Booleano: **bool**
    - **enum, struct e tipos nullable (Exemplo int?)**
- **Tipos de referência**
    - Variáveis de tipos de referência armazenam referências a seus dados
    - É possível que duas variáveis façam referência ao mesmo objeto e, portanto, que operações em uma variável afetem o objeto referenciado pela outra variável
    - Tipos Classe: **class, objet, string**
    - Tipos Arrays: **int[], int[,], etc...**
    - **interface, delegate**
    

### Utilizando instruções em programas

- Ações de um programa são expressas usando instruções
- {
        Um bloco permite que várias instruções sejam escritas em contextos
}
- **Instruções**
    - Declaração de variáveis e constantes locais
    - if
    - switch
    - while
    - do
    - for
    - foreach
    - break
    - continue
    - return
    - throw
    - try .. catch .. finally
    - using

### Exemplificando o conteúdo

- <instruções em código explicadas → https://github.com/gabrielfaraday/csharp-examples>
- **Array**
    - Um **array** é uma estrutura de dados que contém um número X de **elementos**, todos do mesmo **tipo**, que são acessados através de **índices** computados
    - Arrays são tipos de referência e a declaração de uma variável array simplesmente reserva espaço para uma referência de uma instância de array
    - Ao criar um array é especificado o **tamanho** da nova instância, que é fixo durante todo o tempo de vida da instância
    - Os índices dos elementos de um array variam de **0** a **comprimento do array - 1**
    - **Array unidimensional**
        
        ![Untitled](Conhecendo%20varia%CC%81veis%20e%20instruc%CC%A7o%CC%83es%20dc020d2164c14f04ad252c7405a604ba/Untitled.png)
        
    - **Array multidimensional**
        
        ![Untitled](Conhecendo%20varia%CC%81veis%20e%20instruc%CC%A7o%CC%83es%20dc020d2164c14f04ad252c7405a604ba/Untitled%201.png)
        
    - **Inicializador de array**
        
        ![Untitled](Conhecendo%20varia%CC%81veis%20e%20instruc%CC%A7o%CC%83es%20dc020d2164c14f04ad252c7405a604ba/Untitled%202.png)
        
        ou
        
        ![Untitled](Conhecendo%20varia%CC%81veis%20e%20instruc%CC%A7o%CC%83es%20dc020d2164c14f04ad252c7405a604ba/Untitled%203.png)
        
        ou
        
        ![Untitled](Conhecendo%20varia%CC%81veis%20e%20instruc%CC%A7o%CC%83es%20dc020d2164c14f04ad252c7405a604ba/Untitled%204.png)