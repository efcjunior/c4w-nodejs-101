---

# **Semana 2: Trabalhando com Módulos e NPM**

### **Dia 1: Módulos em Node.js - Parte 1**

**Objetivo do Dia:** Aprender o que são módulos em Node.js, como criar módulos e como importá-los em seu código.

---

### 1. **O que são Módulos?**

**Explicação Simples:**
- Em programação, módulos são como pequenos pedaços de código que podem ser reutilizados em diferentes partes do seu programa. Isso ajuda a manter o código organizado e fácil de entender.
- Em Node.js, você pode dividir seu código em vários arquivos, e cada arquivo pode ser considerado um módulo. Assim, cada módulo pode fazer uma coisa específica, como uma função ou uma tarefa.

---

### 2. **Criando o Primeiro Módulo**

**Passo 1:** Crie uma nova pasta dentro de `semana-02` chamada `dia-01-02` no seu repositório no GitHub ou no seu computador.

**Passo 2:** Dentro da pasta `dia-01-02`, crie dois arquivos: `app.js` e `saudacao.js`.

**Passo 3:** No arquivo `saudacao.js`, vamos criar uma função simples que será exportada para ser usada em outro arquivo. Adicione o seguinte código:
```javascript
// saudacao.js

function saudar(nome) {
    return `Olá, ${nome}! Seja bem-vindo(a)!`;
}

module.exports = saudar;
```

**Explicação:**
- **`function saudar(nome)`**: Esta é uma função que recebe um nome como entrada e retorna uma mensagem de saudação.
- **`module.exports = saudar;`**: Este comando exporta a função `saudar` para que ela possa ser usada em outros arquivos.

---

### 3. **Importando e Usando o Módulo**

**Passo 1:** No arquivo `app.js`, vamos importar a função `saudar` que criamos no módulo `saudacao.js` e usá-la para saudar alguém.

**Passo 2:** Adicione o seguinte código no arquivo `app.js`:
```javascript
// app.js

const saudar = require('./saudacao');

const nome = "Lucas";
console.log(saudar(nome));
```

**Explicação:**
- **`const saudar = require('./saudacao');`**: Aqui, estamos importando a função `saudar` do arquivo `saudacao.js` usando o comando `require`.
- **`console.log(saudar(nome));`**: Chamamos a função `saudar` e passamos o nome "Lucas" para ela. O resultado será mostrado no terminal.

---

### 4. **Executando o Código**

**Passo 1:** Abra o terminal e navegue até a pasta `dia-01-02` onde os arquivos `app.js` e `saudacao.js` estão localizados.

**Passo 2:** Execute o arquivo `app.js` usando o seguinte comando:
```bash
node app.js
```

**Resultado esperado:**
O terminal deve mostrar a mensagem:
```
Olá, Lucas! Seja bem-vindo(a)!
```

---

### **Dia 2: Módulos em Node.js - Parte 2**

**Objetivo do Dia:** Aprender a organizar o código em múltiplos arquivos e entender melhor como os módulos podem ser usados para manter o projeto organizado.

---

### 1. **Organizando o Código em Múltiplos Arquivos**

**Passo 1:** Dentro da pasta `dia-01-02`, crie mais dois arquivos: `calculadora.js` e `operacoes.js`.

**Passo 2:** No arquivo `operacoes.js`, vamos criar duas funções, uma para somar e outra para subtrair números:
```javascript
// operacoes.js

function somar(a, b) {
    return a + b;
}

function subtrair(a, b) {
    return a - b;
}

module.exports = {
    somar,
    subtrair
};
```

**Explicação:**
- **Funções `somar` e `subtrair`:** Essas funções recebem dois números e retornam o resultado da soma ou subtração.
- **`module.exports = { somar, subtrair };`**: Exportamos as duas funções como um objeto, o que nos permite importá-las e usá-las em outros arquivos.

---

### 2. **Usando os Módulos na Calculadora**

**Passo 1:** No arquivo `calculadora.js`, vamos importar as funções de `operacoes.js` e usá-las para criar uma simples calculadora.

**Passo 2:** Adicione o seguinte código no arquivo `calculadora.js`:
```javascript
// calculadora.js

const operacoes = require('./operacoes');

const numero1 = 10;
const numero2 = 5;

console.log(`A soma de ${numero1} e ${numero2} é:`, operacoes.somar(numero1, numero2));
console.log(`A subtração de ${numero1} e ${numero2} é:`, operacoes.subtrair(numero1, numero2));
```

**Explicação:**
- **`const operacoes = require('./operacoes');`**: Importamos o módulo `operacoes`, que contém as funções de soma e subtração.
- **`operacoes.somar(numero1, numero2)`**: Chamamos a função de soma com dois números e mostramos o resultado no terminal.
- **`operacoes.subtrair(numero1, numero2)`**: Chamamos a função de subtração com dois números e mostramos o resultado no terminal.

---

### 3. **Executando a Calculadora**

**Passo 1:** Abra o terminal e navegue até a pasta `dia-01-02`.

**Passo 2:** Execute o arquivo `calculadora.js` usando o comando:
```bash
node calculadora.js
```

**Resultado esperado:**
O terminal deve mostrar:
```
A soma de 10 e 5 é: 15
A subtração de 10 e 5 é: 5
```

---

### **Conclusão**

Com esses passos, você aprendeu como criar e usar módulos em Node.js, dividindo seu código em vários arquivos para mantê-lo organizado e fácil de gerenciar. Agora você pode reutilizar esses módulos em diferentes partes do seu projeto, tornando o desenvolvimento mais eficiente e organizado.
