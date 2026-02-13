# 📘 Introdução ao CSS

CSS pode ser aplicado no HTML de **3 formas principais**:

---

# 🎯 1️⃣ CSS Inline (dentro da própria tag)

Você escreve o CSS diretamente no atributo `style` do elemento.

```html
<p style="color: blue; font-size: 18px;">
  Texto azul
</p>
```

## ✅ Como funciona

O estilo é aplicado **apenas naquele elemento específico**.

📌 Profissionalmente: evite em projetos reais.

---

# 🎯 2️⃣ CSS Interno (tag `<style>`)

Você coloca o CSS dentro do `<head>` do HTML.

```html
<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>
```

## ✅ Como funciona

O CSS vale para **aquela página inteira**.

📌 Melhor que inline, mas ainda não é o ideal para projetos grandes.

---

# 🎯 3️⃣ CSS Externo (arquivo separado) ⭐⭐⭐ (Padrão profissional)

Você cria um arquivo separado, por exemplo:

```
styles.css
```

Dentro dele:

```css
p {
  color: blue;
}
```

E conecta no HTML:

```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

## ✅ Como funciona

* Pode ser usado em várias páginas
* Mantém separação clara entre HTML e CSS
* Facilita manutenção
* Permite cache do navegador (melhor performance)

📌 Esse é o padrão moderno.

---

# 🎯 Principais Seletores CSS

CSS é basicamente:

> **Selecionar → Estilizar**

Dominar seletores é dominar como você conversa com o DOM.

---

# 1️⃣ Seletores Básicos

---

## 1.1 🔹 Universal `*`

```css
* {
  margin: 0;
}
```

Seleciona **todos os elementos da página**.

Exemplo:

```html
<div>
  <p>Texto</p>
</div>
```

Tanto `<div>` quanto `<p>` recebem `margin: 0`.

📌 Uso comum: reset global.

---

## 1.2 🔹 Por Tag

```css
p {
  color: blue;
}
```

Seleciona todas as tags `<p>`.

Exemplo:

```html
<p>Primeiro</p>
<p>Segundo</p>
```

Ambos ficam azuis.

📌 Ideal para estilos base (tipografia).

---

## 1.3 🔹 Por Classe

```css
.card {
  background: gray;
}
```

Seleciona qualquer elemento com:

```html
<div class="card"></div>
<section class="card"></section>
```

📌 Pode ser reutilizada várias vezes.

---

## 1.4 🔹 Por ID

```css
#main {
  width: 100%;
}
```

Seleciona:

```html
<div id="main"></div>
```

⚠️ Deve ser único na página.

---

# 🌍 Diferença entre `*`, `html` e `:root`

Esse costuma gerar confusão.

---

## 🔹 `*` (Universal)

Seleciona tudo.

```css
* {
  box-sizing: border-box;
}
```

Aplica a TODOS os elementos.

Especificidade: 0-0-0

---

## 🔹 `html`

Seleciona apenas:

```html
<html>
```

Exemplo:

```css
html {
  font-size: 16px;
}
```

Usado para definir base da aplicação.

Especificidade: 0-0-1

---

## 🔹 `:root`

Seleciona o elemento raiz do documento.

Em HTML:

```
:root === html
```

Mas possui maior especificidade.

Exemplo clássico:

```css
:root {
  --primary-color: blue;
}
```

📌 É o lugar ideal para variáveis globais.

Especificidade: 0-1-0 (mais forte que `html`)

---

# 2️⃣ Seletores Combinadores

Selecionam com base na estrutura.

---

## 2.1 🔹 Descendente (espaço)

```css
div p {
  color: red;
}
```

Seleciona `<p>` dentro de `<div>` em qualquer nível.

```html
<div>
  <section>
    <p>Fica vermelho</p>
  </section>
</div>
```

---

## 2.2 🔹 Filho Direto (`>`)

```css
div > p {
  color: green;
}
```

Seleciona apenas filhos diretos.

```html
<div>
  <p>Selecionado</p>
  <section>
    <p>Não selecionado</p>
  </section>
</div>
```

---

## 2.3 🔹 Irmão Adjacente (`+`)

```css
h1 + p {
  color: purple;
}
```

Seleciona o primeiro `<p>` imediatamente após `<h1>`.

---

## 2.4 🔹 Irmãos Gerais (`~`)

```css
h1 ~ p {
  color: orange;
}
```

Seleciona todos os `<p>` após `<h1>` no mesmo nível.

---

# 3️⃣ Agrupamento

```css
h1, h2, h3 {
  font-family: Arial;
}
```

Aplica a mesma regra para vários seletores.

---

# 4️⃣ Múltiplas Classes

```css
.card.active {
  border: 2px solid green;
}
```

Seleciona apenas:

```html
<div class="card active"></div>
```

Mas NÃO:

```html
<div class="card"></div>
```

---

# 5️⃣ Seletores de Atributo

---

## 5.1 Igualdade

```css
input[type="text"] {
  border: 1px solid black;
}
```

Seleciona apenas inputs do tipo texto.

---

## 5.2 Exemplos úteis

```css
a[target]          /* possui target */
a[href^="https"]   /* começa com https */
a[href$=".com"]    /* termina com .com */
a[href*="google"]  /* contém google */
```

---

# 6️⃣ Pseudo-classes

---

## 6.1 Estados

```css
a:hover {
  color: red;
}
```

* `:hover` → mouse em cima
* `:focus` → foco
* `:active` → clique
* `:visited` → link visitado

---

## 6.2 Estruturais

```css
li:first-child
li:last-child
```

---

## 6.3 🔢 `:nth-child(n)` (Explicação Didática)

Seleciona um elemento baseado na posição dentro do pai.

### Exemplo simples:

```css
li:nth-child(2) {
  color: red;
}
```

HTML:

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

Resultado:

* Apenas "Item 2" fica vermelho.

---

### ⚠️ Ponto importante

Ele conta TODOS os filhos do pai.

```html
<ul>
  <li>Item 1</li>
  <div></div>
  <li>Item 2</li>
</ul>
```

Agora:

```css
li:nth-child(2)
```

Não funciona, porque o segundo filho é `<div>`.

---

### Fórmulas úteis

```css
li:nth-child(odd)   /* ímpares */
li:nth-child(even)  /* pares */
li:nth-child(2n)    /* pares */
li:nth-child(3n)    /* múltiplos de 3 */
```

Exemplo real:

```css
li:nth-child(odd) {
  background: #eee;
}
```

Cria efeito zebra em listas.

---

# 7️⃣ Pseudo-elementos

Pseudo-elementos criam ou estilizam partes internas do elemento.
---
## 7.1 🔥 `::before`

```css
p::before {
  content: "🔥 ";
}
```

HTML:

```html
<p>Texto</p>
```

Renderiza como se fosse:

```
🔥 Texto
```

⚠️ `content` é obrigatório.

Uso real:

```css
.required::after {
  content: "*";
  color: red;
}
```

Mostra um asterisco automático em campos obrigatórios.

---

## 7.2 🔥 `::after`

```css
.card::after {
  content: " Novo";
  color: green;
}
```

Adiciona texto após o conteúdo.

Muito usado para:

* Badges
* Indicadores visuais
* Linhas decorativas

---

## 7.3 `::first-letter`

```css
p::first-letter {
  font-size: 2rem;
  font-weight: bold;
}
```

Apenas a primeira letra do parágrafo é alterada.

---

## 7.4 `::first-line`

```css
p::first-line {
  color: blue;
}
```

Apenas a primeira linha visual do texto.

Se o layout mudar, a linha muda.

---

## 7.5 `::selection`

```css
::selection {
  background: black;
  color: white;
}
```

Estiliza texto selecionado pelo usuário.

---

# 8️⃣ 🔥 Especificidade

Ordem de força:

1. `!important`
2. Inline style
3. ID
4. Classe / atributo / pseudo-classe
5. Tag

Exemplo:

```css
#main { color: red; }
.container { color: blue; }
```

O ID vence.

---

# 🏆 Se você dominar os conceitos abaixo, já está no top 80%

* Classe
* Descendente
* Filho direto
* Atributo
* `:nth-child`
* Pseudo-elementos
* Especificidade

---

# 🎯 O que é Reset CSS?

Todo navegador (Chrome, Firefox, Edge…) aplica **estilos padrão** aos elementos HTML.

Exemplo:

* `<body>` tem margin padrão
* `<h1>` tem font-size grande
* `<ul>` tem padding e bullets
* `<button>` tem estilo próprio

Isso se chama **User Agent Stylesheet**.

👉 O problema: cada navegador tem pequenas diferenças.

**Reset CSS serve para zerar essas diferenças e começar do zero.**

---

# 🧠 Por que isso é importante?

Sem reset:

* Layouts quebram entre navegadores
* Margens aparecem “do nada”
* Elementos têm comportamento inconsistente

Com reset:

> Você controla tudo desde a base.

---

# 🔹 Forma 1 — Reset Simples (Clássico)

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

## O que isso faz?

* Remove todas as margens
* Remove todos os paddings
* Faz o `box-sizing` funcionar de forma previsível

---

## 🔥 Sobre `box-sizing`

Sem isso:

```
width = content + padding + border
```

Com `border-box`:

```
width = já inclui padding e border
```

Isso evita bugs de layout.

---

# 🔹 Forma 2 — Reset Mais Completo

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: sans-serif;
}

h1, h2, h3, h4, h5, h6, p {
  margin: 0;
}

ul, ol {
  list-style: none;
  padding: 0;
}
```

### Por que incluir `::before` e `::after`?

Pseudo-elementos também precisam de `box-sizing` consistente.

---

# 🔹 Forma 3 — Normalize.css (abordagem moderna)

Ao invés de zerar tudo, o **Normalize** apenas padroniza diferenças entre navegadores.

Diferença conceitual:

* Reset → zera tudo
* Normalize → corrige inconsistências

---

# 🏗 Reset Profissional (Boa prática moderna)

Hoje muitos projetos usam algo assim:

```css
/* 1. Box sizing universal */
*, *::before, *::after {
  box-sizing: border-box;
}

/* 2. Remove margens padrão */
body, h1, h2, h3, p, figure {
  margin: 0;
}

/* 3. Remove estilos de lista */
ul[role="list"],
ol[role="list"] {
  list-style: none;
}

/* 4. Melhorar renderização de texto */
body {
  min-height: 100vh;
  line-height: 1.5;
}

/* 5. Tornar imagens responsivas */
img, picture {
  max-width: 100%;
  display: block;
}
```

# 🦾 Reset Que Uso (Simples, tiro e queda!)

```css
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: MontSerrat;
  font-size: clamp(1rem, 2vw, 2rem);
}
```

---

# ⚠️ O que NÃO fazer

❌ Não use reset agressivo em tudo sem saber o impacto
❌ Não remova outline sem substituir (acessibilidade)
❌ Não remova foco de botão sem alternativa

---

# 🧠 Quando usar Reset?

* Sempre no início de projetos
* Antes de criar design system
* Em aplicações web modernas

---

# 🎯 1️⃣ Box Model (Base de Tudo)

Essas são as propriedades mais importantes do CSS.

---

## 🔹 `width` / `height`

Define largura e altura.

```css
.card {
  width: 300px;
  height: 200px;
}
```

---

## 🔹 `margin`

Espaço externo (afasta elementos).

```css
.card {
  margin: 20px;
}
```

Shorthand:

```css
margin: top right bottom left;
margin: 10px 20px;
```

---

## 🔹 `padding`

Espaço interno (entre borda e conteúdo).

```css
.card {
  padding: 16px;
}
```

---

## 🔹 `border`

Define borda.

```css
.card {
  border: 2px solid black;
}
```

---

## 🔥 `box-sizing`

Muito importante.

```css
box-sizing: border-box;
```

Faz a largura incluir padding e border.

---

# 🎨 2️⃣ Texto e Tipografia

---

## 🔹 `color`

Cor do texto.

```css
p {
  color: blue;
}
```

---

## 🔹 `font-size`

```css
p {
  font-size: 18px;
}
```

---

## 🔹 `font-family`

```css
body {
  font-family: Arial, sans-serif;
}
```

---

## 🔹 `font-weight`

```css
strong {
  font-weight: bold;
}
```

---

## 🔹 `text-align`

```css
p {
  text-align: center;
}
```

---

## 🔹 `line-height`

Controla altura da linha.

```css
p {
  line-height: 1.5;
}
```

---

# 🎨 3️⃣ Cores e Fundo

---

## 🔹 `background-color`

```css
.card {
  background-color: gray;
}
```

---

## 🔹 `background-image`

```css
.hero {
  background-image: url("bg.jpg");
}
```

---

## 🔹 `background`

Shorthand poderosa:

```css
background: url("bg.jpg") center/cover no-repeat;
```

---

# 📐 4️⃣ Layout (Essencial Moderno)

---

## 🔹 `display`

Define comportamento do elemento.

```css
display: block;
display: inline;
display: flex;
display: grid;
```

Mais usados hoje:

* `flex`
* `grid`

---

## 🔹 `position`

Controla posicionamento.

```css
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

---

## 🔹 `top`, `left`, `right`, `bottom`

Usados com `position`.

```css
.box {
  position: absolute;
  top: 10px;
  left: 20px;
}
```

---

## 🔹 `overflow`

Controla conteúdo que ultrapassa limites.

```css
overflow: hidden;
overflow: auto;
```

---

# 🔥 5️⃣ Flexbox (Muito Importante)

---

## 🔹 `display: flex`

```css
.container {
  display: flex;
}
```

---

## 🔹 `justify-content`

Alinhamento horizontal.

```css
justify-content: center;
space-between;
```

---

## 🔹 `align-items`

Alinhamento vertical.

```css
align-items: center;
```

---

## 🔹 `gap`

Espaço entre itens.

```css
gap: 16px;
```

---

# 🧱 6️⃣ Grid (Layout Avançado)

---

## 🔹 `display: grid`

```css
.container {
  display: grid;
}
```

---

## 🔹 `grid-template-columns`

```css
grid-template-columns: 1fr 1fr 1fr;
```

---

## 🔹 `grid-template-rows`

```css
grid-template-rows: auto auto;
```

---

## 🔹 `gap`

Também funciona no grid.

---

# ✨ 7️⃣ Efeitos Visuais

---

## 🔹 `box-shadow`

```css
box-shadow: 0 4px 10px rgba(0,0,0,0.2);
```

---

## 🔹 `border-radius`

```css
border-radius: 8px;
```

---

## 🔹 `opacity`

```css
opacity: 0.5;
```

---

## 🔹 `transition`

Cria animação suave.

```css
button {
  transition: background 0.3s ease;
}
```

---

# 🎬 8️⃣ Transformações

---

## 🔹 `transform`

```css
transform: scale(1.2);
transform: rotate(45deg);
transform: translateX(20px);
```

---

# 🧠 Ordem de importância prática (para dominar primeiro)

1. Box model
2. Display (flex e grid)
3. Position
4. Tipografia
5. Cores
6. Transições
7. Transform

---

# 🏆 Se você dominar o que foi mostrado até aqui, já constrói 90% dos layouts modernos.

---

# 🧠 O que são variáveis CSS?

São propriedades customizadas que começam com `--` e são acessadas com `var()`.

Elas ajudam em:

* 🎨 Padronização de cores
* 📏 Controle de espaçamentos
* 🌙 Temas (dark/light)
* 🔁 Manutenção escalável

---

# ⚙️ 1️⃣ Como criar uma variável CSS

Normalmente criamos dentro do `:root`.

```css
:root {
  --primary-color: #3498db;
}
```

👉 `:root` representa o elemento `<html>` e funciona como um escopo global.

---

# ▶️ Como usar a variável

```css
button {
  background-color: var(--primary-color);
}
```

🔁 Fluxo mental:

* Define → `--primary-color`
* Usa → `var(--primary-color)`

---

# 🎯 Exemplo didático completo

```html
<style>
  :root {
    --primary-color: #2ecc71;
    --spacing: 16px;
  }

  .card {
    background-color: var(--primary-color);
    padding: var(--spacing);
    color: white;
  }
</style>

<div class="card">
  Card estilizado com variáveis
</div>
```

Se você mudar `--primary-color`, todos os elementos que usam essa variável mudam juntos.

---

# 📦 2️⃣ Escopo local (variável só dentro de um bloco)

Você pode declarar variáveis dentro de um seletor específico:

```css
.container {
  --box-color: coral;
}

.box {
  background-color: var(--box-color);
}
```

⚠️ Aqui funciona **apenas se `.box` estiver dentro de `.container`**, porque variáveis respeitam herança.

---

# 🔥 3️⃣ Valor padrão (fallback)

Se a variável não existir:

```css
color: var(--text-color, black);
```

Se `--text-color` não estiver definida → usa `black`.

---

# 🌗 4️⃣ Exemplo clássico: Tema Dark Mode

```css
:root {
  --bg-color: white;
  --text-color: black;
}

.dark {
  --bg-color: #111;
  --text-color: white;
}

body {
  background-color: var(--bg-color);
  color: var(--text-color);
}
```

Quando você adiciona a classe `.dark` no `<body>`:

```html
<body class="dark">
```

🔥 O tema inteiro troca automaticamente.

---

# ⚡ Conceito importante (que muita gente não entende)

Variáveis CSS:

* São **dinâmicas**
* Funcionam em runtime
* Podem ser alteradas via JavaScript

# 🏗️ Boas práticas (pensando como dev)

```css
:root {
  /* Colors */
  --color-primary: #3498db;
  --color-secondary: #2ecc71;

  /* Spacing */
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;

  /* Font sizes */
  --font-base: 16px;
  --font-title: 24px;
}
```

Separar por domínio melhora legibilidade e manutenção.

---

# 🎯 O que são `@rules`?

São regras que começam com `@` e controlam:

* Importação
* Responsividade
* Animações
* Fontes
* Camadas
* Suporte condicional
* Escopo

---

# 📚 Principais `@rules` (com explicações claras)

---

# 1️⃣ `@import`

Importa outro arquivo CSS.

```css
@import url("reset.css");
```

📌 Funciona como:

> “Inclua o conteúdo desse arquivo aqui”

⚠️ Não é recomendado em produção moderna
Melhor usar `<link>` no HTML (mais performático).

---

# 2️⃣ `@media` (Responsividade)

A mais importante no dia a dia.

Permite aplicar CSS com base em condições.

```css
@media (max-width: 768px) {
  body {
    background: lightgray;
  }
}
```

Significa:

> “Aplique essas regras somente se a tela for menor que 768px”

---

### 🔥 Exemplo prático

```css
.card {
  width: 400px;
}

@media (max-width: 600px) {
  .card {
    width: 100%;
  }
}
```

Desktop → 400px
Mobile → 100%

---

# 3️⃣ `@keyframes` (Animações)

Define animações.

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
```

Depois aplica:

```css
.box {
  animation: fadeIn 1s ease-in;
}
```

📌 `@keyframes` define
📌 `animation` usa

---

# 4️⃣ `@font-face`

Importa fontes customizadas.

```css
@font-face {
  font-family: "MinhaFonte";
  src: url("minhafonte.woff2") format("woff2");
}
```

Depois:

```css
body {
  font-family: "MinhaFonte";
}
```

---

# 5️⃣ `@supports` (Feature Query)

Aplica CSS somente se o navegador suportar determinada feature.

```css
@supports (display: grid) {
  .container {
    display: grid;
  }
}
```

Significa:

> “Se o navegador suportar grid, use grid”

---

# 6️⃣ `@layer` (CSS moderno)

Organiza prioridades em camadas.

```css
@layer base {
  body {
    margin: 0;
  }
}

@layer components {
  .card {
    padding: 1rem;
  }
}
```

Ajuda a controlar especificidade de forma mais previsível.

Muito usado em frameworks modernos.

---

# 7️⃣ `@scope` (Novo, experimental)

Define escopo local de estilos.

```css
@scope (.card) {
  p {
    color: red;
  }
}
```

O `p` só será vermelho dentro de `.card`.

---

# 🧠 Diferença importante

Seletores normais:

```css
.card { }
div p { }
```

Selecionam elementos.

At-rules:

```css
@media
@keyframes
@font-face
```

Controlam **quando ou como o CSS será aplicado**.

---

# 🎯 Resumo Mental

| @rule        | Serve para          |
| ------------ | ------------------- |
| `@import`    | Importar CSS        |
| `@media`     | Responsividade      |
| `@keyframes` | Animações           |
| `@font-face` | Fontes customizadas |
| `@supports`  | Verificar suporte   |
| `@layer`     | Organização         |
| `@scope`     | Escopo local        |

---

# 📱🎯 O que é Responsividade?

Agora vamos subir um nível. 🚀
Se você dominar isso, você deixa de “fazer layout” e passa a **projetar sistemas adaptáveis**.

##### Responsividade é a capacidade de um layout **se adaptar a diferentes tamanhos de tela**:

* 📱 Celular
* 📲 Tablet
* 💻 Notebook
* 🖥️ Desktop
* 📺 Telas grandes

Não é apenas “diminuir coisas”.
É **reorganizar estrutura, espaçamentos e comportamento**.

---

# 🧠 Conceito Fundamental

Antes da responsividade existia:

> Layout fixo (ex: width: 1200px)

Hoje usamos:

> Layout fluido + media queries + unidades flexíveis

---

# 📐 1️⃣ Medidas Responsivas

Existem dois grandes grupos de unidades:

---

## 🔹 1.1 Unidades Absolutas (evitar para layout)

```css
width: 300px;
```

* `px`
* `pt`
* `cm`
* `mm`

👉 São fixas.
Não se adaptam.

Use `px` com consciência.

---

## 🔹 1.2 Unidades Relativas (Essenciais)

### 📌 `%` (porcentagem)

Relativa ao elemento pai.

```css
.container {
  width: 100%;
}
```

Se o pai tiver 500px → 100% = 500px.

---

### 📌 `em`

Relativa ao `font-size` do elemento pai.

```css
font-size: 2em;
```

Se o pai tiver 16px → 2em = 32px.

⚠️ Pode acumular (cascata).

---

### 📌 `rem` ⭐ (mais usada hoje)

Relativa ao `font-size` do `html`.

```css
font-size: 1.5rem;
```

Se `html { font-size: 16px }`

→ 1.5rem = 24px

📌 Muito mais previsível que `em`.

---

### 📌 `vw` (viewport width)

1vw = 1% da largura da tela

```css
width: 50vw;
```

Se a tela tem 1000px → 50vw = 500px.

---

### 📌 `vh` (viewport height)

1vh = 1% da altura da tela.

```css
height: 100vh;
```

Muito usado para hero sections.

---

### 📌 `clamp()` ⭐⭐⭐ (moderno e poderoso)

Permite limitar crescimento.

```css
font-size: clamp(1rem, 2vw, 2rem);
```

Significa:

* Mínimo: 1rem
* Ideal: 2vw
* Máximo: 2rem

🔥 Isso cria tipografia fluida automática.

---

# 📱 2️⃣ Media Queries (`@media`)

Permitem aplicar CSS baseado em condições.

---

## 🔹 Exemplo básico

```css
@media (max-width: 768px) {
  body {
    background: lightgray;
  }
}
```

Significa:

> Se a tela for menor ou igual a 768px, aplique isso.

---

## 🔹 Breakpoints comuns

Não são regras fixas, mas padrões populares:

* 480px → celulares pequenos
* 768px → tablets
* 1024px → laptops
* 1280px+ → desktops

---

## 🔥 Exemplo real de adaptação

```css
.container {
  display: flex;
  gap: 20px;
}

@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

Desktop → elementos lado a lado
Mobile → elementos empilhados

---

# 📱 3️⃣ Mobile First (Abordagem Profissional Moderna)

Mobile First significa:

> Você começa estilizando para celular
> Depois adapta para telas maiores

---

## 🧠 Por que isso é melhor?

* Menos CSS
* Melhor performance
* Pensamento estruturado
* Mais fácil escalar

---

## 🔥 Exemplo Mobile First

### 1️⃣ Base (Mobile)

```css
.card {
  width: 100%;
  padding: 1rem;
}
```

Sem media query → já funciona no celular.

---

### 2️⃣ Expandindo para telas maiores

```css
@media (min-width: 768px) {
  .card {
    width: 50%;
  }
}
```

Note o uso de `min-width`.

📌 Mobile First usa `min-width`, não `max-width`.

---

# 🧠 Diferença Mental Importante

### ❌ Desktop First

```css
@media (max-width: 768px)
```

Você corrige para baixo.

---

### ✅ Mobile First

```css
@media (min-width: 768px)
```

Você adiciona melhorias para cima.

---

# 🏗️ Estrutura Profissional Exemplo

```css
/* 1. Base Mobile */
body {
  font-family: sans-serif;
}

.container {
  display: flex;
  flex-direction: column;
}

/* 2. Tablet */
@media (min-width: 768px) {
  .container {
    flex-direction: row;
  }
}

/* 3. Desktop */
@media (min-width: 1024px) {
  .container {
    gap: 2rem;
  }
}
```

Organizado e escalável.

---

# 📐 4️⃣ Layout Responsivo com Flexbox

Exemplo clássico:

```css
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.card {
  flex: 1 1 300px;
}
```

Significa:

* Cada card tenta ter 300px
* Se não couber → quebra linha automaticamente

🔥 Isso já é responsivo sem media query.

---

# 🧱 5️⃣ Grid Responsivo Automático

Muito poderoso:

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}
```

Isso cria:

* Colunas automáticas
* Nunca menores que 250px
* Expandem até ocupar espaço disponível

🔥 Responsividade quase automática.