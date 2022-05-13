# Sobre .Net Framework, .Net Core e Xamarin

### **Entendendo .NET Framework**

- Ambiente de desenvolvimento e execução focado em Windows
- Possui dois componentes:
    - **Common Language runtime →** Gerenciamento de execução dos apps
    - **.NET Class Library →** Biblioteca para reutilização de códigos
- Características principais:
    - Gerenciamento de memória
    - Sistema de tipos comum → Tipos definidos pelo próprio framework
    - Grande e específicas bibliotecas de classes utilitárias Ex.: ASP.NET, ADO.NET, WCF, WPF
    - Interoperabilidade entre linguagens
    - Compatibilidade de versões
    - Uso do .NET Standard

### Entendendo .NET e .NET Core

![Untitled](Sobre%20Net%20Framework,%20Net%20Core%20e%20Xamarin%206717e362104042b8b4b5e6d3cf11fc2f/Untitled.png)

**SOBRE .NET CORE E .NET:**

- Plataforma cruzada: Linux, Windows e Mac OS
- Produzir um produto com base de código única
- Open Source → MIT e Apache 2
- **.NET =** .NET Core **+** .NET Framework **+** Xamarin **+** Mono
- Aquisição facilitada a partir do NUGET
- Modular e com melhor desempenho
- Ciclos de lançamentos mais rápidos
    
    ![Untitled](Sobre%20Net%20Framework,%20Net%20Core%20e%20Xamarin%206717e362104042b8b4b5e6d3cf11fc2f/Untitled%201.png)
    

**SOBRE ASP.NET CORE:**

- Construção de aplicações web, IoT, apps e aplicações backend para mobile
- Funcionalidades para construção de aplicações com renderização no servidor
    - **Uso do MVC → ASP.NET Core MVC**
        - Uso de Padrão MVC (Model-View-Controller)
            - **Model:** Representa o estado da aplicação, encapsulando lógica de negócio
            - **View:** Responsável por apresentar dados através de interface
            - **Controller:** Componentes que lidam com a interação do usuário a partir da View e trabalham com a model para apresentar respostas para o usuário
        - Model Binding
            - Mapeamento automático de dados de requisições HTTP para parâmetros de métodos de ação
        - Model Validation: Validação automática no lado do cliente e servidor
        - Razor Pages e Razor markup
            - Modelo baseado em páginas → simplificado
            - Interface e lógica de negócio são separados, mas dentro da página
            - Sintaxe de marcação para inserir código baseado em .NET em páginas WEB = Razor markup + C# + HTML
        - Tag Helpers
        - Permite que o código do lado do servidor participe da criação e renderização de elementos HTML em arquivos Razor
        - Experiência de desenvolvimento com HTML mais amigável
        - IntelliSense no ambiente para sintaxe HTML e Razor
        - Manutenção de código usando somente informações do servidor
- Funcionalidades para construção de aplicações com renderização no cliente
    - Blazor
        - Framework para construir aplicativos do lado do cliente, que são executados direto no navegador com WebAssembly(WASM) usando C#
        - Uso da interoperabilidade com Javascript para lidar com manioulação da DOM e chamadas de API
    - Integração com frameworks como Angular, React e Bootstrap

### Entendendo Xamarin

- Plataforma para desenvolvimento de aplicações mobile modernas com alto desempenho
- Baseado no projeto Mono, implementação open source baseada no .NET Framework
- Criação de interface nativa em cada plataforma (Android, IOS, MacOS e Windows apps) e código de lógica compartilhado
- Possui todos os benefícios já citados da plataforma .NET
- **Xamarin.Forms**
    - Framework open source para desenvolvimento de interfaces para o usuário
    - Aplicativos Android, IOS e Windows com única base de código
    - Criação de UI com XAML e lógica com C#
    - Uso da biblioteca Xamarin.Essentials
        - Informações de dispositivos
        - sistemas de arquuivos
        - acelerômetro
        - bloqueio de tela
- **Xamarin.Android**
    - Compilação de C# para LI (linguagem intermediária), que por sua vez é compilado para assembly nativo no momento da execução
    - Executado no ambiente Mono + ART
- **Xamarin.IOS**
    - Compilação total de C# para código assembly nativo
    - Executado no ambiente Mono + AOT (ahead of time)
    - Restrição de segurança: sem permissão para execução de código gerado dinamicamente