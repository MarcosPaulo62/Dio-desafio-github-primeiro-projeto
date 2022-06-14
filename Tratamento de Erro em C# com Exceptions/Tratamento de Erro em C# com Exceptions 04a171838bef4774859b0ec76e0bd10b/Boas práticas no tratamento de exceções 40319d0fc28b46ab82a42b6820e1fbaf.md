# Boas práticas no tratamento de exceções

### Boas práticas no tratamento de exceções

- Use **try/catch/finally** em trechos de códigos que podem potencialmente gerar exceções e que de fato seu próprio código também consegue tratar
- Nos blocos **catch,** sempre ordene os tratamentos das exceções das classes mais específicas para mais genéricas
- Faça limpeza automática de recursos alocados com **using .**
Caso o objeto não implemente IDisposable utilize **finally**
- Caso exista uma condição com grandes chances de erro, verifique a viabilidade de checar a condição antes de somente tratar a exceção
    
    ![Untitled](Boas%20pra%CC%81ticas%20no%20tratamento%20de%20excec%CC%A7o%CC%83es%2040319d0fc28b46ab82a42b6820e1fbaf/Untitled.png)
    
- Projete classes de forma que as exceções sejam evitadas ou minimizadas
- Lance exceções ao invés de somente retornar um status code
- Somente crie novas classes de exceções, caso as pré-definidas não satisfaçam as necessidades do código
- Crie classes com a terminação Exception e derivadas diretamente da classe base **Exception**
- Utilize no mínimo os construtores já definidos na classe base
- Escreva mensagens de erros claras e sucintas
- É uma boa prática incluir strings traduzidas de acordo com a linguagem do usuário da aplicação através de **sattelites assemblies**
- Em exceções customizadas forneça propriedades adicionais conforme necessidade
- Utilize o comando **throw** para que o stack trace seja mais útil, pois o rastreio começa a partir do lançamento até a captura da exceção
- Utilize métodos construtores de exceções
- Restaure o estado da aplicação caso os métodos completem sua execução devido à exceções