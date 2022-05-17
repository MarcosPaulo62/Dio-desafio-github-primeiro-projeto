# Conhecendo o C#

### O que é e como funciona o C#

- **O que é C#?**
    - C# é uma linguagem elegante, orientada a objeto e fortemente tipada
    - A sintaxe do C# é similar a do C, C++ ou Java
    - Suporta os conceitos de encapsulamento, herança e polimorfismo (OO)
    - Os programas C# são executados no .NET, que inclui:
        - CLR (Common Language Runtime)
        - Conjunto unificado de bibliotecas de classes
    - Atualmente o compilador do C# é o Roslyn
- **Como funciona?**
    - O código-fonte escrito em C# é compilado em uma linguagem intermediária (IL)
    - O código e os recursos de IL são armazenados no disco em um arquivo executável chamado assembly, geralmente com uma extensão .exe ou .dll
    - Quando o programa C# é executado, o assembly é carregado no CLR
    - Em seguida o CLR executará a compilação just in time (JIT) para converter o código IL em instruções de máquina nativas
    - O CLR também fornece outros serviços:
        - Garbage Collector
        - Exception Handles
        - Resources Manager
    - Além dos serviços de tempo de execução, o .NET também inclui uma extensa biblioteca com milhares de classes que fornecem uma ampla variedade de funcionalidades úteis, desde entrada e saída de arquivos, manipulação de cadeias de caracteres, análise XML, etc
    

### Estrutura de programa

- Os principais conceitos organizacionais em C# são:
    - programas
    - namespaces
    - tipos
    - membros
    - assemblies
- Programas C# consistem em um ou mais arquivos
- Os programas declaram tipos, que contêm membros e podem ser organizados em namespaces
- Classes e interfaces são exemplos de tipos
- Campos, métodos, propriedades e eventos são exemplos de membros
- Quando os programas C# são compilados, eles são fisicamente empacotados em assemblies que geralmente têm extensão .exe ou .dll