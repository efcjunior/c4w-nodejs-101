---


---

<hr>
<h1 id="semana-1-introdução-ao-node.js"><strong>Semana 1: Introdução ao Node.js</strong></h1>
<h3 id="dia-5-criando-o-primeiro-script-node.js---parte-1"><strong>Dia 5: Criando o Primeiro Script Node.js - Parte 1</strong></h3>
<p><strong>Objetivo do Dia:</strong> Criar um script simples em Node.js que interage com o terminal e começar a aprender sobre os módulos internos do Node.js.</p>
<hr>
<h3 id="criando-um-script-que-conta-palavras">1. <strong>Criando um Script que Conta Palavras</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>Vamos criar um script que pede ao usuário para digitar uma frase no terminal e, em seguida, conta quantas palavras essa frase tem.</li>
</ul>
<p><strong>Passo 1:</strong> Crie um novo arquivo chamado <code>contadorDePalavras.js</code>.</p>
<p><strong>Passo 2:</strong> No arquivo <code>contadorDePalavras.js</code>, comece escrevendo o código abaixo:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">const</span> readline <span class="token operator">=</span> <span class="token function">require</span><span class="token punctuation">(</span><span class="token string">'readline'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">// Configura a interface para ler a entrada do terminal</span>
<span class="token keyword">const</span> rl <span class="token operator">=</span> readline<span class="token punctuation">.</span><span class="token function">createInterface</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
  input<span class="token punctuation">:</span> process<span class="token punctuation">.</span>stdin<span class="token punctuation">,</span>
  output<span class="token punctuation">:</span> process<span class="token punctuation">.</span>stdout
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">// Pergunta ao usuário para digitar uma frase</span>
rl<span class="token punctuation">.</span><span class="token function">question</span><span class="token punctuation">(</span><span class="token string">"Digite uma frase: "</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span>frase<span class="token punctuation">)</span> <span class="token punctuation">{</span>
  <span class="token comment">// Divide a frase em palavras, usando o espaço como separador</span>
  <span class="token keyword">const</span> palavras <span class="token operator">=</span> frase<span class="token punctuation">.</span><span class="token function">split</span><span class="token punctuation">(</span><span class="token string">' '</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  
  <span class="token comment">// Conta o número de palavras</span>
  <span class="token keyword">const</span> numeroDePalavras <span class="token operator">=</span> palavras<span class="token punctuation">.</span>length<span class="token punctuation">;</span>

  <span class="token comment">// Mostra o número de palavras no terminal</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Número de palavras:"</span><span class="token punctuation">,</span> numeroDePalavras<span class="token punctuation">)</span><span class="token punctuation">;</span>

  <span class="token comment">// Fecha a interface de leitura</span>
  rl<span class="token punctuation">.</span><span class="token function">close</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>readline</code></strong>: Este módulo interno do Node.js permite que você leia a entrada do usuário via terminal.</li>
<li><strong><code>rl.question</code></strong>: Esta função faz uma pergunta ao usuário e espera uma resposta.</li>
<li><strong><code>split(' ')</code></strong>: Divide a frase em um array de palavras, usando o espaço como separador.</li>
<li><strong><code>length</code></strong>: Conta quantos elementos (palavras) existem no array.</li>
</ul>
<p><strong>Passo 3:</strong> Salve o arquivo.</p>
<hr>
<h3 id="executando-o-script">2. <strong>Executando o Script</strong></h3>
<p><strong>Passo 1:</strong> Abra o terminal e navegue até o diretório onde o arquivo <code>contadorDePalavras.js</code> foi salvo.</p>
<p><strong>Passo 2:</strong> Execute o script com o seguinte comando:</p>
<pre class=" language-bash"><code class="prism  language-bash">node contadorDePalavras.js
</code></pre>
<p><strong>Passo 3:</strong> Quando o terminal pedir para digitar uma frase, digite qualquer frase e pressione Enter.</p>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar o número de palavras da frase que foi digitada.</p>
<hr>
<h3 id="dia-6-introdução-aos-módulos-internos-do-node.js"><strong>Dia 6: Introdução aos Módulos Internos do Node.js</strong></h3>
<p><strong>Objetivo do Dia:</strong> Aprender a usar módulos internos do Node.js como <code>fs</code> e <code>path</code> para ler e manipular arquivos.</p>
<hr>
<h3 id="usando-o-módulo-fs-file-system">1. <strong>Usando o Módulo <code>fs</code> (File System)</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>O módulo <code>fs</code> permite que você trabalhe com o sistema de arquivos, como ler, criar, atualizar e deletar arquivos.</li>
</ul>
<p><strong>Passo 1:</strong> Crie um novo arquivo chamado <code>manipulacaoDeArquivos.js</code>.</p>
<p><strong>Passo 2:</strong> No arquivo <code>manipulacaoDeArquivos.js</code>, adicione o código abaixo:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">const</span> fs <span class="token operator">=</span> <span class="token function">require</span><span class="token punctuation">(</span><span class="token string">'fs'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">// Escreve uma frase em um novo arquivo chamado "frase.txt"</span>
fs<span class="token punctuation">.</span><span class="token function">writeFile</span><span class="token punctuation">(</span><span class="token string">'frase.txt'</span><span class="token punctuation">,</span> <span class="token string">'Esta é uma frase de exemplo.'</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span>err<span class="token punctuation">)</span> <span class="token punctuation">{</span>
  <span class="token keyword">if</span> <span class="token punctuation">(</span>err<span class="token punctuation">)</span> <span class="token keyword">throw</span> err<span class="token punctuation">;</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">'Arquivo criado e frase salva!'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

  <span class="token comment">// Lê o conteúdo do arquivo "frase.txt"</span>
  fs<span class="token punctuation">.</span><span class="token function">readFile</span><span class="token punctuation">(</span><span class="token string">'frase.txt'</span><span class="token punctuation">,</span> <span class="token string">'utf8'</span><span class="token punctuation">,</span> <span class="token keyword">function</span><span class="token punctuation">(</span>err<span class="token punctuation">,</span> data<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">if</span> <span class="token punctuation">(</span>err<span class="token punctuation">)</span> <span class="token keyword">throw</span> err<span class="token punctuation">;</span>
    console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">'Conteúdo do arquivo:'</span><span class="token punctuation">,</span> data<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>fs.writeFile</code></strong>: Cria um arquivo e escreve o texto especificado dentro dele.</li>
<li><strong><code>fs.readFile</code></strong>: Lê o conteúdo de um arquivo e exibe no terminal.</li>
<li><strong><code>utf8</code></strong>: Especifica que o arquivo deve ser lido como texto.</li>
</ul>
<p><strong>Passo 3:</strong> Salve o arquivo.</p>
<hr>
<h3 id="usando-o-módulo-path">2. <strong>Usando o Módulo <code>path</code></strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>O módulo <code>path</code> ajuda a trabalhar com caminhos de arquivos e diretórios, facilitando a manipulação de caminhos de arquivos no seu código.</li>
</ul>
<p><strong>Passo 1:</strong> No arquivo <code>manipulacaoDeArquivos.js</code>, adicione o seguinte código abaixo do que já foi escrito:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">const</span> path <span class="token operator">=</span> <span class="token function">require</span><span class="token punctuation">(</span><span class="token string">'path'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">// Exibe o caminho completo do arquivo "frase.txt"</span>
<span class="token keyword">const</span> caminhoArquivo <span class="token operator">=</span> path<span class="token punctuation">.</span><span class="token function">resolve</span><span class="token punctuation">(</span><span class="token string">'frase.txt'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">'Caminho completo do arquivo:'</span><span class="token punctuation">,</span> caminhoArquivo<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>path.resolve</code></strong>: Gera o caminho completo do arquivo baseado no diretório atual.</li>
</ul>
<p><strong>Passo 2:</strong> Salve o arquivo.</p>
<hr>
<h3 id="executando-o-script-1">3. <strong>Executando o Script</strong></h3>
<p><strong>Passo 1:</strong> Abra o terminal e navegue até o diretório onde o arquivo <code>manipulacaoDeArquivos.js</code> foi salvo.</p>
<p><strong>Passo 2:</strong> Execute o script com o seguinte comando:</p>
<pre class=" language-bash"><code class="prism  language-bash">node manipulacaoDeArquivos.js
</code></pre>
<p><strong>Resultado esperado:</strong></p>
<ul>
<li>O terminal deve mostrar que o arquivo <code>frase.txt</code> foi criado e que seu conteúdo foi lido com sucesso.</li>
<li>Em seguida, o terminal deve mostrar o caminho completo do arquivo <code>frase.txt</code> no sistema de arquivos.</li>
</ul>

