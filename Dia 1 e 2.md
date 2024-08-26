---


---

<hr>
<h1 id="semana-1-introdução-ao-node.js"><strong>Semana 1: Introdução ao Node.js</strong></h1>
<h3 id="dia-1-instalação-e-configuração-do-ambiente"><strong>Dia 1: Instalação e Configuração do Ambiente</strong></h3>
<p><strong>Objetivo do Dia:</strong> Configurar o ambiente de programação para começar a escrever e executar códigos em Node.js.</p>
<hr>
<h3 id="o-que-é-node.js">1. <strong>O que é Node.js?</strong></h3>
<p>Node.js é uma ferramenta que permite usar a linguagem de programação JavaScript fora do navegador. Com ela, podemos criar aplicativos como sites, jogos, e ferramentas que rodam em servidores.</p>
<hr>
<h3 id="instalando-node.js-no-computador">2. <strong>Instalando Node.js no Computador</strong></h3>
<p><strong>Passo 1:</strong> Acesse o site oficial do Node.js: <a href="https://nodejs.org">https://nodejs.org</a>.</p>
<p><strong>Passo 2:</strong> No site, escolha a versão “LTS” (Long Term Support), pois é a mais estável e indicada para a maioria dos projetos.</p>
<p><strong>Passo 3:</strong> Baixe o instalador e, após o download, clique duas vezes no arquivo para iniciar a instalação.</p>
<p><strong>Passo 4:</strong> Durante a instalação, mantenha as opções padrão e continue clicando em “Next”. No final, clique em “Finish” para concluir.</p>
<hr>
<h3 id="verificando-a-instalação-do-node.js">3. <strong>Verificando a Instalação do Node.js</strong></h3>
<p><strong>Passo 1:</strong> Abra o terminal do seu computador. No Windows, pode ser o “Prompt de Comando” ou “PowerShell”. No Mac, abra o “Terminal”.</p>
<p><strong>Passo 2:</strong> Digite o comando abaixo e pressione Enter:</p>
<pre class=" language-bash"><code class="prism  language-bash">node -v
</code></pre>
<p><strong>Passo 3:</strong> Se o terminal mostrar um número (a versão do Node.js), a instalação foi bem-sucedida!</p>
<hr>
<h3 id="configurando-um-editor-de-texto">4. <strong>Configurando um Editor de Texto</strong></h3>
<p><strong>Passo 1:</strong> Vamos usar um programa chamado “Visual Studio Code” (VS Code) para escrever nossos códigos.</p>
<p><strong>Passo 2:</strong> Acesse <a href="https://code.visualstudio.com/">https://code.visualstudio.com/</a> e baixe o instalador do VS Code.</p>
<p><strong>Passo 3:</strong> Após baixar, instale o VS Code seguindo as instruções na tela.</p>
<p><strong>Passo 4:</strong> Abra o VS Code após a instalação.</p>
<hr>
<h3 id="criando-o-primeiro-projeto">5. <strong>Criando o Primeiro Projeto</strong></h3>
<p><strong>Passo 1:</strong> No VS Code, crie uma nova pasta para guardar os códigos. Clique em “File” no menu superior e depois em “Open Folder”.</p>
<p><strong>Passo 2:</strong> Escolha um local no seu computador e clique em “New Folder” para criar uma nova pasta. Nomeie-a como “meu_primeiro_projeto” e clique em “Select Folder”.</p>
<p><strong>Passo 3:</strong> Com a pasta aberta no VS Code, clique com o botão direito nela e selecione “New File”. Nomeie o arquivo como <code>index.js</code>.</p>
<hr>
<h3 id="escrevendo-e-rodando-o-primeiro-código">6. <strong>Escrevendo e Rodando o Primeiro Código</strong></h3>
<p><strong>Passo 1:</strong> No arquivo <code>index.js</code>, escreva o seguinte código:</p>
<pre class=" language-javascript"><code class="prism  language-javascript">console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Olá, Node.js!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Passo 2:</strong> Esse código vai mostrar a mensagem “Olá, Node.js!” na tela.</p>
<p><strong>Passo 3:</strong> Para rodar o código, volte ao terminal, navegue até a pasta do projeto e execute o comando abaixo:</p>
<pre class=" language-bash"><code class="prism  language-bash">node index.js
</code></pre>
<p><strong>Passo 4:</strong> Se tudo estiver certo, você verá “Olá, Node.js!” no terminal. Parabéns, você escreveu e rodou seu primeiro código em Node.js!</p>
<hr>
<h3 id="dia-2-fundamentos-de-javascript"><strong>Dia 2: Fundamentos de JavaScript</strong></h3>
<p><strong>Objetivo do Dia:</strong> Aprender os conceitos básicos de JavaScript, a linguagem que usaremos no Node.js.</p>
<hr>
<h3 id="entendendo-variáveis">1. <strong>Entendendo Variáveis</strong></h3>
<p><strong>O que é uma variável?</strong><br>
Pense numa variável como uma caixinha onde guardamos informações, como um número, uma palavra, ou uma frase.</p>
<p><strong>Criando Variáveis em JavaScript</strong></p>
<p><strong>Passo 1:</strong> No arquivo <code>index.js</code>, apague o que fizemos no dia anterior e adicione:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> nome <span class="token operator">=</span> <span class="token string">"João"</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>nome<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong><br>
Aqui, <code>let</code> é usado para criar uma variável chamada <code>nome</code>, e colocamos “João” dentro dela. Quando rodamos o código, a linha <code>console.log(nome);</code> vai mostrar “João” no terminal.</p>
<hr>
<h3 id="trabalhando-com-números">2. <strong>Trabalhando com Números</strong></h3>
<p><strong>Criando e Usando Variáveis Numéricas</strong></p>
<p><strong>Passo 1:</strong> Vamos adicionar mais algumas variáveis no <code>index.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> idade <span class="token operator">=</span> <span class="token number">15</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> anoAtual <span class="token operator">=</span> <span class="token number">2024</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Idade:"</span><span class="token punctuation">,</span> idade<span class="token punctuation">)</span><span class="token punctuation">;</span>
console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Ano:"</span><span class="token punctuation">,</span> anoAtual<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong><br>
Aqui, criamos duas variáveis, <code>idade</code> e <code>anoAtual</code>, e guardamos números nelas. Quando rodamos o código, ele vai mostrar “Idade: 15” e “Ano: 2024” no terminal.</p>
<hr>
<h3 id="condicionais-ifelse">3. <strong>Condicionais (if/else)</strong></h3>
<p><strong>O que é uma Condicional?</strong><br>
Às vezes, queremos que o programa faça algo apenas se uma condição for verdadeira. Por exemplo, mostrar uma mensagem diferente dependendo da idade da pessoa.</p>
<p><strong>Exemplo Prático</strong></p>
<p><strong>Passo 1:</strong> Adicione o código abaixo no <code>index.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">if</span> <span class="token punctuation">(</span>idade <span class="token operator">&gt;=</span> <span class="token number">18</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Você é maior de idade."</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Você é menor de idade."</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Explicação:</strong><br>
Esse código verifica se a idade é 18 ou mais. Se for, ele diz “Você é maior de idade”. Se não for, ele diz “Você é menor de idade”.</p>
<hr>
<h3 id="introdução-a-loops-repetições">4. <strong>Introdução a Loops (Repetições)</strong></h3>
<p><strong>O que é um Loop?</strong><br>
Um loop é uma maneira de fazer o programa repetir algo várias vezes.</p>
<p><strong>Exemplo Prático</strong></p>
<p><strong>Passo 1:</strong> Adicione o código abaixo no <code>index.js</code>:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">let</span> frutas <span class="token operator">=</span> <span class="token punctuation">[</span><span class="token string">"maçã"</span><span class="token punctuation">,</span> <span class="token string">"banana"</span><span class="token punctuation">,</span> <span class="token string">"laranja"</span><span class="token punctuation">]</span><span class="token punctuation">;</span>

<span class="token keyword">for</span> <span class="token punctuation">(</span><span class="token keyword">let</span> i <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span> i <span class="token operator">&lt;</span> frutas<span class="token punctuation">.</span>length<span class="token punctuation">;</span> i<span class="token operator">++</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>frutas<span class="token punctuation">[</span>i<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p><strong>Explicação:</strong><br>
Aqui, temos uma lista de frutas. O loop vai passar por cada fruta na lista e mostrá-la no terminal.</p>
<hr>

