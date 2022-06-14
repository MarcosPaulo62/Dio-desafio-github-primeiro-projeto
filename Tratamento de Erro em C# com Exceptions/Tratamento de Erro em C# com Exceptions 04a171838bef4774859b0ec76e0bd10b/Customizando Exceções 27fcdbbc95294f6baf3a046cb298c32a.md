# Customizando Exceções

### Customizando Exceções

- Apesar da hierarquia de classes existentes com base na classe Exception, é possível criar sua própria classe de exceção de acordo com a necessidade
- Motivações:
    - Quando uma exceção reflete um erro específico que não foi mapeado por uma classe de exceção existente
    - Quando a exceção necessita de um tratamento diferenciado
- Procedimento:
    - Definir uma classe que herda de Exception
    - Definir construtores da classe
    - Se necessário, sobrescreva membros cujo comportamento queira modificar
    - Definir se a exceção será serializável
- Classe:
    
    ```csharp
    using System.Runtime.Serialization;
    
    namespace Projeto
    {
        [Serializable]
        public class MyClassException : Exception
        {      
            public MyClassException()
            {
            }
            public MyClassException(string? message) : base(message)
            {
            }
            public MyClassException(string? message, Exception? innerException) : base(message, innerException)
            {
            }
            public MyClassException(SerializationInfo info, StreamingContext context) : base(info, context)
            {
            }
    
            // Pra cima tudo herdado, pra baixo customizar
            
            public string? MyProperty { get; set; }
        }
    }
    ```
    
- Programa:
    
    ```csharp
    using Projeto;
    
    int a = 100, b = 0;
    
    double resulatdo = 0;
    
    try // captura a exceção
    {
        if (b == 0)
            throw new MyClassException("Minha mensagem customizada de erro"); // lança uma exceção
    
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
    }
    finally // é impresso sempre
    {
        System.Console.WriteLine("Divisão finalizada.");
    }
    ```