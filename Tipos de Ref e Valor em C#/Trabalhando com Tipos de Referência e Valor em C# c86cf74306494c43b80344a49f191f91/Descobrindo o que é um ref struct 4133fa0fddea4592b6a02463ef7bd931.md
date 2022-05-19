# Descobrindo o que é um ref struct

### Teoria Sobre os Conceitos de Ref e Struct

- “ref struct” serve para assegurar que a struct ficará na stack e nunca irá para a Heap
- **ref struct não pode:**
    - ser elemento tipado de um array
    - ser o tipo em campo em uma classe ou não ref struct
    - implementar interfaces
    - ser convertida para Object e nem para Value Type
    - ser usada em métodos assíncronos
- Então, quando usar
    - Quando for necessário garantir que a instância da struct não ira para a Heap
    - Quando for usar tipos do c# que são ref struct, como o caso do ref struct Span