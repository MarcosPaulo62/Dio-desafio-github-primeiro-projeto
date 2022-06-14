# Protocolo de comunicação Web HTTP

### Como funciona o protocolo HTTP?

- **HyperText Transfer Protocol (HTTP)**
- Definido pelos RFCs 1945 e 2116
- Protocolo de comunicação
- Browser → implementa o cliente HTTP
- Servidor → host objetos web
- **Arquitetura Client-server**
- Cliente
    - Mensagens - Request HTTP
- Servidor
    - Mensagens - Response HTTP
- **Stateless** - um não guarda o estado do outro
- Mensagens HTTP
    - **Tipos:**
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled.png)
    
    - **GET** → Solicitando informação ou conteúdo
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%201.png)
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%202.png)
    
    - **POST →** Submissão de conteúdo
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%203.png)
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%204.png)
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%205.png)
    
- **Formato de estruturação de dados nas Mensagens HTTP**
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%206.png)
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%207.png)
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%208.png)
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%209.png)
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2010.png)
    
    - Por qual optar? Depende.
    

### Mensagens HTTP - Request & Response

### Mensagem HTTP - Request

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2011.png)

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2012.png)

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2013.png)

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2014.png)

- **Métodos seguros -** somente leitura, não modificam o servidor

### **Mensagem HTTP - Response**

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2015.png)

- **Status Line**
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2016.png)
    
    - Alguns **Status code**
        
        ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2017.png)
        
        ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2018.png)
        
- **Header lines**
    
    ![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2019.png)
    
- **Entity**
    - Requestor Method & Status Code

### Para que serve os Cookies e Cache

### **O que são Cookies?**

- Pequenos pedaços ou blocos de dados criados e utilizados pelo servidor para persistir dados no dispositivo do cliente
- Ficam no Header file

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2020.png)

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2021.png)

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2022.png)

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2023.png)

![Untitled](Protocolo%20de%20comunicac%CC%A7a%CC%83o%20Web%20HTTP%2052e05bc398784e7ebfd1a07726d570c7/Untitled%2024.png)

- **Cookies de sessão:** são apagados após o fim da sessão
- **Cookies persistentes:** não são apagados
- Exemplos de usos de Cookies:
    - Manter logins ativos
    - Informação de website
    - Carrinho de ecommerce

### **Cache**

- **Web Cache → Proxy Server**
- Intermediário entre o **Cliente** e o **HTTP Server**
- **Cliente** faz uma requisição ao **Proxy Server**, ele verifica se tem as informações e se tiver envia ao **Cliente**
- Se não tem as informações ou as informações existentes tiverem data antiga o **Proxy Server** faz uma requisição ao **HTTP Server**, recebe as informações, atualiza sua base e depois envia para o **Cliente**
- Vantagens:
    - Redução de tempo de resposta, geralmente Proxy está num caminho mais curto
    - Redução do tráfego
    - Redução de banda

### HTTP 2.0 - Atualizações do protocolo

- Única conexão persistente
- Compressão de header
- Server push
- HTTPS por padrão - TLS
- Negociação no handshake

### Servidores/Sistemas de aplicação

- HTTP Servers
- Alguns exemplos:
    - Apache
    - XAMPP
    - NGINX