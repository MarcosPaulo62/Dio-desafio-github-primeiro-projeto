# Entendendo a classe System.Exception

### Hierarquia de classes exception

![Untitled](Entendendo%20a%20classe%20System%20Exception%20c0e8a2daf4794bc7bbd4eba7416bd623/Untitled.png)

- Toda exceção em .NET herda da classe System.Exception
- Algumas exceções comuns
    
    ![Untitled](Entendendo%20a%20classe%20System%20Exception%20c0e8a2daf4794bc7bbd4eba7416bd623/Untitled%201.png)
    

### Propriedades e métodos úteis da classe Exception

- Propriedades importantes herdadas:
    - Message: descrição legível para humanos com a causa da exceção
    - InnerException: obtém conjunto de exceções superiores ou exceção que levou à exceção atual.
    - StackTrace: rastreamento do caminho até chegar ao erro
    - Source: relacionada à aplicação ou objeto que causou o erro
    - TargetSite: relacionada ao método que lançou a exceção atual
- **Métodos**
    
    ![Untitled](Entendendo%20a%20classe%20System%20Exception%20c0e8a2daf4794bc7bbd4eba7416bd623/Untitled%202.png)
    
    - Dada uma cadeia de exceções, somente uma delas pode ser a causa raiz para todas as outras, portanto é a ‘exceção base’
    
    ![Untitled](Entendendo%20a%20classe%20System%20Exception%20c0e8a2daf4794bc7bbd4eba7416bd623/Untitled%203.png)
    
    - Configuração de informações relacionadas à exceção lançada
        - info: guarda objeto de dados serializados
        - context: contém informação de contexto sobre origem ou destino dos dados a serem transmitidos
    
    ![Untitled](Entendendo%20a%20classe%20System%20Exception%20c0e8a2daf4794bc7bbd4eba7416bd623/Untitled%204.png)
    
    - Retorna tipo da instância atual em tempo de execução
    
    ![Untitled](Entendendo%20a%20classe%20System%20Exception%20c0e8a2daf4794bc7bbd4eba7416bd623/Untitled%205.png)
    
    - Retorna representação da atual exceção em forma de string

### Comandos para lançar e tratar exceções

- Comando **try**
    - Provê mecanismo para capturar exceções que ocorrem durante a execução de certo bloco de código
- Comando **catch**
    - Após a captura, o sistema procura pelo comando catch mais próximo que pode lidar com a exceção
    - Pode usar mais de um catch, do mais específico pro mais generalista
- Comando **finally**
    - Bloco útil para liberação de recursos, pois sempre é executado, independente da captura e tratamento da exceção
        
        ![Untitled](Entendendo%20a%20classe%20System%20Exception%20c0e8a2daf4794bc7bbd4eba7416bd623/Untitled%206.png)
        
- Comando **throw**
    - Lança uma exceção em código explicitamente
    
    ![Untitled](Entendendo%20a%20classe%20System%20Exception%20c0e8a2daf4794bc7bbd4eba7416bd623/Untitled%207.png)
    
    - Utilizar o comando em um contexto de exceção já capturada, faz o “relançamento” da exceção dentro do catch, provendo assim mais informações para depuração
- Comando **when**
    - Trata exceções de acordo com requerimentos específicos que você define para dada exceção
    - Útil quando uma exceção pode ser tratada igualmente para múltiplos erros sob determinadas condições
- **Customizando exceções**
    
    ```csharp
    int a = 100, b = 0;
    
    double resulatdo = 0;
    
    try // captura a exceção
    {
        if (b == 0)
            throw new ArithmeticException(); // lança uma exceção
    
        resulatdo = a / b;
    
        System.Console.WriteLine(resulatdo);
    }
    catch(DivideByZeroException ex) when (a < 1000) // trata exceçção divisão por zero, se a for menor que mil
    {
        System.Console.WriteLine(ex.Message + " - 1°");
    }
    catch(Exception ex) // trata qualquer exceção
    {
        System.Console.WriteLine(ex.Message + " - 2°");
        throw; // relança a exceção
    }
    finally // é impresso sempre
    {
        System.Console.WriteLine("Divisão finalizada.");
    }
    ```