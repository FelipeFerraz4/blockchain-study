# Guia do Git

O Git é um sistema de controle de versão distribuído que permite que equipes de desenvolvedores colaborem em projetos de software de forma eficiente.

## Conceitos Básicos


<!-- # Configura nome e e-mail do usuário
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@example.com"

# Verifica as configurações
git config --list

# Define editor de texto padrão
git config --global core.editor "code --wait"

# Cria um alias para git status
git config --global alias.st status -->

### 1. Repositório

Um **repositório** é o local onde o histórico de versões do seu projeto é armazenado. Ele contém todos os arquivos do projeto, além de informações sobre todas as mudanças feitas ao longo do tempo. Um repositório Git pode ser local (na sua máquina) ou remoto (hospedado em plataformas como GitHub, GitLab, Bitbucket, etc.).

- Comandos:
  - `git init`: Inicializa um novo repositório Git local.
  - `git clone [URL]`: Clona um repositório remoto para o seu ambiente local.

- Comandos de Configuração:
  - `git config --list`: Lista todas as configurações do Git atualmente definidas.
  - `git config --global user.name "Seu Nome"`: Configura o nome de usuário que será associado aos commits.
  - `git config --global user.email "seu.email@example.com"`: Configura o endereço de e-mail que será associado aos commits.


### 2. Commit

Um **commit** é uma captura de uma mudança no código. Ele salva as alterações feitas em um ou mais arquivos e cria um ponto de restauração no histórico do repositório. Cada commit tem uma mensagem associada, que descreve o que foi alterado.

- Comandos:
  - `git add [arquivo]`: Adiciona arquivos ao estágio (preparando-os para o commit).
  - `git commit -m "mensagem"`: Cria um commit com uma mensagem descritiva.
  - `git log`: Exibe o histórico de commits.

### 3. Branch

Um **branch** (ramo) é uma linha independente de desenvolvimento dentro do repositório. Ele permite que você trabalhe em funcionalidades ou correções separadas do código principal (geralmente a branch `main` ou `master`). Isso permite que diferentes versões do código sejam desenvolvidas simultaneamente.

- **Comandos:**
  - `git branch [nome-da-branch]`: Cria uma nova branch.
  - `git switch [nome-da-branch]`: Troca para a branch especificada (comando mais recente e intuitivo).
  - `git checkout [nome-da-branch]`: Também troca para a branch especificada (comando mais antigo, mas ainda válido).
  - `git switch -c [nome-da-branch]`: Cria e muda para uma nova branch ao mesmo tempo.
  - `git checkout -b [nome-da-branch]`: Cria e muda para uma nova branch ao mesmo tempo (comando mais antigo).
  - `git branch -d [nome-da-branch]`: Exclui uma branch que não está mais em uso.

### 4. Merge

O **merge** combina as alterações feitas em uma branch com outra. Isso é comum quando se finaliza uma nova funcionalidade em uma branch separada e deseja-se integrar essas mudanças na branch principal.

- Comandos:
  - `git merge [nome-da-branch]`: Faz o merge da branch especificada com a branch atual.
  - `git merge --abort`: Aborta o processo de merge se ocorrerem conflitos.

### 5. Sincronização de Repositórios (Pull e Push) 

O conceito de **sincronização de repositórios** no Git refere-se ao processo de manter os repositórios local (na sua máquina) e remoto (geralmente em um serviço de hospedagem como GitHub, GitLab ou Bitbucket) em um estado consistente e atualizado. A sincronização é fundamental para a colaboração em equipe e para garantir que todos os desenvolvedores tenham acesso às últimas alterações no código.

> [!IMPORTANT]
> Importancia da sincronização:
>  - Evitar conflitos: Quando você sincroniza regularmente seu repositório local com o remoto, reduz o risco de conflitos de código.
>  - Backup e segurança: O repositório remoto serve como um backup seguro das suas alterações.

- Comando:
  - `git pull [remote] [branch]`: Puxa as alterações de um repositório remoto para a branch local.
  - `git push [remote] [branch]`: Envia as alterações para o repositório remoto.
  - `git fetch`: Baixa as alterações do repositório remoto, mas não as aplica à branch atual.
  - `git pull --rebase [remote] [branch]`: Faz o fetch das mudanças e aplica as alterações locais "por cima" das mudanças remotas, reescrevendo o histórico para evitar conflitos.

## 6. Conflitos

**Conflitos** ocorrem quando duas ou mais pessoas editam a mesma parte do código em branches diferentes e o Git não consegue resolver automaticamente qual versão deve ser mantida. Quando isso acontece, é necessário resolver o conflito manualmente.

### Comando:
- `git status`: Mostra se há conflitos de merge e quais arquivos estão envolvidos.
- `git log --merge`: Mostra quais commits estão causando o conflito.
 

## 7. Stash

O **stash** é uma forma de salvar temporariamente suas mudanças não commitadas sem adicioná-las ao commit. Isso é útil quando você precisa mudar de branch, mas ainda não quer fazer commit das mudanças atuais.

### Comandos:
- `git stash`: Guarda as mudanças não commitadas.
- `git stash apply`: Aplica as mudanças que estavam no stash.
- `git stash drop [stash]`: Remove um stash específico.
- `git stash pop`: Aplica e remove o stash da lista.
- `git stash list`: Lista todas as mudanças armazenadas no stash.lista.

## 8. Conceito de Workflow

O Workflow do Git refere-se ao conjunto de práticas e procedimentos que uma equipe ou um desenvolvedor individual segue ao usar o Git para gerenciar alterações em um projeto.

### Workflow Básico:
1. `git clone` para copiar o repositório remoto.
2. `git pull` para sincronizar as mudanças do repositório remoto.
3. `git checkout -b [nome-da-branch]` para criar e mudar para uma nova branch.
4. `git add` e `git commit` para salvar as mudanças.
5. `git push` para enviar suas mudanças para o repositório remoto.
6. `git checkout main` e `git merge [nome-da-branch]` para integrar a funcionalidade desenvolvida.

---
