# **Semana 3: Servidores HTTP e APIs Simples**

### **Dia 1: Criando um Servidor HTTP - Parte 1**

**Objetivo do Dia:** Aprender a configurar um servidor HTTP básico usando o módulo `http` do Node.js.

---

### 1. **O que é um Servidor HTTP?**

**Explicação Simples:**
- Um servidor HTTP é como uma pessoa que recebe pedidos (requisições) e responde a eles. No nosso caso, vamos usar Node.js para criar um servidor que responde a requisições feitas através do navegador ou de outro programa.

---

### 2. **Configurando o Projeto**

**Passo 1:** Crie uma nova pasta dentro de `semana-03` chamada `dia-01-02` no seu repositório ou no seu computador.

**Passo 2:** Abra o terminal e navegue até a nova pasta `dia-01-02`.

**Passo 3:** Inicialize um novo projeto Node.js com o comando:
```bash
npm init -y
```

**Explicação:**
- Isso cria um arquivo `package.json` para o projeto, que é usado para gerenciar o projeto e suas dependências.

---

### 3. **Criando um Servidor HTTP Básico**

**Passo 1:** Crie um arquivo chamado `server.js` dentro da pasta `dia-01-02`.

**Passo 2:** No arquivo `server.js`, adicione o seguinte código para criar um servidor básico:
```javascript
// server.js

const http = require('http');

// Cria um servidor que responde a todas as requisições com "Olá, mundo!"
const servidor = http.createServer((req, res) => {
    res.statusCode = 200; // Define o status da resposta como 200 (OK)
    res.setHeader('Content-Type', 'text/plain'); // Define o tipo de conteúdo como texto simples
    res.end('Olá, mundo!\n'); // Envia a resposta "Olá, mundo!" e termina a resposta
});

// Define a porta onde o servidor vai escutar (porta 3000)
const porta = 3000;

// Inicia o servidor
servidor.listen(porta, () => {
    console.log(`Servidor rodando em http://localhost:${porta}/`);
});
```

**Explicação:**
- **`http.createServer()`**: Cria um servidor HTTP que escuta requisições e responde a elas.
- **`res.statusCode = 200;`**: Define o código de status da resposta como 200, o que significa que tudo correu bem.
- **`res.setHeader('Content-Type', 'text/plain');`**: Define o tipo de conteúdo da resposta como texto simples.
- **`res.end('Olá, mundo!\n');`**: Envia a resposta "Olá, mundo!" e encerra a resposta.

**Passo 3:** Salve o arquivo.

---

### 4. **Executando o Servidor**

**Passo 1:** No terminal, dentro da pasta `dia-01-02`, execute o servidor com o comando:
```bash
node server.js
```

**Passo 2:** Abra o navegador e vá para a URL `http://localhost:3000/`.

**Resultado esperado:**
Você deve ver a mensagem "Olá, mundo!" no navegador.

---

### **Dia 2: Respostas Simples com Texto e HTML**

**Objetivo do Dia:** Aprender a responder a requisições HTTP com texto simples e HTML usando o módulo `http` do Node.js.

---

### 1. **Respondendo com Texto Simples**

**Passo 1:** Vamos modificar o servidor para responder com diferentes tipos de texto dependendo da URL solicitada.

**Passo 2:** No arquivo `server.js`, modifique o código para ficar assim:
```javascript
// server.js

const http = require('http');

// Cria um servidor que responde com diferentes textos dependendo da URL
const servidor = http.createServer((req, res) => {
    res.statusCode = 200;

    if (req.url === '/') {
        res.setHeader('Content-Type', 'text/plain');
        res.end('Você está na página inicial!\n');
    } else if (req.url === '/sobre') {
        res.setHeader('Content-Type', 'text/plain');
        res.end('Esta é a página Sobre.\n');
    } else {
        res.statusCode = 404;
        res.setHeader('Content-Type', 'text/plain');
        res.end('Página não encontrada.\n');
    }
});

// Define a porta onde o servidor vai escutar (porta 3000)
const porta = 3000;

// Inicia o servidor
servidor.listen(porta, () => {
    console.log(`Servidor rodando em http://localhost:${porta}/`);
});
```

**Explicação:**
- **`req.url`**: Verifica a URL solicitada pelo usuário.
- **Respostas personalizadas**: Dependendo da URL, o servidor responde com diferentes mensagens de texto simples.

**Passo 3:** Salve o arquivo e execute o servidor novamente:
```bash
node server.js
```

**Passo 4:** No navegador, visite as seguintes URLs:
- `http://localhost:3000/` (deve mostrar "Você está na página inicial!")
- `http://localhost:3000/sobre` (deve mostrar "Esta é a página Sobre.")
- `http://localhost:3000/algumacoisa` (deve mostrar "Página não encontrada.")

---

### 2. **Respondendo com HTML Simples**

**Passo 1:** Vamos agora modificar o servidor para responder com conteúdo HTML.

**Passo 2:** No arquivo `server.js`, modifique o código para ficar assim:
```javascript
// server.js

const http = require('http');

// Cria um servidor que responde com conteúdo HTML
const servidor = http.createServer((req, res) => {
    res.statusCode = 200;

    if (req.url === '/') {
        res.setHeader('Content-Type', 'text/html');
        res.end('<h1>Bem-vindo à Página Inicial!</h1><p>Esta é a página principal.</p>');
    } else if (req.url === '/sobre') {
        res.setHeader('Content-Type', 'text/html');
        res.end('<h1>Sobre Nós</h1><p>Esta é a página Sobre.</p>');
    } else {
        res.statusCode = 404;
        res.setHeader('Content-Type', 'text/html');
        res.end('<h1>404 - Página não encontrada</h1><p>Desculpe, não conseguimos encontrar o que você está procurando.</p>');
    }
});

// Define a porta onde o servidor vai escutar (porta 3000)
const porta = 3000;

// Inicia o servidor
servidor.listen(porta, () => {
    console.log(`Servidor rodando em http://localhost:${porta}/`);
});
```

**Explicação:**
- **`Content-Type: text/html`**: Agora, o servidor responde com conteúdo HTML em vez de texto simples.
- **HTML no `res.end()`**: Você pode escrever código HTML diretamente no `res.end()` para criar respostas mais ricas.

**Passo 3:** Salve o arquivo e execute o servidor novamente:
```bash
node server.js
```

**Passo 4:** No navegador, visite novamente as URLs:
- `http://localhost:3000/` (deve mostrar uma página com título e parágrafo HTML).
- `http://localhost:3000/sobre` (deve mostrar uma página Sobre com HTML).
- `http://localhost:3000/algumacoisa` (deve mostrar uma página 404 personalizada com HTML).

---

### **Conclusão**

Com esses passos, você aprendeu a configurar um servidor HTTP básico em Node.js, responder a requisições com texto simples e HTML, e personalizar as respostas dependendo da URL solicitada. Isso é o começo para entender como funcionam servidores e APIs, que são fundamentais para o desenvolvimento web.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTAxMDA0ODQ0XX0=
-->