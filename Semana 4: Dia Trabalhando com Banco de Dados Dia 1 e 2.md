---


---

<h1 id="semana-4-trabalhando-com-banco-de-dados"><strong>Semana 4: Trabalhando com Banco de Dados</strong></h1>
<h3 id="objetivo"><strong>Objetivo:</strong></h3>
<p>Introduzir o aluno ao uso de bancos de dados com Node.js, usando o MongoDB e a biblioteca Mongoose para realizar operações básicas de CRUD (Create, Read, Update, Delete).</p>
<hr>
<h3 id="dia-1-configuração-do-mongodb-e-conexão-com-node.js"><strong>Dia 1: Configuração do MongoDB e Conexão com Node.js</strong></h3>
<h4 id="o-que-é-o-mongodb"><strong>1. O que é o MongoDB?</strong></h4>
<p><strong>Explicação Simples:</strong></p>
<ul>
<li>MongoDB é um banco de dados NoSQL, o que significa que ele armazena dados em documentos no formato JSON em vez de tabelas como nos bancos de dados tradicionais (SQL). Ele é muito usado para aplicações que precisam armazenar dados flexíveis.</li>
</ul>
<hr>
<h4 id="instalando-o-mongodb-localmente"><strong>2. Instalando o MongoDB Localmente</strong></h4>
<p><strong>Passo 1:</strong> Vá até o site oficial do <a href="https://www.mongodb.com/try/download/community">MongoDB</a> e baixe a versão <strong>MongoDB Community Server</strong> compatível com seu sistema operacional.</p>
<p><strong>Passo 2:</strong> Siga as instruções de instalação fornecidas pelo MongoDB para o seu sistema (Windows, macOS ou Linux).</p>
<p><strong>Passo 3:</strong> Após instalar, inicie o MongoDB no seu computador. Para iniciar o MongoDB, use o terminal ou o prompt de comando:</p>
<pre class=" language-bash"><code class="prism  language-bash">mongod
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>mongod</code></strong>: Este comando inicia o servidor MongoDB localmente. Ele começa a escutar conexões no seu sistema para gerenciar bancos de dados.</li>
</ul>
<hr>
<h4 id="instalando-o-mongoose"><strong>3. Instalando o Mongoose</strong></h4>
<p><strong>Passo 1:</strong> No seu projeto Node.js (por exemplo, <code>semana-04/dia-01-02</code>), abra o terminal e instale o Mongoose, que é uma biblioteca que facilita o uso do MongoDB com Node.js:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">npm</span> <span class="token function">install</span> mongoose
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li>O Mongoose é uma biblioteca que ajuda a definir modelos de dados e interagir com o MongoDB de maneira mais simples.</li>
</ul>
<hr>
<h4 id="conectando-o-node.js-ao-mongodb-usando-mongoose"><strong>4. Conectando o Node.js ao MongoDB Usando Mongoose</strong></h4>
<p><strong>Passo 1:</strong> Crie um arquivo chamado <code>app.js</code> no seu projeto.</p>
<p><strong>Passo 2:</strong> No arquivo <code>app.js</code>, adicione o seguinte código para conectar o Node.js ao MongoDB:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// app.js</span>

<span class="token keyword">const</span> mongoose <span class="token operator">=</span> <span class="token function">require</span><span class="token punctuation">(</span><span class="token string">'mongoose'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">// Conectar ao MongoDB</span>
mongoose<span class="token punctuation">.</span><span class="token function">connect</span><span class="token punctuation">(</span><span class="token string">'mongodb://localhost:27017/meu_banco_de_dados'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span> useNewUrlParser<span class="token punctuation">:</span> <span class="token boolean">true</span><span class="token punctuation">,</span> useUnifiedTopology<span class="token punctuation">:</span> <span class="token boolean">true</span> <span class="token punctuation">}</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Conectado ao MongoDB!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token punctuation">(</span>error<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">error</span><span class="token punctuation">(</span><span class="token string">"Erro ao conectar ao MongoDB:"</span><span class="token punctuation">,</span> error<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>mongoose.connect()</code></strong>: Este método conecta o Node.js ao MongoDB usando a URL de conexão.</li>
<li><strong><code>mongodb://localhost:27017/meu_banco_de_dados</code></strong>: A URL de conexão indica que o MongoDB está rodando localmente e se conectará ao banco de dados chamado <code>meu_banco_de_dados</code>.</li>
</ul>
<hr>
<h3 id="dia-2-realizando-operações-crud-com-mongodb"><strong>Dia 2: Realizando Operações CRUD com MongoDB</strong></h3>
<h4 id="criando-um-modelo-schema-no-mongoose"><strong>1. Criando um Modelo (Schema) no Mongoose</strong></h4>
<p><strong>Passo 1:</strong> No arquivo <code>app.js</code>, defina um modelo para os dados que serão armazenados no banco de dados. Vamos usar um exemplo de uma coleção de “Usuários”:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// Definir o schema do usuário</span>
<span class="token keyword">const</span> usuarioSchema <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token class-name">mongoose<span class="token punctuation">.</span>Schema</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
    nome<span class="token punctuation">:</span> String<span class="token punctuation">,</span>
    idade<span class="token punctuation">:</span> Number<span class="token punctuation">,</span>
    email<span class="token punctuation">:</span> String
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">// Criar o modelo do usuário</span>
<span class="token keyword">const</span> Usuario <span class="token operator">=</span> mongoose<span class="token punctuation">.</span><span class="token function">model</span><span class="token punctuation">(</span><span class="token string">'Usuario'</span><span class="token punctuation">,</span> usuarioSchema<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>usuarioSchema</code></strong>: Define como os documentos de “Usuários” serão armazenados no MongoDB (com nome, idade e email).</li>
<li><strong><code>Usuario</code></strong>: Um modelo Mongoose para realizar operações com a coleção “Usuários”.</li>
</ul>
<hr>
<h4 id="criando-um-documento-no-mongodb-create"><strong>2. Criando um Documento no MongoDB (Create)</strong></h4>
<p><strong>Passo 1:</strong> Adicione o seguinte código no <code>app.js</code> para criar um novo usuário no banco de dados:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// Criar um novo usuário</span>
<span class="token keyword">const</span> novoUsuario <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token class-name">Usuario</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
    nome<span class="token punctuation">:</span> <span class="token string">"João"</span><span class="token punctuation">,</span>
    idade<span class="token punctuation">:</span> <span class="token number">30</span><span class="token punctuation">,</span>
    email<span class="token punctuation">:</span> <span class="token string">"joao@email.com"</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">// Salvar o usuário no banco de dados</span>
novoUsuario<span class="token punctuation">.</span><span class="token function">save</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Usuário criado com sucesso!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token punctuation">(</span>error<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">error</span><span class="token punctuation">(</span><span class="token string">"Erro ao criar usuário:"</span><span class="token punctuation">,</span> error<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>novoUsuario.save()</code></strong>: Este método salva o novo documento de usuário no MongoDB.</li>
</ul>
<hr>
<h4 id="lendo-documentos-do-mongodb-read"><strong>3. Lendo Documentos do MongoDB (Read)</strong></h4>
<p><strong>Passo 1:</strong> Adicione o código para ler todos os usuários do banco de dados:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// Ler todos os usuários</span>
Usuario<span class="token punctuation">.</span><span class="token function">find</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token punctuation">(</span>usuarios<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Usuários encontrados:"</span><span class="token punctuation">,</span> usuarios<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token punctuation">(</span>error<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">error</span><span class="token punctuation">(</span><span class="token string">"Erro ao buscar usuários:"</span><span class="token punctuation">,</span> error<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>Usuario.find()</code></strong>: Busca todos os documentos da coleção “Usuários” e os exibe.</li>
</ul>
<hr>
<h4 id="atualizando-um-documento-no-mongodb-update"><strong>4. Atualizando um Documento no MongoDB (Update)</strong></h4>
<p><strong>Passo 1:</strong> Adicione o código para atualizar a idade de um usuário:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// Atualizar a idade de um usuário</span>
Usuario<span class="token punctuation">.</span><span class="token function">updateOne</span><span class="token punctuation">(</span><span class="token punctuation">{</span> nome<span class="token punctuation">:</span> <span class="token string">"João"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token punctuation">{</span> idade<span class="token punctuation">:</span> <span class="token number">35</span> <span class="token punctuation">}</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Usuário atualizado com sucesso!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token punctuation">(</span>error<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">error</span><span class="token punctuation">(</span><span class="token string">"Erro ao atualizar usuário:"</span><span class="token punctuation">,</span> error<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>Usuario.updateOne()</code></strong>: Atualiza um documento com base no nome “João” e define a nova idade como 35.</li>
</ul>
<hr>
<h4 id="excluindo-um-documento-do-mongodb-delete"><strong>5. Excluindo um Documento do MongoDB (Delete)</strong></h4>
<p><strong>Passo 1:</strong> Adicione o código para excluir um usuário do banco de dados:</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token comment">// Excluir um usuário</span>
Usuario<span class="token punctuation">.</span><span class="token function">deleteOne</span><span class="token punctuation">(</span><span class="token punctuation">{</span> nome<span class="token punctuation">:</span> <span class="token string">"João"</span> <span class="token punctuation">}</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token function">then</span><span class="token punctuation">(</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Usuário excluído com sucesso!"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span>
    <span class="token punctuation">.</span><span class="token keyword">catch</span><span class="token punctuation">(</span><span class="token punctuation">(</span>error<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
        console<span class="token punctuation">.</span><span class="token function">error</span><span class="token punctuation">(</span><span class="token string">"Erro ao excluir usuário:"</span><span class="token punctuation">,</span> error<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Explicação:</strong></p>
<ul>
<li><strong><code>Usuario.deleteOne()</code></strong>: Exclui um documento com o nome “João” do banco de dados.</li>
</ul>
<hr>
<h3 id="conclusão"><strong>Conclusão</strong></h3>
<p>Ao final do Dia 2, o aluno terá aprendido como configurar o MongoDB, conectar o Node.js ao banco de dados usando o Mongoose, e realizar operações CRUD básicas, como criar, ler, atualizar e excluir documentos. Essas operações são fundamentais para qualquer aplicação que interaja com um banco de dados.</p>

