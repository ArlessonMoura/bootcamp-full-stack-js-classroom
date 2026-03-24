## 🚀 Lab: Do Zero ao Primeiro Pull Request

### Fase 1: O "Mundo Local" (Git)
Nesta etapa, o aluno prepara o ambiente e faz as primeiras alterações.

1.  **Criar a pasta do projeto:**
    ```bash
    mkdir projeto-fullstack && cd projeto-fullstack
    ```
2.  **Iniciar o Git:**
    ```bash
    git init
    ```
3.  **Criar um arquivo inicial (Simulando o Backend ou Frontend):**
    ```bash
    echo "<h1>Meu Projeto Full Stack</h1>" > index.html
    ```
4.  **O primeiro registro no tempo:**
    ```bash
    git add index.html
    git commit -m "docs: setup inicial do projeto"
    ```

---

### Fase 2: Organização Profissional (Branches)
Um dev Full Stack nunca mexe na `main` diretamente. Vamos criar uma funcionalidade.

1.  **Criar e entrar em uma nova branch:**
    ```bash
    git checkout -b feat/estilizacao
    ```
2.  **Simular uma alteração (Ex: Adicionar CSS):**
    ```bash
    echo "body { background: #f0f0f0; }" > style.css
    ```
3.  **Salvar a funcionalidade:**
    ```bash
    git add .
    git commit -m "feat: adiciona estilos basicos"
    ```

---

### Fase 3: Conexão com o "Mundo Externo" (GitHub)
Agora vamos levar o código do computador para a nuvem.

1.  **Criar o repositório no GitHub:**
    * Vá em [github.com/new](https://github.com/new).
    * Nome: `projeto-fullstack`.
    * **Não** marque "Add a README" ou ".gitignore" agora.
2.  **Conectar o PC ao GitHub:**
    *(Copie a linha que o GitHub mostrar, algo como:)*
    ```bash
    git remote add origin https://github.com/SEU_USUARIO/projeto-fullstack.git
    ```
3.  **Enviar a Main e a Feature:**
    ```bash
    git push -u origin main
    git push origin feat/estilizacao
    ```

---

### Fase 4: O Ritual do Dev (Pull Request)
No navegador, peça para os alunos:
1.  Abrir o repositório no GitHub.
2.  Clicar no botão amarelo **"Compare & pull request"**.
3.  Escrever uma breve descrição do que foi feito.
4.  **Simular a revisão:** Como se o Senior estivesse olhando o código antes de aprovar.

---

### 💡 Desafio Extra (O "Vida Real")
Para os alunos que terminarem rápido:
* voltem para a `main` localmente (`git checkout main`).
* Criar um arquivo `README.md` direto pelo site do GitHub.
* Dar um `git pull origin main` no terminal para ver o arquivo "aparecer" magicamente na sua máquina.
