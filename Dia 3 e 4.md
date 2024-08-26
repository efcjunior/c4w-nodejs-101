---


---

<hr>
<h1 id="semana-1-introdução-ao-node.js"><strong>Semana 1: Introdução ao Node.js</strong></h1>
<h3 id="dia-3-fundamentos-de-javascript---parte-1"><strong>Dia 3: Fundamentos de JavaScript - Parte 1</strong></h3>
<p><strong>Objetivo do Dia:</strong> Aprender sobre variáveis, tipos de dados e operadores em JavaScript.</p>
<hr>
<h3 id="o-que-são-variáveis">1. <strong>O que são Variáveis?</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>Variáveis são como caixinhas onde guardamos informações. Essas informações podem ser números, palavras, ou até frases inteiras.</li>
<li>Pense numa variável como um nome que damos para algo que queremos usar depois no código.</li>
</ul>
<p><strong>Passo 1:</strong> Abra o arquivo <code>index.js</code> que criamos no Dia 1.</p>
<p><strong>Passo 2:</strong> Escreva o seguinte código para criar variáveis e mostrar o que elas guardam:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> nome <span class="token operator">=</span> <span class="token string">"Lucas"</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> idade <span class="token operator">=</span> <span class="token number">30</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> cidade <span class="token operator">=</span> <span class="token string">"São Paulo"</span><span class="token punctuation">;</span>

console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Nome:"</span><span class="token punctuation">,</span> nome<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Idade:"</span><span class="token punctuation">,</span> idade<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Cidade:"</span><span class="token punctuation">,</span> cidade<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>let nome = "Lucas";</code></strong>: Criamos uma variável chamada <code>nome</code> e guardamos o valor “Lucas” nela.</li>
<li><strong><code>console.log("Nome:", nome);</code></strong>: Mostramos no terminal o texto “Nome:” seguido do valor guardado na variável <code>nome</code>.</li>
</ul>
<p><strong>Passo 3:</strong> Rode o código no terminal:</p>
<pre class=" language-bash"><code class="prism  language-bash">node index.js
</code></pre>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar:</p>
<pre><code>Nome: Lucas
Idade: 30
Cidade: São Paulo
</code></pre>
<hr>
<h3 id="tipos-de-dados">2. <strong>Tipos de Dados</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>Em JavaScript, as variáveis podem guardar diferentes tipos de dados:
<ul>
<li><strong>Números</strong>: Por exemplo, <code>30</code> ou <code>3.14</code>.</li>
<li><strong>Texto (String)</strong>: Sequências de caracteres, como <code>"Olá"</code> ou <code>"JavaScript"</code>.</li>
<li><strong>Booleano</strong>: Verdadeiro ou falso (<code>true</code> ou <code>false</code>).</li>
</ul>
</li>
</ul>
<p><strong>Passo 1:</strong> Adicione os seguintes exemplos no <code>index.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> numero <span class="token operator">=</span> <span class="token number">42</span><span class="token punctuation">;</span>          <span class="token comment">// Número</span>
<span class="token keyword">let</span> texto <span class="token operator">=</span> <span class="token string">"Aprendendo JavaScript"</span><span class="token punctuation">;</span>  <span class="token comment">// Texto (String)</span>
<span class="token keyword">let</span> verdadeiro <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span>    <span class="token comment">// Booleano (verdadeiro ou falso)</span>

console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Número:"</span><span class="token punctuation">,</span> numero<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Texto:"</span><span class="token punctuation">,</span> texto<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Verdadeiro:"</span><span class="token punctuation">,</span> verdadeiro<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Passo 2:</strong> Rode o código no terminal para ver o resultado.</p>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar:</p>
<pre><code>Número: 42
Texto: Aprendendo JavaScript
Verdadeiro: true
</code></pre>
<hr>
<h3 id="operadores">3. <strong>Operadores</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>Operadores são usados para fazer cálculos ou comparar valores.</li>
<li>Existem diferentes tipos de operadores:
<ul>
<li><strong>Aritméticos:</strong> Para cálculos, como <code>+</code> (soma), <code>-</code> (subtração), <code>*</code> (multiplicação), <code>/</code> (divisão).</li>
<li><strong>De Comparação:</strong> Para comparar valores, como <code>==</code> (igual), <code>!=</code> (diferente), <code>&gt;</code> (maior), <code>&lt;</code> (menor).</li>
</ul>
</li>
</ul>
<p><strong>Passo 1:</strong> Adicione os exemplos abaixo no <code>index.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> a <span class="token operator">=</span> <span class="token number">10</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> b <span class="token operator">=</span> <span class="token number">5</span><span class="token punctuation">;</span>

<span class="token keyword">let</span> soma <span class="token operator">=</span> a <span class="token operator">+</span> b<span class="token punctuation">;</span>  <span class="token comment">// Soma</span>
<span class="token keyword">let</span> diferenca <span class="token operator">=</span> a <span class="token operator">-</span> b<span class="token punctuation">;</span>  <span class="token comment">// Subtração</span>
<span class="token keyword">let</span> produto <span class="token operator">=</span> a <span class="token operator">*</span> b<span class="token punctuation">;</span>  <span class="token comment">// Multiplicação</span>
<span class="token keyword">let</span> divisao <span class="token operator">=</span> a <span class="token operator">/</span> b<span class="token punctuation">;</span>  <span class="token comment">// Divisão</span>

console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Soma:"</span><span class="token punctuation">,</span> soma<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Diferença:"</span><span class="token punctuation">,</span> diferenca<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Produto:"</span><span class="token punctuation">,</span> produto<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Divisão:"</span><span class="token punctuation">,</span> divisao<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Passo 2:</strong> Rode o código no terminal para ver os resultados.</p>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar:</p>
<pre><code>Soma: 15
Diferença: 5
Produto: 50
Divisão: 2
</code></pre>
<hr>
<h3 id="dia-4-fundamentos-de-javascript---parte-2"><strong>Dia 4: Fundamentos de JavaScript - Parte 2</strong></h3>
<p><strong>Objetivo do Dia:</strong> Aprender sobre estruturas de controle, como if/else e loops.</p>
<hr>
<h3 id="estruturas-de-controle-ifelse">1. <strong>Estruturas de Controle: if/else</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>Às vezes, queremos que o programa tome decisões, como “se a idade for 18 ou mais, mostre que é maior de idade”.</li>
<li>Usamos <strong>if/else</strong> para fazer isso.</li>
</ul>
<p><strong>Passo 1:</strong> Adicione o código abaixo no <code>index.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> idade <span class="token operator">=</span> <span class="token number">16</span><span class="token punctuation">;</span>

<span class="token keyword">if</span> <span class="token punctuation">(</span>idade <span class="token operator">&gt;=</span> <span class="token number">18</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Você é maior de idade."</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Você é menor de idade."</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li>O código verifica se a <code>idade</code> é 18 ou mais.</li>
<li>Se for, mostra “Você é maior de idade”.</li>
<li>Se não for, mostra “Você é menor de idade”.</li>
</ul>
<p><strong>Passo 2:</strong> Rode o código no terminal.</p>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar:</p>
<pre><code>Você é menor de idade.
</code></pre>
<hr>
<h3 id="estruturas-de-repetição-loops">2. <strong>Estruturas de Repetição: Loops</strong></h3>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>Loops permitem repetir uma ação várias vezes, como “mostrar cada item de uma lista de frutas”.</li>
<li>Um dos loops mais comuns é o <strong>for</strong>.</li>
</ul>
<p><strong>Passo 1:</strong> Adicione o código abaixo no <code>index.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> frutas <span class="token operator">=</span> <span class="token punctuation">[</span><span class="token string">"maçã"</span><span class="token punctuation">,</span> <span class="token string">"banana"</span><span class="token punctuation">,</span> <span class="token string">"laranja"</span><span class="token punctuation">]</span><span class="token punctuation">;</span>

<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">let</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> frutas<span class="token punctuation">.</span>length<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>frutas<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>let frutas = ["maçã", "banana", "laranja"];</code></strong>: Criamos uma lista com três frutas.</li>
<li>O loop <strong>for</strong> começa no <code>0</code> (primeira fruta) e vai até <code>2</code> (última fruta), mostrando cada uma delas.</li>
</ul>
<p><strong>Passo 2:</strong> Rode o código no terminal.</p>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar:</p>
<pre><code>maçã
banana
laranja
</code></pre>
<hr>
<h3 id="exercício-prático">3. <strong>Exercício Prático</strong></h3>
<p><strong>Tarefa:</strong></p>
<ul>
<li>Peça ao aluno para criar uma nova lista de números e usar um loop para somar todos os números da lista.</li>
<li>O aluno deve exibir o resultado no terminal.</li>
</ul>
<p><strong>Dica:</strong></p>
<ul>
<li>O aluno pode usar o que aprendeu sobre variáveis, loops, e operadores para completar essa tarefa.</li>
</ul>
<p><strong>Exemplo de Solução:</strong></p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> numeros <span class="token operator">=</span> <span class="token punctuation">[</span><span class="token number">10</span><span class="token punctuation">,</span> <span class="token number">20</span><span class="token punctuation">,</span> <span class="token number">30</span><span class="token punctuation">]</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> somaTotal <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>

<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">let</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> numeros<span class="token punctuation">.</span>length<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  somaTotal <span class="token operator">+=</span> numeros<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">;</span>  <span class="token comment">// somaTotal = somaTotal + numeros[i];</span>
<span class="token punctuation">}</span>

console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Soma total:"</span><span class="token punctuation">,</span> somaTotal<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar:</p>
<pre><code>Soma total: 60
</code></pre>
<hr>

