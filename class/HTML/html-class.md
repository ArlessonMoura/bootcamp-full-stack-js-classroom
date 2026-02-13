# Introdução ao HTML

---

## 🧱 Estrutura básica

Essas são obrigatórias em praticamente todo HTML.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Título da página</title>
  </head>
  <body>
    Conteúdo visível
  </body>
</html>
```

* `<html>` → raiz do documento
* `<head>` → metadados (não aparece na tela)
* `<body>` → conteúdo da página
* `<title>` → título da aba
* `<meta>` → configurações (charset, viewport, SEO)

---

## 🧭 Semântica (HTML5 – **importantíssimo**)

Ajuda acessibilidade, SEO e organização.

* `<header>` → cabeçalho
* `<nav>` → navegação
* `<main>` → conteúdo principal
* `<section>` → seção temática
* `<article>` → conteúdo independente
* `<aside>` → conteúdo lateral
* `<footer>` → rodapé

👉 **Regra mental**: se faz sentido fora do contexto, é `article`.

---

## ✍️ Texto e conteúdo

* `<h1>` a `<h6>` → títulos (hierarquia importa!)
* `<p>` → parágrafo
* `<strong>` → importância (semântica)
* `<em>` → ênfase
* `<br>` → quebra de linha
* `<hr>` → separador temático

---

## 🔗 Links e mídia

* `<a>` → link
* `<img>` → imagem
* `<audio>` → áudio
* `<video>` → vídeo
* `<source>` → fonte de mídia

```html
<a href="https://google.com">Google</a>
<img src="img.png" alt="Descrição da imagem">
```

---

## 📋 Listas

* `<ul>` → lista não ordenada
* `<ol>` → lista ordenada
* `<li>` → item da lista

---

## 📦 Containers genéricos

* `<div>` → bloco (sem semântica)
* `<span>` → inline

⚠️ Use só quando **não existir uma tag semântica melhor**.

---

## 📝 Formulários

* `<form>` → formulário
* `<input>` → campo
* `<label>` → rótulo
* `<textarea>` → texto longo
* `<select>` / `<option>` → seleção
* `<button>` → botão

```html
<form>
  <label>Email</label>
  <input type="email">
  <button>Enviar</button>
</form>
```

---

## 📊 Tabelas

* `<table>` → tabela
* `<thead>`, `<tbody>`, `<tfoot>`
* `<tr>` → linha
* `<th>` → cabeçalho
* `<td>` → célula

---

## ⚙️ Scripts e estilos

* `<script>` → JavaScript
* `<link>` → CSS externo
* `<style>` → CSS interno

---

## 🧠 Dica de ouro (mentalidade moderna)

* **HTML = estrutura**
* **CSS = aparência**
* **JS = comportamento**

