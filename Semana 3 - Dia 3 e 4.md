# **Semana 3: Servidores HTTP e APIs Simples**

### **Dia 3: Criando uma API Simples que Retorna JSON**

**Objetivo do Dia:** Aprender a criar uma API simples que responde com dados em formato JSON usando Node.js.

---

### 1. **O que é uma API?**

**Explicação Simples:**
- **API** (Interface de Programação de Aplicações) é uma forma de permitir que diferentes programas se comuniquem entre si. Quando você cria uma API, está criando um conjunto de regras que outros programas podem usar para interagir com o seu aplicativo.
- Uma API que usa o protocolo HTTP permite que os dados sejam enviados e recebidos através da internet.

---

### 2. **Configurando o Projeto**

**Passo 1:** Crie uma nova pasta dentro de `semana-03` chamada `dia-03-04` no seu repositório ou no seu computador.

**Passo 2:** Abra o terminal e navegue até a nova pasta `dia-03-04`.

**Passo 3:** Inicialize um novo projeto Node.js com o comando:
```bash
npm init -y
```

**Explicação:**
- Isso cria um arquivo `package.json` que será usado para gerenciar o projeto.

---

### 3. **Criando uma API Simples**

**Passo 1:** Crie um arquivo chamado `api.js` dentro da pasta `dia-03-04`.

**Passo 2:** No arquivo `api.js`, vamos começar criando um servidor HTTP que responde com dados em formato JSON.

**Passo 3:** Adicione o seguinte código:
```javascript
// api.js

const http = require('http');

// Dados de exemplo que serão retornados pela API
const dados = {
    nome: "Lucas",
    idade: 25,
    cidade: "São Paulo"
};

// Cria um servidor que responde com dados em formato JSON
const servidor = http.createServer((req, res) => {
    res.statusCode = 200; // Define o status da resposta como 200 (OK)
    res.setHeader('Content-Type', 'application/json'); // Define o tipo de conteúdo como JSON
    res.end(JSON.stringify(dados)); // Converte o objeto 'dados' para JSON e envia como resposta
});

// Define a porta onde o servidor vai escutar (porta 3000)
const porta = 3000;

// Inicia o servidor
servidor.listen(porta, () => {
    console.log(`Servidor rodando em http://localhost:${porta}/`);
});
```

**Explicação:**
- **`Content-Type: application/json`**: Define que o conteúdo da resposta é JSON.
- **`JSON.stringify(dados)`**: Converte o objeto `dados` em uma string JSON para que possa ser enviado na resposta.

**Passo 4:** Salve o arquivo.

---

### 4. **Executando a API**

**Passo 1:** No terminal, dentro da pasta `dia-03-04`, execute o servidor com o comando:
```bash
node api.js
```

**Passo 2:** Abra o navegador e vá para a URL `http://localhost:3000/`.

**Resultado esperado:**
Você deve ver os dados em formato JSON, algo como:
```json
{
  "nome": "Lucas",
  "idade": 25,
  "cidade": "São Paulo"
}
```

---

### **Dia 4: Introdução ao Conceito de Rotas e Métodos HTTP**

**Objetivo do Dia:** Aprender sobre rotas e métodos HTTP e como usá-los para criar uma API mais complexa.

---

### 1. **O que são Rotas e Métodos HTTP?**

**Explicação Simples:**
- **Rotas** são caminhos que levam a diferentes partes da API. Por exemplo, você pode ter uma rota para retornar informações de um usuário (`/usuario`) e outra para retornar informações de produtos (`/produtos`).
- **Métodos HTTP** são diferentes tipos de requisições que você pode fazer para a API. Os mais comuns são:
  - **GET**: Para obter dados.
  - **POST**: Para enviar dados.
  - **PUT**: Para atualizar dados.
  - **DELETE**: Para deletar dados.

---

### 2. **Criando Rotas Simples na API**

**Passo 1:** No arquivo `api.js`, vamos adicionar algumas rotas para diferentes dados.

**Passo 2:** Modifique o código para ficar assim:
```javascript
// api.js

const http = require('http');

// Dados de exemplo que serão retornados pela API
const usuario = {
    nome: "Lucas",
    idade: 25,
    cidade: "São Paulo"
};

const produtos = [
    { id: 1, nome: "Produto A", preco: 10.0 },
    { id: 2, nome: "Produto B", preco: 20.0 },
    { id: 3, nome: "Produto C", preco: 30.0 }
];

// Cria um servidor que responde com diferentes dados dependendo da rota
const servidor = http.createServer((req, res) => {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'application/json');

    if (req.url === '/usuario') {
        res.end(JSON.stringify(usuario));
    } else if (req.url === '/produtos') {
        res.end(JSON.stringify(produtos));
    } else {
        res.statusCode = 404;
        res.end(JSON.stringify({ mensagem: "Rota não encontrada" }));
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
- **`req.url === '/usuario'`**: Se o usuário acessar a rota `/usuario`, o servidor responde com os dados do usuário.
- **`req.url === '/produtos'`**: Se o usuário acessar a rota `/produtos`, o servidor responde com uma lista de produtos.
- **`404`**: Se a rota não for encontrada, o servidor responde com uma mensagem de erro.

**Passo 3:** Salve o arquivo.

---

### 3. **Testando as Rotas**

**Passo 1:** No terminal, execute o servidor novamente:
```bash
node api.js
```

**Passo 2:** No navegador, teste as seguintes URLs:
- `http://localhost:3000/usuario` (deve mostrar os dados do usuário).
- `http://localhost:3000/produtos` (deve mostrar a lista de produtos).
- `http://localhost:3000/qualquercoisa` (deve mostrar a mensagem "Rota não encontrada").

**Resultado esperado:**
- Cada rota deve retornar os dados correspondentes em formato JSON.

---

### **Conclusão**

Com esses passos, você aprendeu a criar uma API simples usando Node.js, a responder com dados em formato JSON, e a usar rotas para organizar melhor sua API. Isso é essencial para entender como criar aplicações que interagem com outras partes da web ou com diferentes sistemas.
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTY0OTM0ODk5XX0=
-->