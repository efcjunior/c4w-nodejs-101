# **Semana 3: Servidores HTTP e APIs Simples**

### **Dias 5 e 6: Projeto 2 - API de Tarefas (ToDo List)**

**Objetivo:** Criar uma API RESTful para gerenciar tarefas (criar, ler, atualizar, excluir) e armazenar os dados em um arquivo JSON.

---

### **Dia 5: Configurando a API de Tarefas**

#### **1. Configurando o Projeto**

**Passo 1:** Crie uma nova pasta dentro de `semana-03` chamada `dia-05-06` no seu repositório ou no seu computador.

**Passo 2:** Abra o terminal e navegue até a nova pasta `dia-05-06`.

**Passo 3:** Inicialize um novo projeto Node.js com o comando:
```bash
npm init -y
```

**Explicação:**
- Isso cria um arquivo `package.json` que será usado para gerenciar o projeto e suas dependências.

---

#### **2. Criando o Arquivo para Armazenar Tarefas**

**Passo 1:** Dentro da pasta `dia-05-06`, crie um arquivo chamado `tarefas.json`.

**Passo 2:** No arquivo `tarefas.json`, adicione um array vazio, pois este arquivo armazenará as tarefas:
```json
[]
```

**Explicação:**
- Este arquivo começará vazio e será preenchido com as tarefas criadas pela API.

---

#### **3. Criando a Estrutura Básica da API**

**Passo 1:** Crie um arquivo chamado `api.js` dentro da pasta `dia-05-06`.

**Passo 2:** No arquivo `api.js`, adicione o seguinte código básico para configurar o servidor HTTP:
```javascript
// api.js

const http = require('http');
const fs = require('fs');

// Função para ler as tarefas do arquivo JSON
function lerTarefas() {
    const data = fs.readFileSync('tarefas.json');
    return JSON.parse(data);
}

// Função para salvar as tarefas no arquivo JSON
function salvarTarefas(tarefas) {
    fs.writeFileSync('tarefas.json', JSON.stringify(tarefas, null, 2));
}

// Cria o servidor HTTP
const servidor = http.createServer((req, res) => {
    res.setHeader('Content-Type', 'application/json');

    if (req.url === '/tarefas' && req.method === 'GET') {
        // Lê e retorna todas as tarefas
        const tarefas = lerTarefas();
        res.statusCode = 200;
        res.end(JSON.stringify(tarefas));
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
- **`lerTarefas`**: Lê o arquivo `tarefas.json` e retorna o conteúdo como um objeto JavaScript.
- **`salvarTarefas`**: Salva o array de tarefas no arquivo `tarefas.json`.
- **Servidor HTTP**: Configura o servidor para escutar na porta 3000 e responder à rota `/tarefas` com o método GET.

**Passo 3:** Salve o arquivo.

---

#### **4. Testando a API para Listar Tarefas**

**Passo 1:** No terminal, dentro da pasta `dia-05-06`, execute o servidor com o comando:
```bash
node api.js
```

**Passo 2:** Abra o navegador ou use uma ferramenta como o Postman e vá para a URL `http://localhost:3000/tarefas`.

**Resultado esperado:**
- O servidor deve responder com um array vazio `[]` (já que não há tarefas criadas ainda).

---

### **Dia 6: Adicionando Funcionalidades à API de Tarefas**

#### **1. Adicionando Tarefas à API**

**Passo 1:** No arquivo `api.js`, vamos adicionar a funcionalidade para criar uma nova tarefa usando o método POST.

**Passo 2:** Modifique o código para incluir o seguinte:
```javascript
// api.js

const http = require('http');
const fs = require('fs');

// Função para ler as tarefas do arquivo JSON
function lerTarefas() {
    const data = fs.readFileSync('tarefas.json');
    return JSON.parse(data);
}

// Função para salvar as tarefas no arquivo JSON
function salvarTarefas(tarefas) {
    fs.writeFileSync('tarefas.json', JSON.stringify(tarefas, null, 2));
}

// Cria o servidor HTTP
const servidor = http.createServer((req, res) => {
    res.setHeader('Content-Type', 'application/json');

    if (req.url === '/tarefas' && req.method === 'GET') {
        // Lê e retorna todas as tarefas
        const tarefas = lerTarefas();
        res.statusCode = 200;
        res.end(JSON.stringify(tarefas));

    } else if (req.url === '/tarefas' && req.method === 'POST') {
        // Recebe os dados da nova tarefa e adiciona ao arquivo
        let corpo = '';
        req.on('data', (chunk) => {
            corpo += chunk.toString();
        });

        req.on('end', () => {
            const novaTarefa = JSON.parse(corpo);
            const tarefas = lerTarefas();
            tarefas.push(novaTarefa);
            salvarTarefas(tarefas);
            res.statusCode = 201; // 201 significa que algo foi criado
            res.end(JSON.stringify(novaTarefa));
        });

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
- **POST `/tarefas`**: Permite adicionar uma nova tarefa ao array de tarefas e salva no arquivo `tarefas.json`.

**Passo 3:** Salve o arquivo.

---

#### **2. Testando a Criação de Tarefas**

**Passo 1:** No terminal, execute o servidor com:
```bash
node api.js
```

**Passo 2:** Use o Postman ou uma ferramenta similar para enviar uma requisição POST para `http://localhost:3000/tarefas` com um corpo JSON, como este:
```json
{
  "id": 1,
  "titulo": "Estudar Node.js",
  "concluida": false
}
```

**Resultado esperado:**
- A nova tarefa deve ser adicionada ao arquivo `tarefas.json` e o servidor deve responder com os dados da tarefa criada.

---

#### **3. Adicionando a Funcionalidade de Atualização de Tarefas**

**Passo 1:** Vamos permitir que os usuários atualizem tarefas usando o método PUT.

**Passo 2:** Adicione o seguinte código ao `api.js`:
```javascript
// api.js

// ...

    } else if (req.url.startsWith('/tarefas/') && req.method === 'PUT') {
        // Atualiza uma tarefa existente
        const id = parseInt(req.url.split('/')[2]);
        let corpo = '';
        req.on('data', (chunk) => {
            corpo += chunk.toString();
        });

        req.on('end', () => {
            const tarefaAtualizada = JSON.parse(corpo);
            let tarefas = lerTarefas();
            tarefas = tarefas.map(tarefa => tarefa.id === id ? tarefaAtualizada : tarefa);
            salvarTarefas(tarefas);
            res.statusCode = 200;
            res.end(JSON.stringify(tarefaAtualizada));
        });

    } else {
        res.statusCode = 404;
        res.end(JSON.stringify({ mensagem: "Rota não encontrada" }));
    }
});

// ...
```

**Explicação:**
- **PUT `/tarefas/:id`**: Permite atualizar uma tarefa existente baseada no `id`.

**Passo 3:** Salve o arquivo.

---

#### **4. Testando a Atualização de Tarefas**

**Passo 1:** No terminal, execute o servidor com:
```bash
node api.js
```

**Passo 2:** Use o Postman para enviar uma requisição PUT para `http://localhost:3000/tarefas/1` com o corpo JSON atualizado:
```json
{
  "id": 1,
  "titulo": "Estudar Node.js e APIs",
  "concluida": true
}
```

**Resultado esperado:**
- A tarefa no `tarefas.json` deve ser atualizada com as novas informações.

---

#### **5. Adicionando a Funcionalidade de Exclusão de Tarefas**

**Passo 1:** Agora, vamos permitir que os usuários excluam tarefas usando o método DELETE.

**Passo 2:** Adicione o

 seguinte código ao `api.js`:
```javascript
// api.js

// ...

    } else if (req.url.startsWith('/tarefas/') && req.method === 'DELETE') {
        // Exclui uma tarefa existente
        const id = parseInt(req.url.split('/')[2]);
        let tarefas = lerTarefas();
        tarefas = tarefas.filter(tarefa => tarefa.id !== id);
        salvarTarefas(tarefas);
        res.statusCode = 200;
        res.end(JSON.stringify({ mensagem: "Tarefa excluída com sucesso" }));

    } else {
        res.statusCode = 404;
        res.end(JSON.stringify({ mensagem: "Rota não encontrada" }));
    }
});

// ...
```

**Explicação:**
- **DELETE `/tarefas/:id`**: Permite excluir uma tarefa existente baseada no `id`.

**Passo 3:** Salve o arquivo.

---

#### **6. Testando a Exclusão de Tarefas**

**Passo 1:** No terminal, execute o servidor com:
```bash
node api.js
```

**Passo 2:** Use o Postman para enviar uma requisição DELETE para `http://localhost:3000/tarefas/1`.

**Resultado esperado:**
- A tarefa com o `id` especificado deve ser removida do arquivo `tarefas.json`, e o servidor deve responder com uma mensagem confirmando a exclusão.

---

### **Conclusão**

Com esses passos, você criou uma API RESTful completa para gerenciar uma lista de tarefas (ToDo List). A API permite criar, ler, atualizar e excluir tarefas, armazenando os dados em um arquivo JSON. Isso oferece uma base sólida para entender como funcionam as APIs e como elas podem ser usadas para criar aplicações web interativas e dinâmicas.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMzA3NTcxOF19
-->