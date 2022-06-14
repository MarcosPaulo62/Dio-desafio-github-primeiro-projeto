# Conheça o Entity Framework e crie aplicações ASP.NET

### O que é Entity Framework

- O Entity framework é um ORM (Mapeador relacional de objeto) que permite que os desenvolvedores de .NET trabalhem com um banco de dados usando objetos .NET. Elimina a necessidade da maioria do código de acesso a dados que os desenvolvedores geralmente precisam gravar.
- O Entity Framework possui três linhas principais de utilização:
    - Database First
    - Model First
    - Code First
- **Database First**
    - Em diversos casos nos deparamos com situações em que o banco de dados foi criado antes de iniciar a aplicação. Isso é muito comum em equipes mais acostumadas com o modelo relacional do que com o modelo orientado a objetos.
    Diante desse cenário é normal optar pela utilização Database First que tem como objetivo ler o banco de dados e aplicar uma engenharia reversa carregando as classes que representarão as tabelas do banco de dados.
- **Model First**
    - O Model First nos permite gerar primeiro um modelo e a partir dele gerar nossa base de dados
    Essa montagem de modelo é feita através do EDM Designer utilizando os componentes que ele nos disponibiliza sendo as mais comuns “Entity” e “Association”.
- **Code First**
    - Na abordagem Code First você cria primeiro as suas classes de entidade e deixa para o Entity Framework a responsabilidade de criar o banco de dados.
    Essas classes são conhecidas como classes POCO (Plan Old CLR Objects) que são classes que utilizam apenas os tipos do .NET Framework sendo independente de qualquer outro framework inclusive do “Entity”, essas classes podem ser utilizadas por outros projetos que utilizem ou não o Entity Framework.

### Data Annotations

- O Data Annotations é um recurso que permite que você adicione atributos e métodos em nossas classes para alterar convenções padrão e personalizar alguns comportamentos.
- Principais Atributos
    - **Required**: Significa campo obrigatório
    - **RegularExpression**: Valida o campo por expressão regular
    - **Display**: Nome a ser mostrado em todas as interfaces de usuário
    - **StringLength**: Determina a quantidade máxima de caracteres que poderá ser informada
    - **MinLength**: Determina a quantidade mínima de caracteres que poderá ser informada
    - **DisplayFormat:** Formato a ser exibido nas interfaces de usuário
    - **Range**: Define a faixa de dados aceita pela propriedade

### Migrations

- O Migrations é um recurso que oferece uma maneira de atualizar de forma incremental o esquema de banco de dados para manter em sincronia com o modelo de classe do seu projeto preservando os dados existentes no banco de dados.
Com o Migrations também é possível realizar o downgrade caso você deseje voltar o seu banco de dados para a versão anterior em que se encontrava, além de manter um histórico de alterações.

### Introdução ao ASP .NET MVC

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%201.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%202.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%203.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%204.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%205.png)

## Routes

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%206.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%207.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%208.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%209.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2010.png)

## Action Results

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2011.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2012.png)

## HTTP Verbs

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2013.png)

## Razor

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2014.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2015.png)

## Middlewares

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2016.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2017.png)

## Startup.cs

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2018.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2019.png)

![Untitled](Conhec%CC%A7a%20o%20Entity%20Framework%20e%20crie%20aplicac%CC%A7o%CC%83es%20AS%2033ecc5b2e8f549a6b44e1a15655b6209/Untitled%2020.png)