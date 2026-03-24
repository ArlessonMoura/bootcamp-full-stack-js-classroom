## 🛠️ O Essencial: Git & GitHub para Devs Full Stack

### 1. O Ponto de Partida (Setup)
Tudo começa criando o repositório ou trazendo um projeto existente para sua máquina.

* `git init`: Cria o "cérebro" do Git na sua pasta local.
* `git clone <url>`: Copia um projeto do GitHub para o seu computador. **(O mais comum em times)**.
* `git remote add origin <url>`: Conecta seu código local a um repositório vazio no GitHub.

---

### 2. O Ciclo de Desenvolvimento Local
Imagine que você acabou de criar um novo componente React ou uma rota na sua API em Go.

* `git status`: **O comando de ouro.** Use sempre para saber em que pé as coisas estão.
* `git add .`: Prepara todas as suas alterações (o "staging area").
* `git commit -m "feat: adiciona componente de login"`: Cria um marco no tempo.
    > **Dica de Aula:** Ensine sobre "Commits Semânticos" (feat, fix, docs). Ajuda muito na organização de projetos grandes.

---

### 3. Organização com Branches (Onde a mágica acontece)
Nunca trabalhamos direto na `main`. Criamos "ramais" para não quebrar o código que já está rodando.

* `git branch <nome-da-feature>`: Cria uma nova ramificação.
* `git checkout -b <nome>`: Atalho para criar e já entrar na branch nova.
* `git branch -a`: Lista todas as branches (locais e remotas).

---

### 4. Interação com o Mundo (GitHub)
Agora é hora de subir seu código para o time revisar ou para fazer o deploy.

* **`git push origin <branch>`**: Envia sua branch local para o GitHub.
* **`git pull origin main`**: Traz as atualizações que outros colegas fizeram para o seu PC.
* **`git fetch`**: "Dá uma espiadinha" no que tem de novo no servidor sem alterar nada no seu código ainda.

---

### 5. Resgate e Segurança (O "Socorro!")
Errar faz parte do dia a dia de quem coda.

* `git restore <arquivo>`: Desfaz mudanças em um arquivo que ainda não foi "commitado".
* `git checkout .`: Descarta **todas** as mudanças locais não salvas (cuidado!).
* `git log --oneline`: Mostra um histórico resumido para você achar onde as coisas estavam funcionando.

---

### 💡 Exemplo de um Fluxo Real (Workflow)
Para um iniciante, o fluxo visual ajuda a fixar:
1.  `git checkout -b feature-x` (Cria branch)
2.  *Escreve o código*
3.  `git add .` + `git commit` (Salva local)
4.  `git push origin feature-x` (Sobe pro GitHub)
5.  **Abrir um Pull Request (PR)** no site do GitHub (Para o Senior revisar).

---