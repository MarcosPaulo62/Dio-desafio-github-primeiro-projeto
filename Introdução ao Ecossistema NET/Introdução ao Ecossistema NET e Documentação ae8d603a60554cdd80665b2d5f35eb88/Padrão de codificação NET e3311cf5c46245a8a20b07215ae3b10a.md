# Padrão de codificação .NET

### O que é escrever um bom código?

- “Bom código”
    - Ser confiável
    - Ser sustentável
    - Ser eficiente
- Por que e como devemos padronizar?
    - Melhorar comunicação entre equipe
    - Facilitar manutenção de códigos
    - Utilizar documentação e boas práticas de codificação, como clean code
    

### Entender o Clean Code

- **O que é?**
    - Conjunto de boas práticas na escrita de software para obtenção de maior legibilidade e manutenibilidade de código
- **Regras gerais**
    1. Siga SEMPRE as convenções adotadas pela equipe!
    2. KISS: Keep It Stupid Simple (Mantenha isto estupidamente simples)
    3. Devolva o código mais limpo do que você encontrou
    4. Busque sempre entender e solucionar os problemas a partir de sua raiz
- **Regras para entendimento de código**
    1. Seja consistente na escrita de todo o código
    2. Utilize variáveis concisas e que realmente passem a informação necessária
    3. Observe a necessidade de criação de objetos de valor ao invés do uso de tipos primitivos
    4. Evite dependências lógicas
    5. Evite condicionais negativas
- **Regras para nomeação**
    1. Escolher nomes descritivos para classes, variáveis e métodos
    2. Para variáveis semelhantes, faça uma distinção identificável
    3. Utilizar nomes de fácil leitura e busca
    4. Utilize constantes para guardar strings a serem comparadas
    5. Não use prefixos ou caracteres especiais
- **Regras para métodos**
    1. Métodos não devem ser grandes e devem possuir somente um objetivo/responsabilidade
    2. Métodos devem possuir nomes descritivos
    3. Evite a exigência de muitos parâmetros dentro do método
    4. Evite que uma função altere valores de outra classe sem ser a própria classe
    5. Evite utilização de flags desnecessárias
- **Regras para comentários**
    1. Evite comentários desnecessários, torne seu código autoexplicativo
    2. Não seja redundante
    3. Não deixe código desnecessário comentado
    4. Comentários podem ser úteis para falar sobre a intenção de uma classe ou método
    5. Comentários podem explanar regras mais complexas e alertas sobre consequências mais sérias
- **Regras para estruturação de código**
    1. Declare variáveis próximas de seu uso
    2. Agrupe métodos similares
    3. Declare funções de cima para baixo
    4. Mantenha poucas e curtas linhas
    5. Use espaçamentos e identação corretamente
    

### Convenções de nomenclatura

- **Notação Húngara**
    - Facilitar o reconhecimento do tipo de variável
    - Não recomendado
- **Camel Case**
    - Escrever palavras ou frases compostas considerando a primeira letra da primeira palavra sempre minúscula e as subsequentes maiúsculas
    - Ex.: valorDoDesconto, nomeCompleto
- **Pascal Case**
    - Escrever palavras ou frases compostas considerando a primeira letra de cada palavra maiúscula
    - Ex.: ValorDoDesconto, NomeCompleto
- **Qual o padrão para C#?**
    - Não há uma regra obrigatória, porém grande maioria dos desenvolvedores convenciona da seguinte forma:
        - Nomes de classes e métodos → PascalCase
        - Nomes de variáveis e parâmetros → CamelCase
    - No caso de interfaces recomenda-se o uso do prefixo “I”
        - Ex.: IEntidade, IRepositorioCliente
- **Recomendações da Microsoft**
    - Uso do PascalCase
        - Classes
        - Interfaces
        - Membros de tipos públicos
    - Uso de CamelCase
        - Campos privados e internos → deve-se ainda usá-los com prefixo “_”.
        - Campos estáticos privados ou internos → usar com prefixo “s_”.