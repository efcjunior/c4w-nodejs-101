<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Semana 2 - Dia 1 e 2</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><hr>
<h1 id="semana-2-trabalhando-com-módulos-e-npm"><strong>Semana 2: Trabalhando com Módulos e NPM</strong></h1>
<h3 id="dia-1-módulos-em-node.js---parte-1"><strong>Dia 1: Módulos em Node.js - Parte 1</strong></h3>
<p><strong>Objetivo do Dia:</strong> Aprender o que são módulos em Node.js, como criar módulos e como importá-los em seu código.</p>
<hr>
<h3 id="o-que-são-módulos">1. <strong>O que são Módulos?</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>Em programação, módulos são como pequenos pedaços de código que podem ser reutilizados em diferentes partes do seu programa. Isso ajuda a manter o código organizado e fácil de entender.</li>
<li>Em Node.js, você pode dividir seu código em vários arquivos, e cada arquivo pode ser considerado um módulo. Assim, cada módulo pode fazer uma coisa específica, como uma função ou uma tarefa.</li>
</ul>
<hr>
<h3 id="criando-o-primeiro-módulo">2. <strong>Criando o Primeiro Módulo</strong></h3>
<p><strong>Passo 1:</strong> Crie uma nova pasta dentro de <code>semana-02</code> chamada <code>dia-01-02</code> no seu repositório no GitHub ou no seu computador.</p>
<p><strong>Passo 2:</strong> Dentro da pasta <code>dia-01-02</code>, crie dois arquivos: <code>app.js</code> e <code>saudacao.js</code>.</p>
<p><strong>Passo 3:</strong> No arquivo <code>saudacao.js</code>, vamos criar uma função simples que será exportada para ser usada em outro arquivo. Adicione o seguinte código:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// saudacao.js</span>

<span class="token keyword">function</span> <span class="token function">saudar</span><span class="token punctuation">(</span>nome<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token template-string"><span class="token string">`Olá, </span><span class="token interpolation"><span class="token interpolation-punctuation punctuation">${</span>nome<span class="token interpolation-punctuation punctuation">}</span></span><span class="token string">! Seja bem-vindo(a)!`</span></span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

module<span class="token punctuation">.</span>exports <span class="token operator">=</span> saudar<span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>function saudar(nome)</code></strong>: Esta é uma função que recebe um nome como entrada e retorna uma mensagem de saudação.</li>
<li><strong><code>module.exports = saudar;</code></strong>: Este comando exporta a função <code>saudar</code> para que ela possa ser usada em outros arquivos.</li>
</ul>
<hr>
<h3 id="importando-e-usando-o-módulo">3. <strong>Importando e Usando o Módulo</strong></h3>
<p><strong>Passo 1:</strong> No arquivo <code>app.js</code>, vamos importar a função <code>saudar</code> que criamos no módulo <code>saudacao.js</code> e usá-la para saudar alguém.</p>
<p><strong>Passo 2:</strong> Adicione o seguinte código no arquivo <code>app.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// app.js</span>

<span class="token keyword">const</span> saudar <span class="token operator">=</span> <span class="token function">require</span><span class="token punctuation">(</span><span class="token string">'./saudacao'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">const</span> nome <span class="token operator">=</span> <span class="token string">"Lucas"</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token function">saudar</span><span class="token punctuation">(</span>nome<span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>const saudar = require('./saudacao');</code></strong>: Aqui, estamos importando a função <code>saudar</code> do arquivo <code>saudacao.js</code> usando o comando <code>require</code>.</li>
<li><strong><code>console.log(saudar(nome));</code></strong>: Chamamos a função <code>saudar</code> e passamos o nome “Lucas” para ela. O resultado será mostrado no terminal.</li>
</ul>
<hr>
<h3 id="executando-o-código">4. <strong>Executando o Código</strong></h3>
<p><strong>Passo 1:</strong> Abra o terminal e navegue até a pasta <code>dia-01-02</code> onde os arquivos <code>app.js</code> e <code>saudacao.js</code> estão localizados.</p>
<p><strong>Passo 2:</strong> Execute o arquivo <code>app.js</code> usando o seguinte comando:</p>
<pre class=" language-bash"><code class="prism  language-bash">node app.js
</code></pre>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar a mensagem:</p>
<pre><code>Olá, Lucas! Seja bem-vindo(a)!
</code></pre>
<hr>
<h3 id="dia-2-módulos-em-node.js---parte-2"><strong>Dia 2: Módulos em Node.js - Parte 2</strong></h3>
<p><strong>Objetivo do Dia:</strong> Aprender a organizar o código em múltiplos arquivos e entender melhor como os módulos podem ser usados para manter o projeto organizado.</p>
<hr>
<h3 id="organizando-o-código-em-múltiplos-arquivos">1. <strong>Organizando o Código em Múltiplos Arquivos</strong></h3>
<p><strong>Passo 1:</strong> Dentro da pasta <code>dia-01-02</code>, crie mais dois arquivos: <code>calculadora.js</code> e <code>operacoes.js</code>.</p>
<p><strong>Passo 2:</strong> No arquivo <code>operacoes.js</code>, vamos criar duas funções, uma para somar e outra para subtrair números:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// operacoes.js</span>

<span class="token keyword">function</span> <span class="token function">somar</span><span class="token punctuation">(</span>a<span class="token punctuation">,</span> b<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> a <span class="token operator">+</span> b<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">function</span> <span class="token function">subtrair</span><span class="token punctuation">(</span>a<span class="token punctuation">,</span> b<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> a <span class="token operator">-</span> b<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

module<span class="token punctuation">.</span>exports <span class="token operator">=</span> <span class="token punctuation">{</span>
    somar<span class="token punctuation">,</span>
    subtrair
<span class="token punctuation">}</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong>Funções <code>somar</code> e <code>subtrair</code>:</strong> Essas funções recebem dois números e retornam o resultado da soma ou subtração.</li>
<li><strong><code>module.exports = { somar, subtrair };</code></strong>: Exportamos as duas funções como um objeto, o que nos permite importá-las e usá-las em outros arquivos.</li>
</ul>
<hr>
<h3 id="usando-os-módulos-na-calculadora">2. <strong>Usando os Módulos na Calculadora</strong></h3>
<p><strong>Passo 1:</strong> No arquivo <code>calculadora.js</code>, vamos importar as funções de <code>operacoes.js</code> e usá-las para criar uma simples calculadora.</p>
<p><strong>Passo 2:</strong> Adicione o seguinte código no arquivo <code>calculadora.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// calculadora.js</span>

<span class="token keyword">const</span> operacoes <span class="token operator">=</span> <span class="token function">require</span><span class="token punctuation">(</span><span class="token string">'./operacoes'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">const</span> numero1 <span class="token operator">=</span> <span class="token number">10</span><span class="token punctuation">;</span>
<span class="token keyword">const</span> numero2 <span class="token operator">=</span> <span class="token number">5</span><span class="token punctuation">;</span>

console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token template-string"><span class="token string">`A soma de </span><span class="token interpolation"><span class="token interpolation-punctuation punctuation">${</span>numero1<span class="token interpolation-punctuation punctuation">}</span></span><span class="token string"> e </span><span class="token interpolation"><span class="token interpolation-punctuation punctuation">${</span>numero2<span class="token interpolation-punctuation punctuation">}</span></span><span class="token string"> é:`</span></span><span class="token punctuation">,</span> operacoes<span class="token punctuation">.</span><span class="token function">somar</span><span class="token punctuation">(</span>numero1<span class="token punctuation">,</span> numero2<span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token template-string"><span class="token string">`A subtração de </span><span class="token interpolation"><span class="token interpolation-punctuation punctuation">${</span>numero1<span class="token interpolation-punctuation punctuation">}</span></span><span class="token string"> e </span><span class="token interpolation"><span class="token interpolation-punctuation punctuation">${</span>numero2<span class="token interpolation-punctuation punctuation">}</span></span><span class="token string"> é:`</span></span><span class="token punctuation">,</span> operacoes<span class="token punctuation">.</span><span class="token function">subtrair</span><span class="token punctuation">(</span>numero1<span class="token punctuation">,</span> numero2<span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>const operacoes = require('./operacoes');</code></strong>: Importamos o módulo <code>operacoes</code>, que contém as funções de soma e subtração.</li>
<li><strong><code>operacoes.somar(numero1, numero2)</code></strong>: Chamamos a função de soma com dois números e mostramos o resultado no terminal.</li>
<li><strong><code>operacoes.subtrair(numero1, numero2)</code></strong>: Chamamos a função de subtração com dois números e mostramos o resultado no terminal.</li>
</ul>
<hr>
<h3 id="executando-a-calculadora">3. <strong>Executando a Calculadora</strong></h3>
<p><strong>Passo 1:</strong> Abra o terminal e navegue até a pasta <code>dia-01-02</code>.</p>
<p><strong>Passo 2:</strong> Execute o arquivo <code>calculadora.js</code> usando o comando:</p>
<pre class=" language-bash"><code class="prism  language-bash">node calculadora.js
</code></pre>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar:</p>
<pre><code>A soma de 10 e 5 é: 15
A subtração de 10 e 5 é: 5
</code></pre>
<hr>
<h3 id="conclusão"><strong>Conclusão</strong></h3>
<p>Com esses passos, você aprendeu como criar e usar módulos em Node.js, dividindo seu código em vários arquivos para mantê-lo organizado e fácil de gerenciar. Agora você pode reutilizar esses módulos em diferentes partes do seu projeto, tornando o desenvolvimento mais eficiente e organizado.</p>
</div>
</body>

</html>
