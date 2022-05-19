# Entendendo o que são Value Types e References Types

### **Apresentação e Visão geral do curso**

- **Objetivo do curso**
    - Entender a diferença entre utilizar variáveis por referência e valor, será fundamental para entender como o computador executa o código que você escreve. Ou seja, sem entender esse conceito fundamental um desenvolvedor terá muitos problemas para descobrir **bugs** (Comportamento indesejado no código).

### **Entendendo o que são Value Types e Reference Types**

- **Common Type System (CTS)**
    
    ![Untitled](Entendendo%20o%20que%20sa%CC%83o%20Value%20Types%20e%20References%20Typ%2070486272c74e446c8450ff6776ee202f/Untitled.png)
    
- **Value Type**
    - Contém uma INSTÂNCIA do tipo criado
    - A instância sempre é copiada ao atribuir o valor para outra variável
    - Alocação na Stack (melhor performance)
    - O valor inicial é sempre o valor default de cada tipo
- **Reference Types**
    - Contém uma REFERÊNCIA para uma instância do tipo criado
    - A referência nunca muda ao atribuir o valor para outra variável
    - Na STACK fica um ponteiro e a alocação na HEAP
    - Seu valor inicial é sempre “Null”
    - Requer gerenciamento da Memória através do GC
- **Value Types**
    - Tipos primitivos
        - Valores numéricos
            - int
            - decimal
            - double, etc
        - Boolean (true/false)
        - Char
        - Tuples
- **Reference Types**
    - Classe
    - Interface
    - Delegate
    - Record
    - Object
    - String

### **Criando o projeto no VS Code**

- Ir na **launch.json** da pasta **.vscode** e colocar **"integratedTerminal”** no campo **“console”**
- Usar **“using static *System*.Console;”** para não precisar digitar Console toda hora