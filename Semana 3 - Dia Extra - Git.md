# **Semana 3: Extra Day - Trabalhando com Git e GitHub via Linha de Comando**

### **Objetivo do Dia:**
Aprender a criar um repositório no GitHub, clonar o repositório localmente, adicionar arquivos, fazer staging, commit e push usando comandos Git.

---

### **1. Criando um Repositório no GitHub**

**Passo 1:** Acesse o [GitHub](https://github.com) e faça login na sua conta.

**Passo 2:** No canto superior direito da página, clique no ícone de `+` e selecione **New repository** (Novo repositório).

**Passo 3:** Na página de criação do repositório:
   - **Repository name (Nome do repositório):** Digite um nome para o seu projeto, como `meu-projeto-nodejs`.
   - **Description (Descrição):** Opcionalmente, adicione uma breve descrição do projeto.
   - **Public:** Certifique-se de que a opção "Public" esteja marcada para que o repositório seja visível para todos.
   - **Add a README file:** Marque esta opção para criar um arquivo README automaticamente.

**Passo 4:** Clique no botão **Create repository** (Criar repositório) para finalizar.

---

### **2. Clonando o Repositório para seu Computador**

**Passo 1:** Após criar o repositório, você verá uma página com a URL do repositório. Copie essa URL.

**Passo 2:** Abra o terminal no seu computador.

**Passo 3:** Navegue até o diretório onde você deseja clonar o repositório. Por exemplo, para ir para a pasta `projetos`, digite:
```bash
cd ~/projetos
```

**Passo 4:** Use o comando `git clone` seguido da URL do repositório que você copiou:
```bash
git clone https://github.com/seu-usuario/meu-projeto-nodejs.git
```

**Passo 5:** Após o clone, navegue até a pasta do projeto clonado:
```bash
cd meu-projeto-nodejs
```

---

### **3. Adicionando Arquivos ao Projeto**

**Passo 1:** No terminal, crie um novo arquivo dentro do projeto clonado. Por exemplo, um arquivo `index.js`:
```bash
echo "// Arquivo inicial" > index.js
```

**Passo 2:** Verifique o status do repositório para ver quais arquivos foram adicionados ou modificados:
```bash
git status
```

**Passo 3:** Você verá que o arquivo `index.js` está na lista de arquivos não monitorados (untracked files).

---

### **4. Fazendo Staging e Commit das Mudanças**

**Passo 1:** Adicione o arquivo `index.js` ao staging area para incluí-lo no próximo commit:
```bash
git add index.js
```

**Passo 2:** Verifique novamente o status do repositório:
```bash
git status
```

**Passo 3:** Agora, o arquivo `index.js` estará na lista de arquivos preparados para o commit (staged).

**Passo 4:** Faça o commit das mudanças com uma mensagem descritiva:
```bash
git commit -m "Adiciona arquivo inicial index.js"
```

---

### **5. Enviando as Mudanças para o GitHub (Push)**

**Passo 1:** Após fazer o commit, envie as mudanças para o repositório remoto no GitHub:
```bash
git push origin main
```

**Explicação:**
- **`origin`**: Refere-se ao repositório remoto que você clonou.
- **`main`**: Refere-se ao branch principal onde as mudanças serão aplicadas.

**Passo 2:** Verifique no GitHub se o arquivo `index.js` foi adicionado ao seu repositório.

---

### **6. Resumo dos Comandos Usados**

Aqui está um resumo dos comandos que você aprendeu:

1. **Clonar um repositório:**
   ```bash
   git clone <URL-do-repositório>
   ```

2. **Adicionar arquivos ao staging area:**
   ```bash
   git add <nome-do-arquivo>
   ```

3. **Fazer commit das mudanças:**
   ```bash
   git commit -m "Mensagem do commit"
   ```

4. **Enviar (push) as mudanças para o GitHub:**
   ```bash
   git push origin main
   ```

---

### **Conclusão**

Com esses passos, você aprendeu a criar um repositório no GitHub, clonar o repositório localmente, adicionar arquivos, fazer staging, commit e push usando a linha de comando. Esses são os fundamentos básicos do Git e GitHub, ferramentas essenciais para qualquer desenvolvedor.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ4MTYxMzIxXX0=
-->