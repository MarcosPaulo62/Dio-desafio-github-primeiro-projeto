# O que são propriedades e eventos

### Conhecendo sobre propriedades e eventos em orientação a objetos

### Propriedades

- Uma forma mais inteligente de fazer implementações de campos em classes são as propriedades.
- Propriedades consistem em um par de métodos “get” e “set” que respectivamente servem para recuperar e atribuir o valor a um campo.
- Geralmente, para cada método existe uma variável dentro da classe que armazena o valor da propriedade.

### Eventos

- São mensagens que a classe dispara em determinada situação. Para que o evento funcione, é necessário que um método seja escrito para ser executado quando ocorrer o evento. A classe apenas fica sabendo que existe esse método em tempo de execução.
- Para que o mecanismo dos eventos funcione, é necessário usar um tipo de estrutura chamado **Delegate,** uma variável que guarda o endereço de uma função. Assim, quando o evento é disparado, essa variável chama a função associada a ela.