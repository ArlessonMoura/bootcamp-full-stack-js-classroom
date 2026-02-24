# 🏝️ Desafio HTML — **A Ilha do Dev Perdido**

## 📖 Contexto (lúdico)

Você está preso em uma ilha deserta 🌴
A única forma de pedir resgate é criando uma **página HTML informativa** que será enviada via satélite.

Essa página precisa conter **todas as informações necessárias** para que o resgate aconteça com sucesso.

> ⚠️ **Regras da ilha:**
> ✅ Apenas HTML puro
> ✅ Usar **tags semânticas corretamente**

---

## 🎯 Objetivo do desafio

Criar um arquivo chamado:

```
resgate.html
```

Que represente uma **página completa**, bem estruturada, semântica e acessível.

---

## 🧱 Requisitos obrigatórios (Checklist Técnico)

### 1️⃣ Estrutura básica do HTML

A página **PRECISA** conter:

* `<!DOCTYPE html>`
* `<html>`
* `<head>`

  * `<meta charset="UTF-8">`
  * `<title>` com algo como: `Pedido de Resgate`
* `<body>`

---

### 2️⃣ Estrutura semântica (HTML5)

Organize a página usando as tags abaixo:

* `<header>`
* `<nav>`
* `<main>`
* `<section>`
* `<article>`
* `<aside>`
* `<footer>`

---

### 3️⃣ Conteúdo obrigatório da página

#### 🧭 `<header>`

* Um `<h1>` com o nome da página
* Um `<p>` explicando rapidamente a situação do náufrago

---

#### 🧭 `<main>`

##### 🔹 `<section>` — **Sobre o Náufrago**

* Um `<article>` com:

  * `<h2>`
  * `<p>`
  * Uso de `<strong>` e `<em>`
* Uma `<img>` representando o náufrago

  * **Obrigatório:** atributo `alt`

---

##### 🔹 `<section>` — **Localização da Ilha**

* Texto explicando onde você está
* Um `<hr>` separando visualmente o conteúdo
* Um link externo com `<a>` (ex: mapa fictício)

---

##### 🔹 `<section>` — **Suprimentos Disponíveis**

Criar **duas listas**:

* Uma `<ul>` com suprimentos básicos
* Uma `<ol>` com prioridades de resgate

---

##### 🔹 `<aside>`

Informações extras, curiosidades ou avisos:

* Exemplo: “Última mensagem enviada às 14h”
* Use `<span>` em algum trecho do texto

---

---

### 4️⃣ 📝 Formulário de Pedido de Resgate

Criar um formulário completo usando:

* `<form>`
* `<label>`
* `<input>` (tipos: `text`, `email`)
* `<textarea>`
* `<select>` com `<option>`
* `<button>`

📌 Campos sugeridos:

* Nome do náufrago
* Email de contato
* Nível de urgência (Baixo / Médio / Alto)
* Mensagem para a equipe de resgate

---

### 6️⃣ 🧭 `<footer>`

* Texto de encerramento
* Um `<br>`
* Um link externo (ex: “Organização Internacional de Resgate”)

---

## 🧠 Critérios de Avaliação

| Critério                        | Peso |
| ------------------------------- | ---- |
| Uso correto das tags semânticas | ⭐⭐⭐⭐ |
| Estrutura HTML válida           | ⭐⭐⭐  |
| Clareza do conteúdo             | ⭐⭐⭐  |
| Organização e hierarquia        | ⭐⭐⭐⭐ |
| Criatividade                    | ⭐⭐   |

---

## 🏆 Bônus (opcional)

💡 Ganha destaque quem:

* Usar corretamente **IDs para navegação** (quem se adiantar a lógica de ancoras html com links <a></a>)
* Mantiver hierarquia correta de `<h1>` a `<h3>`
* 🎥 Mídia Adicionar **pelo menos UM** dos itens:
    * `<audio>`
    * `<video>`
> Com uso da tag: `<source>`
* Criar uma história envolvente 😄

---

## 🧪 Resultado esperado

Ao abrir o `resgate.html` no navegador, deve parecer:

* Uma **página real**
* Com início, meio e fim
* Organizada
* Semântica
* Legível sem nenhum estilo
