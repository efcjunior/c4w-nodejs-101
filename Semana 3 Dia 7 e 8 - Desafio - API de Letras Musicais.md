# **Semana 3: Desafio - API de Letras Musicais**

### **Objetivo do Desafio:**
Criar uma API RESTful que gerencie letras de músicas, permitindo as operações de criação, leitura, atualização e exclusão (CRUD). A API deve armazenar as letras em um arquivo JSON, assim como foi feito na API de Tarefas (ToDo List).

---

### **Roteiro do Desafio**

#### **1. Estrutura Básica do Projeto**

**Passo 1:** Crie uma nova pasta chamada `desafio-letras-musicais` para organizar o projeto.

**Passo 2:** Dentro da pasta `desafio-letras-musicais`, inicialize um novo projeto Node.js com o comando:
```bash
npm init -y
```

**Passo 3:** Crie um arquivo chamado `letras.json` dentro da pasta `desafio-letras-musicais`. Este arquivo começará vazio, com um array:
```json
[]
```

**Passo 4:** Crie um arquivo chamado `api.js` que conterá a lógica da API.

---

#### **2. Implementando a API de Letras Musicais**

**Passo 1:** No arquivo `api.js`, configure o servidor HTTP básico, importando os módulos necessários (`http` e `fs`). Configure as funções para ler e salvar as letras musicais.

```javascript
// api.js

const http = require('http');
const fs = require('fs');

// Funções para ler e salvar as letras musicais
function lerLetras() {
    // Implemente a leitura do arquivo letras.json
}

function salvarLetras(letras) {
    // Implemente a gravação no arquivo letras.json
}

// Criação do servidor HTTP
const servidor = http.createServer((req, res) => {
    res.setHeader('Content-Type', 'application/json');

    if (req.url === '/letras' && req.method === 'GET') {
        // Implementação para retornar todas as letras

    } else if (req.url === '/letras' && req.method === 'POST') {
        // Implementação para criar uma nova letra

    } else if (req.url.startsWith('/letras/') && req.method === 'PUT') {
        // Implementação para atualizar uma letra existente

    } else if (req.url.startsWith('/letras/') && req.method === 'DELETE') {
        // Implementação para deletar uma letra existente

    } else {
        res.statusCode = 404;
        res.end(JSON.stringify({ mensagem: "Rota não encontrada" }));
    }
});

// Define a porta onde o servidor vai escutar
const porta = 3000;

// Inicia o servidor
servidor.listen(porta, () => {
    console.log(`Servidor rodando em http://localhost:${porta}/`);
});
```

**Passo 2:** Preencha as funções no servidor HTTP:

- **GET `/letras`**: Retorna todas as letras de músicas armazenadas no arquivo `letras.json`.
- **POST `/letras`**: Permite criar uma nova letra de música e armazená-la no arquivo JSON.
- **PUT `/letras/:id`**: Permite atualizar uma letra de música existente com base no `id`.
- **DELETE `/letras/:id`**: Permite excluir uma letra de música existente com base no `id`.

---

#### **3. Detalhando as Funcionalidades**

**Passo 1:** Para a criação de letras musicais:

- Quando o usuário fizer um POST para `/letras`, a nova letra deve ter um `id` único, `título`, `artista`, e `letra` (o conteúdo da música). Essas informações devem ser passadas no corpo da requisição como JSON.

**Passo 2:** Para a leitura das letras:

- A rota GET `/letras` deve retornar um array com todas as letras de músicas armazenadas no arquivo `letras.json`.

**Passo 3:** Para a atualização de letras:

- A rota PUT `/letras/:id` deve permitir que o usuário atualize o `título`, `artista`, ou `letra` de uma música específica. A atualização deve ser feita com base no `id` passado na URL.

**Passo 4:** Para a exclusão de letras:

- A rota DELETE `/letras/:id` deve permitir que o usuário exclua uma letra de música com base no `id` passado na URL.

---

#### **4. Testando a API**

**Passo 1:** Teste todas as rotas da API usando o Postman ou outra ferramenta de sua escolha:

- Crie várias letras musicais usando a rota POST `/letras`.
- Verifique se a rota GET `/letras` retorna todas as letras criadas.
- Atualize uma das letras usando a rota PUT `/letras/:id`.
- Exclua uma letra usando a rota DELETE `/letras/:id`.

**Passo 2:** Verifique o arquivo `letras.json` para garantir que ele está sendo atualizado corretamente com cada operação (criação, atualização, exclusão).

---

### **Dicas Adicionais**

- **Validação Simples:** Adicione validação simples para garantir que os campos `título`, `artista`, e `letra` não estejam vazios ao criar ou atualizar uma letra.
- **Mensagens de Erro:** Retorne mensagens de erro apropriadas se o `id` de uma letra não for encontrado durante uma atualização ou exclusão.
- **Organização do Código:** Separe as funções de leitura, escrita, e manipulação de letras musicais em funções bem definidas dentro do arquivo `api.js` para manter o código organizado.

---

### **Conclusão do Desafio**

Após concluir o desafio, você terá uma API RESTful completa que gerencia letras de músicas, com todas as operações básicas de CRUD. Esse desafio reforça os conceitos aprendidos durante a semana e oferece uma experiência prática na criação de APIs usando Node.js.

Boa sorte e divirta-se criando sua API de letras musicais!
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MTMyNTY3NjBdfQ==
-->