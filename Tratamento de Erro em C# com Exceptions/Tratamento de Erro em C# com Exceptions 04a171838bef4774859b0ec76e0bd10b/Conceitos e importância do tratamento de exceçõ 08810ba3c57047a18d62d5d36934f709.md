# Conceitos e importância do tratamento de exceções

### Conceitos e importância do tratamento de exceções

### Exceções: conceito e tipos

- O que é uma exceção?
    - Qualquer condição de erro ou comportamento inesperado por um programa em execução
        - falha de codificação
        - falta de recursos disponíveis
        - condições inesperadas pelo runtime
- Tipos de erros possíveis
    - Erros de sintaxe
    - Erros em tempo de execução
    - Erros lógicos
- **Erro lógico**
    - Exceção provocada por falha lógica do desenvolvedor
    - Deve ser tratado a partir da correção do código falho
    
    ![Untitled](Conceitos%20e%20importa%CC%82ncia%20do%20tratamento%20de%20excec%CC%A7o%CC%83%2008810ba3c57047a18d62d5d36934f709/Untitled.png)
    
- **Erros de tempo de execução**
    - Erros em tempo de execução que não estão necessariamente relacionados à código mal escrito
        - comum em caso de leitura/escrita de arquivos
- **Falha de sistema**
    - Erro de tempo de execução que não pode ser tratado programaticamente de maneira significativa
        - falta de recursos
        
        ![Untitled](Conceitos%20e%20importa%CC%82ncia%20do%20tratamento%20de%20excec%CC%A7o%CC%83%2008810ba3c57047a18d62d5d36934f709/Untitled%201.png)
        

### Importância do tratamento de erros

- Evitar parada súbita do sistema
- Mensagens amigáveis para usuário final
- Melhor comunicação com desenvolvedores para tratar rapidamente o problema