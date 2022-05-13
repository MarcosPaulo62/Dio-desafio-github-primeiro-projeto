# O que usar? Quando usar?

### .NET x .NET Framework: Qual escolher para minha aplicação

- **Use .NET quando:**
    - Necessitar de plataforma cruzada
    - Há direcionamento de microsserviços
        - Azure Service Fabric
        - Azure App Service
    - Uso de Docker
        - Hospedagem em infraestrutura Linux ou Windows
        - Azure Kubenetes Service
    - Alto desempenho e sistemas escalonáveis
    - Necessidade de versões .NET diferentes por aplicação
- **Use .NET Framework quando:**
    - Não houver necessidade de migração para .NET
    - Bibliotecas de terceiros ou pacotes NUGET não são disponíveis para .NET
    - Necessidade de tecnologias não disponíveis para .NET
        - ASP.NET WebForms
        - ASP.NET Web Pages não estão incluídos no ASP.NET Core
        - Implementação do lado servidor para WCF
        - Workflow Foundation, Workflow Services e Workflow Data Services
    - Quando o projeto não suporta determinada linguagem para o caso de Visual Basic e F#
    
    ![Untitled](O%20que%20usar%20Quando%20usar%202cc04ef208544e70be10df55677fb821/Untitled.png)
    

### O que usar para cada tipo de aplicação

- Aplicações Desktop
    - Universal Windows Apps
    - Windows Presentation Foundation (WPF)
    - Windows Forms
    - Xamarin.MAC
- Aplicações baseadas em containers
    - AZURE: Plataforma de nuvem completa que pode hospedar aplicativos e simplificar o desenvolvimento de novos aplicativos
- Aprendizagem de máquina com .NET
    - ML.NET
        - Framework de aprendizagem de máquina de plataforma cruzada e open source
        - Criação de modelos de aprendizagem de máquina a partir de interface gráfica (Model Builder) ou por meio do ML.NET CLI
        - Integração com outros frameworks famosos como TensorFlow, ONNX, IFER.NET
- Desenvolvimento de Jogos
    - Unity, MonoGame, Godot, Stride, Wave Engine, FlatRedBall e CRYENGINE
- Internet das Coisas (IoT)
    - Bibliotecas específicas para integração de aplicações com hardware especializado como sensores, dispositivos LCD, conversores analógico-digital
    - Suportado em muitas versões  do Linux que suportam ARM/ARM64 e Windows IoT Core
    - .NET NanoFramework
        - Plataforma gratuita e open-source que permite o desenvolvimento de aplicações com C# acoplados a dispositivos
        - Meadow
            - Plataforma IoT e full-stack que permite construir soluções focadas para indústria de forma segura e escalável