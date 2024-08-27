<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Semana 2 - Dia 3 e 4</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><hr>
<h1 id="semana-2-introdução-ao-npm"><strong>Semana 2: Introdução ao NPM</strong></h1>
<h3 id="dia-3-instalação-e-uso-de-pacotes-via-npm"><strong>Dia 3: Instalação e Uso de Pacotes via NPM</strong></h3>
<p><strong>Objetivo do Dia:</strong> Aprender o que é o NPM, como ele funciona e como instalar e usar pacotes em seus projetos.</p>
<hr>
<h3 id="o-que-é-o-npm">1. <strong>O que é o NPM?</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li><strong>NPM</strong> (Node Package Manager) é uma ferramenta que vem junto com o Node.js. Ele é usado para gerenciar pacotes, que são pequenos pedaços de código que outras pessoas escreveram e que você pode usar no seu projeto.</li>
<li>Com o NPM, você pode instalar, atualizar ou remover pacotes no seu projeto com apenas alguns comandos.</li>
</ul>
<hr>
<h3 id="inicializando-um-projeto-node.js-com-npm">2. <strong>Inicializando um Projeto Node.js com NPM</strong></h3>
<p><strong>Passo 1:</strong> Crie uma nova pasta dentro de <code>semana-02</code> chamada <code>dia-03-04</code> no seu repositório ou no seu computador.</p>
<p><strong>Passo 2:</strong> Abra o terminal e navegue até a nova pasta <code>dia-03-04</code>.</p>
<p><strong>Passo 3:</strong> No terminal, inicialize um novo projeto Node.js com o comando:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">npm</span> init -y
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li>Este comando cria um arquivo chamado <code>package.json</code> na sua pasta. Esse arquivo guarda informações sobre o seu projeto e lista os pacotes que você instalar.</li>
</ul>
<p><strong>Passo 4:</strong> Abra o arquivo <code>package.json</code> que foi criado. Você verá algo como isto:</p>
<pre class=" language-json"><code class="prism  language-json"><span class="token punctuation">{</span>
  <span class="token string">"name"</span><span class="token punctuation">:</span> <span class="token string">"dia-03-04"</span><span class="token punctuation">,</span>
  <span class="token string">"version"</span><span class="token punctuation">:</span> <span class="token string">"1.0.0"</span><span class="token punctuation">,</span>
  <span class="token string">"description"</span><span class="token punctuation">:</span> <span class="token string">""</span><span class="token punctuation">,</span>
  <span class="token string">"main"</span><span class="token punctuation">:</span> <span class="token string">"index.js"</span><span class="token punctuation">,</span>
  <span class="token string">"scripts"</span><span class="token punctuation">:</span> <span class="token punctuation">{</span>
    <span class="token string">"test"</span><span class="token punctuation">:</span> <span class="token string">"echo \"Error: no test specified\" &amp;&amp; exit 1"</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token string">"author"</span><span class="token punctuation">:</span> <span class="token string">""</span><span class="token punctuation">,</span>
  <span class="token string">"license"</span><span class="token punctuation">:</span> <span class="token string">"ISC"</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li>O arquivo <code>package.json</code> é onde você pode configurar seu projeto, adicionar informações como nome, versão e dependências (os pacotes que você instala).</li>
</ul>
<hr>
<h3 id="instalando-pacotes-com-npm">3. <strong>Instalando Pacotes com NPM</strong></h3>
<p><strong>Passo 1:</strong> Vamos instalar um pacote popular chamado <code>lodash</code>, que tem várias funções úteis para trabalhar com dados.</p>
<p><strong>Passo 2:</strong> No terminal, digite o seguinte comando para instalar o pacote <code>lodash</code>:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">npm</span> <span class="token function">install</span> lodash
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li>Este comando instala o pacote <code>lodash</code> e o adiciona ao arquivo <code>package.json</code> na seção <code>dependencies</code>. Ele também cria uma pasta chamada <code>node_modules</code>, onde todos os pacotes instalados são guardados.</li>
</ul>
<p><strong>Passo 3:</strong> Verifique o arquivo <code>package.json</code> novamente. Agora, você verá algo como isto:</p>
<pre class=" language-json"><code class="prism  language-json"><span class="token string">"dependencies"</span><span class="token punctuation">:</span> <span class="token punctuation">{</span>
  <span class="token string">"lodash"</span><span class="token punctuation">:</span> <span class="token string">"^4.17.21"</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li>Agora, <code>lodash</code> está listado como uma dependência do seu projeto. Isso significa que você pode usá-lo em seu código.</li>
</ul>
<hr>
<h3 id="usando-o-pacote-instalado-no-código">4. <strong>Usando o Pacote Instalado no Código</strong></h3>
<p><strong>Passo 1:</strong> Crie um arquivo chamado <code>app.js</code> dentro da pasta <code>dia-03-04</code>.</p>
<p><strong>Passo 2:</strong> No arquivo <code>app.js</code>, escreva o seguinte código para usar o pacote <code>lodash</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// app.js</span>

<span class="token keyword">const</span> _ <span class="token operator">=</span> <span class="token function">require</span><span class="token punctuation">(</span><span class="token string">'lodash'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">const</span> numeros <span class="token operator">=</span> <span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
<span class="token keyword">const</span> numerosEmbaralhados <span class="token operator">=</span> _<span class="token punctuation">.</span><span class="token function">shuffle</span><span class="token punctuation">(</span>numeros<span class="token punctuation">)</span><span class="token punctuation">;</span>

console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Números originais:"</span><span class="token punctuation">,</span> numeros<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Números embaralhados:"</span><span class="token punctuation">,</span> numerosEmbaralhados<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>const _ = require('lodash');</code></strong>: Isso importa o pacote <code>lodash</code> para que você possa usá-lo no seu código.</li>
<li><strong><code>_.shuffle(numeros);</code></strong>: Aqui usamos uma função do <code>lodash</code> chamada <code>shuffle</code> que embaralha os elementos do array.</li>
</ul>
<p><strong>Passo 3:</strong> Execute o código no terminal:</p>
<pre class=" language-bash"><code class="prism  language-bash">node app.js
</code></pre>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar os números originais e os números embaralhados, algo como:</p>
<pre><code>Números originais: [ 1, 2, 3, 4, 5 ]
Números embaralhados: [ 4, 1, 5, 3, 2 ]
</code></pre>
<hr>
<h3 id="dia-4-criação-de-scripts-npm"><strong>Dia 4: Criação de Scripts NPM</strong></h3>
<p><strong>Objetivo do Dia:</strong> Aprender a criar e usar scripts NPM para automatizar tarefas comuns no seu projeto.</p>
<hr>
<h3 id="o-que-são-scripts-npm">1. <strong>O que são Scripts NPM?</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>Scripts NPM são comandos personalizados que você pode adicionar ao seu projeto. Eles permitem que você automatize tarefas, como rodar o seu código, testar sua aplicação, ou até mesmo iniciar um servidor.</li>
</ul>
<hr>
<h3 id="criando-um-script-npm">2. <strong>Criando um Script NPM</strong></h3>
<p><strong>Passo 1:</strong> Abra o arquivo <code>package.json</code> na pasta <code>dia-03-04</code>.</p>
<p><strong>Passo 2:</strong> Na seção <code>"scripts"</code>, você verá algo assim:</p>
<pre class=" language-json"><code class="prism  language-json"><span class="token string">"scripts"</span><span class="token punctuation">:</span> <span class="token punctuation">{</span>
  <span class="token string">"test"</span><span class="token punctuation">:</span> <span class="token string">"echo \"Error: no test specified\" &amp;&amp; exit 1"</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Passo 3:</strong> Vamos adicionar um script personalizado chamado <code>start</code> que executa o arquivo <code>app.js</code> que criamos:</p>
<pre class=" language-json"><code class="prism  language-json"><span class="token string">"scripts"</span><span class="token punctuation">:</span> <span class="token punctuation">{</span>
  <span class="token string">"start"</span><span class="token punctuation">:</span> <span class="token string">"node app.js"</span><span class="token punctuation">,</span>
  <span class="token string">"test"</span><span class="token punctuation">:</span> <span class="token string">"echo \"Error: no test specified\" &amp;&amp; exit 1"</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li>O script <code>start</code> vai executar o comando <code>node app.js</code> sempre que você digitar <code>npm start</code> no terminal.</li>
</ul>
<hr>
<h3 id="executando-o-script-npm">3. <strong>Executando o Script NPM</strong></h3>
<p><strong>Passo 1:</strong> No terminal, dentro da pasta <code>dia-03-04</code>, execute o script <code>start</code> usando o comando:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">npm</span> start
</code></pre>
<p><strong>Resultado esperado:</strong><br>
O terminal deve executar o <code>app.js</code>, assim como você fez no Dia 3, mostrando os números originais e embaralhados.</p>
<hr>
<h3 id="criando-scripts-adicionais">4. <strong>Criando Scripts Adicionais</strong></h3>
<p><strong>Passo 1:</strong> Vamos criar outro script chamado <code>embaralhar</code> para rodar apenas a função de embaralhar os números.</p>
<p><strong>Passo 2:</strong> No arquivo <code>package.json</code>, adicione o script:</p>
<pre class=" language-json"><code class="prism  language-json"><span class="token string">"scripts"</span><span class="token punctuation">:</span> <span class="token punctuation">{</span>
  <span class="token string">"start"</span><span class="token punctuation">:</span> <span class="token string">"node app.js"</span><span class="token punctuation">,</span>
  <span class="token string">"embaralhar"</span><span class="token punctuation">:</span> <span class="token string">"node app.js"</span><span class="token punctuation">,</span>
  <span class="token string">"test"</span><span class="token punctuation">:</span> <span class="token string">"echo \"Error: no test specified\" &amp;&amp; exit 1"</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Passo 3:</strong> No terminal, execute o novo script com o comando:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">npm</span> run embaralhar
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>npm run embaralhar</code></strong> executa o script <code>embaralhar</code> que você criou, que simplesmente roda o código de <code>app.js</code> de novo.</li>
</ul>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar novamente os números originais e os números embaralhados.</p>
<hr>
<h3 id="conclusão"><strong>Conclusão</strong></h3>
<p>Com esses passos, você aprendeu como instalar pacotes usando o NPM, como usar esses pacotes em seu código e como criar scripts NPM para automatizar tarefas no seu projeto. Isso é fundamental para trabalhar de maneira eficiente e organizada com Node.js.</p>
</div>
</body>

</html>
