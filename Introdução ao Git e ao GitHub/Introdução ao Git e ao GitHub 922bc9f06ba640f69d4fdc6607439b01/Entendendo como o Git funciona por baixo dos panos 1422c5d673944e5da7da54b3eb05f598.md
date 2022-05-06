# Entendendo como o Git funciona por baixo dos panos

### Tópicos fundamentais para entender o funcionamento do Git

- **Objetos fundamentais**
- **Sistema distribuído**
- **Segurança**
- **SHA1**
    - A sigla SHA significa Secure hash Algorithm (Algoritmo de Hash Seguro), é um conjunto de funções hash criptográficas projetadas pela NSA (Agência de Segurança Nacional dos EUA)
    - A encriptação gera conjunto de caracteres identificador de 40 dígitos
    
    ![Untitled](Entendendo%20como%20o%20Git%20funciona%20por%20baixo%20dos%20panos%201422c5d673944e5da7da54b3eb05f598/Untitled.png)
    

### Objetos internos do Git

- **BLOBS**
    - Bolhas
    - Mesmo conteúdo, porém o git guarda esse conteúdo diferente:
        
        ![Untitled](Entendendo%20como%20o%20Git%20funciona%20por%20baixo%20dos%20panos%201422c5d673944e5da7da54b3eb05f598/Untitled%201.png)
        
    - O git guarda assim:
        
        ![Untitled](Entendendo%20como%20o%20Git%20funciona%20por%20baixo%20dos%20panos%201422c5d673944e5da7da54b3eb05f598/Untitled%202.png)
        
    - Logo:
        
        ![Untitled](Entendendo%20como%20o%20Git%20funciona%20por%20baixo%20dos%20panos%201422c5d673944e5da7da54b3eb05f598/Untitled%203.png)
        

- **TREES**
    - Árvores
    - Armazenam Blobs
    - Guarda o nome dos arquivos
    - Pode conter outras árvores
        
        ![Untitled](Entendendo%20como%20o%20Git%20funciona%20por%20baixo%20dos%20panos%201422c5d673944e5da7da54b3eb05f598/Untitled%204.png)
        
        ![Untitled](Entendendo%20como%20o%20Git%20funciona%20por%20baixo%20dos%20panos%201422c5d673944e5da7da54b3eb05f598/Untitled%205.png)
        
- **COMMIT**
    - Aponta para uma árvore
    - Aponta para um parente (commit realizado anteriormente)
    - Aponta para um autor
    - Aponta para uma mensagem
    - Leva um timestamp (data, hora que foi criado)
    - Tem um SHA próprio
        
        ![Untitled](Entendendo%20como%20o%20Git%20funciona%20por%20baixo%20dos%20panos%201422c5d673944e5da7da54b3eb05f598/Untitled%206.png)
        
    

### Chave SSH e Token

Configurações de autenticação via terminal