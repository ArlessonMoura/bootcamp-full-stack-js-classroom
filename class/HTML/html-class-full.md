# 📘 HTML — Estrutura, Semântica e Formulários (Nível Arquitetura)

HTML **não é linguagem de layout**.

> HTML é linguagem de **estrutura, significado e contrato de dados**.

Ele define:

* Estrutura
* Hierarquia
* Semântica
* Acessibilidade
* Base para SEO
* Base para CSS
* Base para JavaScript
* Base para comunicação com o servidor

---

# 🧱 Estrutura Base (Documento HTML5)

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Descrição da página">
    <title>Título da página</title>
  </head>
  <body>
    Conteúdo visível
  </body>
</html>
```

---

## 🔍 Explicação Profunda

### `<!DOCTYPE html>`

Declara HTML5.

Sem isso → navegador entra em **quirks mode** (modo legado), alterando o comportamento de renderização.

---

### `<html lang="pt-BR">`

* Define idioma do documento
* Fundamental para leitores de tela
* Ajuda mecanismos de busca

---

### `<meta charset="UTF-8">`

Permite:

* Acentos
* Emojis
* Caracteres especiais

Sem isso → texto quebrado.

---

### `<meta name="viewport">`

Essencial para responsividade.

Sem ele, o mobile simula uma tela desktop.

---

### `<meta name="description">`

Resumo exibido no Google.
Não é fator direto de ranking, mas impacta CTR.

---

# 🧠 Arquitetura Semântica

Semântica = significado estrutural.

HTML5 introduziu elementos que descrevem intenção, não aparência.

---

## 🧭 Estrutura Moderna

```html
<header>
  <nav></nav>
</header>

<main>
  <section>
    <article></article>
  </section>
</main>

<aside></aside>

<footer></footer>
```

---

## 📌 Significado Real

### `<header>`

Cabeçalho da página ou de uma seção.
Pode existir mais de um.

---

### `<nav>`

Agrupa navegação principal.
Não é qualquer conjunto de links.

---

### `<main>`

Conteúdo principal da página.
Deve existir apenas um por documento.

---

### `<section>`

Agrupa conteúdo tematicamente relacionado.
Geralmente deve conter um título (`h2`, `h3`).

---

### `<article>`

Conteúdo independente.

Exemplos:

* Post
* Produto
* Comentário
* Notícia

Regra mental:

> Se pode existir fora do contexto → é `article`.

---

### `<aside>`

Conteúdo complementar:

* Sidebar
* Links relacionados
* Publicidade

---

### `<footer>`

Rodapé da página ou seção.

---

# ✍️ Texto e Hierarquia

HTML é hierárquico, não visual.

---

## 🔹 Títulos (`h1` a `h6`)

```html
<h1>Título principal</h1>
<h2>Subtítulo</h2>
<h3>Subseção</h3>
```

Hierarquia importa mais que tamanho.

Nunca use heading apenas para aumentar fonte.

---

## 🔹 Importância Semântica

```html
<strong>Importante</strong>
<em>Ênfase</em>
```

* `<strong>` = importância
* `<em>` = ênfase

Não é sobre negrito/itálico.

---

## 🔹 Elementos Inline Semânticos

```html
<mark>Destaque</mark>
<small>Texto secundário</small>
<cite>Obra</cite>
<abbr title="Cascading Style Sheets">CSS</abbr>
```

Melhoram acessibilidade e compreensão.

---

# 🔗 Links

```html
<a href="https://google.com">Google</a>
```

---

## 🔹 Segurança moderna

```html
<a href="https://exemplo.com" target="_blank" rel="noopener noreferrer">
  Abrir
</a>
```

Evita vulnerabilidade de manipulação da aba original.

---

# 🖼️ Imagens

```html
<img src="img.png" alt="Descrição da imagem">
```

`alt` é obrigação profissional.

Usado por:

* Leitores de tela
* SEO
* Quando imagem falha

---

## 🔹 Imagem Responsiva

```html
<img 
  src="small.jpg"
  srcset="small.jpg 480w, large.jpg 800w"
  sizes="(max-width: 600px) 480px, 800px"
  alt="Descrição">
```

Entrega imagem adequada ao tamanho da tela.

---

# 📋 Listas

### Não ordenada

```html
<ul>
  <li>Item</li>
</ul>
```

### Ordenada

```html
<ol>
  <li>Passo 1</li>
</ol>
```

### Lista de definição

```html
<dl>
  <dt>HTML</dt>
  <dd>Linguagem de marcação</dd>
</dl>
```

---

# 📦 Containers Genéricos

### `<div>`

Bloco sem significado.

### `<span>`

Inline sem significado.

Regra:

> Use apenas se nenhuma tag semântica fizer sentido.

---

# 📝 Formulários — Estrutura e Contrato de Dados

Formulários conectam HTML ao backend.

---

## 🔹 Estrutura Base

```html
<form action="/submit" method="POST">
  <label for="email">Email</label>
  <input id="email" name="email" type="email" required>

  <button type="submit">Enviar</button>
</form>
```

---

## 🧠 Anatomia de um `<input>`

Atributos essenciais:

* `type`
* `name` ⚠️ (sem ele não envia dado)
* `id`
* `value`
* `required`
* `placeholder`
* `readonly`
* `disabled`
* `autocomplete`

---

# 📅 Inputs de Data e Tempo

```html
<input type="date">
<input type="time">
<input type="datetime-local">
<input type="month">
<input type="week">
```

✔ Interface nativa
✔ Validação automática
✔ Melhor UX mobile

---

# 🔘 `type="radio"` — Escolha Única

Permite escolher apenas uma opção por grupo.

Radios pertencem ao mesmo grupo quando compartilham o mesmo `name`.

```html
<fieldset>
  <legend>Escolha seu plano</legend>

  <label>
    <input type="radio" name="plano" value="basico">
    Básico
  </label>

  <label>
    <input type="radio" name="plano" value="premium">
    Premium
  </label>
</fieldset>
```

### O que acontece:

* Apenas um pode ser selecionado
* O valor enviado será o `value` marcado
* `fieldset + legend` melhora acessibilidade

---

# ☑️ `type="checkbox"` — Escolha Múltipla

Permite múltiplas seleções.

```html
<label>
  <input type="checkbox" name="interesses[]" value="frontend">
  Front-end
</label>

<label>
  <input type="checkbox" name="interesses[]" value="backend">
  Back-end
</label>
```

Enviado ao backend como:

```
interesses = ["frontend", "backend"]
```

---

## 📌 Diferença Fundamental

| Tipo     | Pode marcar várias? | Precisa mesmo name? |
| -------- | ------------------- | ------------------- |
| radio    | ❌ Não               | ✅ Sim               |
| checkbox | ✅ Sim               | ❌ Não obrigatório   |

---

## 🔹 Marcado por padrão

```html
<input type="checkbox" checked>
```

---

# 🖱️ Botões

```html
<button type="submit">Enviar</button>
<button type="reset">Limpar</button>
<button type="button">Clique</button>
```

⚠ Se não definir `type`, o padrão é `submit`.

---

# ⚙️ Scripts e Performance

```html
<script src="app.js" defer></script>
```

* `async` → executa assim que carrega
* `defer` → executa após o HTML ser parseado

---

# ♿ Acessibilidade Profissional

```html
<button aria-label="Fechar menu">X</button>
```

Use ARIA quando a semântica padrão não for suficiente.

Prefira sempre tag semântica antes de usar `role`.

---

# 🧠 Mentalidade Profissional

HTML não é:

❌ Apenas visual
❌ Apenas marcação

HTML é:

✔ Estrutura
✔ Significado
✔ Acessibilidade
✔ SEO
✔ Performance
✔ Base de integração com backend

---

# 🏗️ Checklist Mental Antes de Escrever HTML

1. Qual é o conteúdo principal?
2. O que é independente?
3. O que é complementar?
4. O que é navegação?
5. A hierarquia está correta?
6. Os dados do formulário têm `name`?
7. Está acessível?

---

# 🏆 Resumo Final

* HTML = significado
* CSS = apresentação
* JS = comportamento
* Formulários = contrato de dados
* Semântica = arquitetura invisível
* Acessibilidade = responsabilidade
* Hierarquia = estrutura mental