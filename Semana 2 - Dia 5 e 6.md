<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Semana 2 - Dia 5 e 6</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><hr>
<h1 id="semana-2-projeto-1---gerador-de-senhas"><strong>Semana 2: Projeto 1 - Gerador de Senhas</strong></h1>
<h3 id="dia-5-criando-o-gerador-de-senhas-aleatórias---parte-1"><strong>Dia 5: Criando o Gerador de Senhas Aleatórias - Parte 1</strong></h3>
<p><strong>Objetivo do Dia:</strong> Criar um script em Node.js que gera senhas aleatórias e permite ao usuário escolher o tamanho da senha.</p>
<hr>
<h3 id="configurando-o-projeto">1. <strong>Configurando o Projeto</strong></h3>
<p><strong>Passo 1:</strong> Crie uma nova pasta dentro de <code>semana-02</code> chamada <code>dia-05-06</code> no seu repositório ou no seu computador.</p>
<p><strong>Passo 2:</strong> Abra o terminal e navegue até a nova pasta <code>dia-05-06</code>.</p>
<p><strong>Passo 3:</strong> Inicialize um novo projeto Node.js com o comando:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">npm</span> init -y
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li>Isso cria um arquivo <code>package.json</code> que será usado para gerenciar o projeto e suas dependências.</li>
</ul>
<hr>
<h3 id="criando-o-script-para-o-gerador-de-senhas">2. <strong>Criando o Script para o Gerador de Senhas</strong></h3>
<p><strong>Passo 1:</strong> Crie um arquivo chamado <code>geradorDeSenhas.js</code> dentro da pasta <code>dia-05-06</code>.</p>
<p><strong>Passo 2:</strong> No arquivo <code>geradorDeSenhas.js</code>, vamos começar criando uma função simples que gera uma senha aleatória de letras.</p>
<p><strong>Passo 3:</strong> Adicione o seguinte código:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// geradorDeSenhas.js</span>

<span class="token keyword">function</span> <span class="token function">gerarSenha</span><span class="token punctuation">(</span>tamanho<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">const</span> caracteres <span class="token operator">=</span> <span class="token string">'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz'</span><span class="token punctuation">;</span>
    <span class="token keyword">let</span> senha <span class="token operator">=</span> <span class="token string">''</span><span class="token punctuation">;</span>
    <span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">let</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> tamanho<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">const</span> indice <span class="token operator">=</span> Math<span class="token punctuation">.</span><span class="token function">floor</span><span class="token punctuation">(</span>Math<span class="token punctuation">.</span><span class="token function">random</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">*</span> caracteres<span class="token punctuation">.</span>length<span class="token punctuation">)</span><span class="token punctuation">;</span>
        senha <span class="token operator">+=</span> caracteres<span class="token punctuation">[</span>indice<span class="token punctuation">]</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    <span class="token keyword">return</span> senha<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token comment">// Exemplo de uso</span>
<span class="token keyword">const</span> tamanho <span class="token operator">=</span> <span class="token number">8</span><span class="token punctuation">;</span> <span class="token comment">// Tamanho da senha</span>
<span class="token keyword">const</span> senhaGerada <span class="token operator">=</span> <span class="token function">gerarSenha</span><span class="token punctuation">(</span>tamanho<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Senha gerada:"</span><span class="token punctuation">,</span> senhaGerada<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>caracteres</code></strong>: Esta string contém todas as letras maiúsculas e minúsculas que podem ser usadas na senha.</li>
<li><strong><code>Math.random()</code></strong>: Esta função gera um número aleatório entre 0 e 1, que usamos para escolher um caractere aleatório da string <code>caracteres</code>.</li>
<li><strong><code>Math.floor()</code></strong>: Esta função arredonda o número para baixo, garantindo que o índice seja um número inteiro válido.</li>
</ul>
<p><strong>Passo 4:</strong> Salve o arquivo.</p>
<hr>
<h3 id="executando-o-gerador-de-senhas">3. <strong>Executando o Gerador de Senhas</strong></h3>
<p><strong>Passo 1:</strong> No terminal, execute o script com o seguinte comando:</p>
<pre class=" language-bash"><code class="prism  language-bash">node geradorDeSenhas.js
</code></pre>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar uma senha aleatória composta de 8 letras, algo como:</p>
<pre><code>Senha gerada: AbCDefGh
</code></pre>
<hr>
<h3 id="dia-6-adicionando-funcionalidades-extras"><strong>Dia 6: Adicionando Funcionalidades Extras</strong></h3>
<p><strong>Objetivo do Dia:</strong> Melhorar o gerador de senhas, adicionando opções para incluir números e símbolos, e permitir que o usuário escolha essas opções.</p>
<hr>
<h3 id="adicionando-números-e-símbolos-à-senha">1. <strong>Adicionando Números e Símbolos à Senha</strong></h3>
<p><strong>Passo 1:</strong> Vamos modificar a função <code>gerarSenha</code> para permitir que o usuário escolha se quer incluir números e símbolos na senha.</p>
<p><strong>Passo 2:</strong> No arquivo <code>geradorDeSenhas.js</code>, modifique o código para ficar assim:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// geradorDeSenhas.js</span>

<span class="token keyword">function</span> <span class="token function">gerarSenha</span><span class="token punctuation">(</span>tamanho<span class="token punctuation">,</span> incluirNumeros <span class="token operator">=</span> <span class="token boolean">false</span><span class="token punctuation">,</span> incluirSimbolos <span class="token operator">=</span> <span class="token boolean">false</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">let</span> caracteres <span class="token operator">=</span> <span class="token string">'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz'</span><span class="token punctuation">;</span>
    <span class="token keyword">if</span> <span class="token punctuation">(</span>incluirNumeros<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        caracteres <span class="token operator">+=</span> <span class="token string">'0123456789'</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    <span class="token keyword">if</span> <span class="token punctuation">(</span>incluirSimbolos<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        caracteres <span class="token operator">+=</span> <span class="token string">'!@#$%^&amp;*()_+[]{}|;:,.&lt;&gt;?'</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token keyword">let</span> senha <span class="token operator">=</span> <span class="token string">''</span><span class="token punctuation">;</span>
    <span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">let</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> tamanho<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">const</span> indice <span class="token operator">=</span> Math<span class="token punctuation">.</span><span class="token function">floor</span><span class="token punctuation">(</span>Math<span class="token punctuation">.</span><span class="token function">random</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">*</span> caracteres<span class="token punctuation">.</span>length<span class="token punctuation">)</span><span class="token punctuation">;</span>
        senha <span class="token operator">+=</span> caracteres<span class="token punctuation">[</span>indice<span class="token punctuation">]</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    <span class="token keyword">return</span> senha<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token comment">// Exemplo de uso</span>
<span class="token keyword">const</span> tamanho <span class="token operator">=</span> <span class="token number">12</span><span class="token punctuation">;</span> <span class="token comment">// Tamanho da senha</span>
<span class="token keyword">const</span> incluirNumeros <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span> <span class="token comment">// Incluir números na senha</span>
<span class="token keyword">const</span> incluirSimbolos <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">;</span> <span class="token comment">// Incluir símbolos na senha</span>
<span class="token keyword">const</span> senhaGerada <span class="token operator">=</span> <span class="token function">gerarSenha</span><span class="token punctuation">(</span>tamanho<span class="token punctuation">,</span> incluirNumeros<span class="token punctuation">,</span> incluirSimbolos<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Senha gerada:"</span><span class="token punctuation">,</span> senhaGerada<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>incluirNumeros</code></strong>: Esta opção adiciona números à lista de caracteres que podem ser usados na senha.</li>
<li><strong><code>incluirSimbolos</code></strong>: Esta opção adiciona símbolos à lista de caracteres que podem ser usados na senha.</li>
<li><strong>Valores padrão</strong>: As variáveis <code>incluirNumeros</code> e <code>incluirSimbolos</code> têm valores padrão definidos como <code>false</code>, o que significa que se você não passar um valor para elas, elas serão <code>false</code> por padrão.</li>
</ul>
<hr>
<h3 id="executando-o-gerador-de-senhas-com-novas-funcionalidades">2. <strong>Executando o Gerador de Senhas com Novas Funcionalidades</strong></h3>
<p><strong>Passo 1:</strong> No terminal, execute o script novamente com o comando:</p>
<pre class=" language-bash"><code class="prism  language-bash">node geradorDeSenhas.js
</code></pre>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar uma senha aleatória composta de letras, números e símbolos, algo como:</p>
<pre><code>Senha gerada: Ab1!Cd2@Ef3#
</code></pre>
<hr>
<h3 id="permitir-ao-usuário-escolher-as-opções-no-terminal">3. <strong>Permitir ao Usuário Escolher as Opções no Terminal</strong></h3>
<p><strong>Passo 1:</strong> Vamos melhorar ainda mais o gerador de senhas, permitindo que o usuário escolha o tamanho da senha e se quer incluir números e símbolos diretamente no terminal.</p>
<p><strong>Passo 2:</strong> No arquivo <code>geradorDeSenhas.js</code>, adicione o código abaixo:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// geradorDeSenhas.js</span>

<span class="token keyword">const</span> readline <span class="token operator">=</span> <span class="token function">require</span><span class="token punctuation">(</span><span class="token string">'readline'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">function</span> <span class="token function">gerarSenha</span><span class="token punctuation">(</span>tamanho<span class="token punctuation">,</span> incluirNumeros <span class="token operator">=</span> <span class="token boolean">false</span><span class="token punctuation">,</span> incluirSimbolos <span class="token operator">=</span> <span class="token boolean">false</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">let</span> caracteres <span class="token operator">=</span> <span class="token string">'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz'</span><span class="token punctuation">;</span>
    <span class="token keyword">if</span> <span class="token punctuation">(</span>incluirNumeros<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        caracteres <span class="token operator">+=</span> <span class="token string">'0123456789'</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    <span class="token keyword">if</span> <span class="token punctuation">(</span>incluirSimbolos<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        caracteres <span class="token operator">+=</span> <span class="token string">'!@#$%^&amp;*()_+[]{}|;:,.&lt;&gt;?'</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>

    <span class="token keyword">let</span> senha <span class="token operator">=</span> <span class="token string">''</span><span class="token punctuation">;</span>
    <span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">let</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> tamanho<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token keyword">const</span> indice <span class="token operator">=</span> Math<span class="token punctuation">.</span><span class="token function">floor</span><span class="token punctuation">(</span>Math<span class="token punctuation">.</span><span class="token function">random</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">*</span> caracteres<span class="token punctuation">.</span>length<span class="token punctuation">)</span><span class="token punctuation">;</span>
        senha <span class="token operator">+=</span> caracteres<span class="token punctuation">[</span>indice<span class="token punctuation">]</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    <span class="token keyword">return</span> senha<span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token comment">// Configurando o readline para ler a entrada do usuário</span>
<span class="token keyword">const</span> rl <span class="token operator">=</span> readline<span class="token punctuation">.</span><span class="token function">createInterface</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
    input<span class="token punctuation">:</span> process<span class="token punctuation">.</span>stdin<span class="token punctuation">,</span>
    output<span class="token punctuation">:</span> process<span class="token punctuation">.</span>stdout
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

rl<span class="token punctuation">.</span><span class="token function">question</span><span class="token punctuation">(</span><span class="token string">'Qual o tamanho da senha? '</span><span class="token punctuation">,</span> <span class="token punctuation">(</span>tamanho<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
    rl<span class="token punctuation">.</span><span class="token function">question</span><span class="token punctuation">(</span><span class="token string">'Incluir números? (s/n) '</span><span class="token punctuation">,</span> <span class="token punctuation">(</span>respostaNumeros<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        rl<span class="token punctuation">.</span><span class="token function">question</span><span class="token punctuation">(</span><span class="token string">'Incluir símbolos? (s/n) '</span><span class="token punctuation">,</span> <span class="token punctuation">(</span>respostaSimbolos<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
            <span class="token keyword">const</span> incluirNumeros <span class="token operator">=</span> respostaNumeros<span class="token punctuation">.</span><span class="token function">toLowerCase</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">===</span> <span class="token string">'s'</span><span class="token punctuation">;</span>
            <span class="token keyword">const</span> incluirSimbolos <span class="token operator">=</span> respostaSimbolos<span class="token punctuation">.</span><span class="token function">toLowerCase</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">===</span> <span class="token string">'s'</span><span class="token punctuation">;</span>
            <span class="token keyword">const</span> senhaGerada <span class="token operator">=</span> <span class="token function">gerarSenha</span><span class="token punctuation">(</span><span class="token function">parseInt</span><span class="token punctuation">(</span>tamanho<span class="token punctuation">)</span><span class="token punctuation">,</span> incluirNumeros<span class="token punctuation">,</span> incluirSimbolos<span class="token punctuation">)</span><span class="token punctuation">;</span>
            console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Senha gerada:"</span><span class="token punctuation">,</span> senhaGerada<span class="token punctuation">)</span><span class="token punctuation">;</span>
            rl<span class="token punctuation">.</span><span class="token function">close</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>readline</code></strong>: Este módulo permite que o programa faça perguntas ao usuário e receba respostas diretamente no terminal.</li>
<li><strong><code>rl.question</code></strong>: Faz uma pergunta ao usuário e espera uma resposta. Baseado nas respostas, o programa gera a senha conforme as preferências do usuário.</li>
</ul>
<hr>
<h3 id="executando-o-gerador-de-senhas-com-interação-do-usuário">4. <strong>Executando o Gerador de Senhas com Interação do Usuário</strong></h3>
<p><strong>Passo 1:</strong> No terminal, execute o script novamente:</p>
<pre class=" language-bash"><code class="prism  language-bash">node geradorDeSenhas.js
</code></pre>
<p><strong>Passo 2:</strong> Responda às perguntas no terminal:</p>
<ul>
<li>Informe o tamanho da senha (por exemplo, 10).</li>
<li>Escolha se quer incluir números (responda com “s” para sim ou “n” para não).</li>
<li>Escolha se quer incluir símbolos (responda com “s” para sim ou “n” para não).</li>
</ul>
<p><strong>Resultado esperado:</strong><br>
O terminal deve mostrar uma senha gerada de acordo com as opções que você escolheu, por exemplo:</p>
<pre><code>Senha gerada: Ab3!Df7@Gh
</code></pre>
<hr>
<h3 id="conclusão"><strong>Conclusão</strong></h3>
<p>Com esses passos, você criou um gerador de senhas aleatórias em Node.js, que permite ao usuário escolher o tamanho da senha e se quer incluir números e símbolos. Esse projeto não só reforça conceitos básicos de Node.js como também mostra como criar scripts úteis e interativos.</p>
</div>
</body>

</html>
