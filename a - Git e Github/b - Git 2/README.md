# Guia do Git 2

## Conceitos Avançados

### 1. Conventional Commits

A **Git Commit Convention** (ou **Git Commit Message Guidelines**) refere-se a um conjunto de práticas recomendadas para escrever mensagens de commit de forma padronizada e compreensível.

- **Estrutura do Commit:**
  ```bash
  <tipo>[escopo opcional]: <descrição curta>

  [corpo opcional]

  [rodapé opcional]
  ```

- **Tipo** `(obrigatório)`:

  O tipo indica o propósito do commit.
    - `feat:` Uma nova funcionalidade para o projeto.
    - `fix:` Correção de um bug.
    - `chore:` Alterações de manutenção ou tarefas que não afetam o código de produção (por exemplo, mudanças de configuração).
    - `docs:` Alterações na documentação.
    - `style:` Mudanças relacionadas a formatação de código (espaços em branco, ponto e vírgula, etc.) que não alteram a lógica.
    - `refactor:` Mudança de código que não corrige um bug nem adiciona uma funcionalidade.
    - `test:` Adição ou correção de testes.
    - `perf:` Melhorias de performance.
    - `build:` Alterações que afetam o sistema de build ou dependências externas.
    - `ci:` Mudanças relacionadas à configuração de CI (integração contínua).
  
- **Escopo** `(opcional)`:

  O escopo define a área do código afetada pela mudança, como um módulo, componente ou camada. Exemplo: feat(user): adicionar endpoint de criação de usuário.

- **Descrição curta** `(obrigatório)`:

  Uma breve descrição do que foi alterado. Deve ser objetiva e clara, sem ponto final.

- **Corpo** `(opcional)`:

  Aqui você pode adicionar mais detalhes sobre a mudança. Isso é útil quando o commit é complexo ou precisa de uma explicação adicional. Use o corpo para descrever o que foi alterado e por que.

- **Rodapé** `(opcional)`:
  
  O rodapé é usado para informações como fechar issues ou breaking changes (mudanças que quebram compatibilidade):
    - `BREAKING CHANGE:` Para descrever mudanças que quebram compatibilidade com versões anteriores.
    - `Fixes #<issue-number>:` Para vincular o commit a uma issue no GitHub, Jira, etc.

### 2. Aliases

Os **Aliases** são atalhos para comandos Git, permitindo a execução de comandos comuns de forma mais rápida.

- Principais Aliases:
  - `git config --global alias.st status`: Cria um alias global para o comando `git status`.
  - `git config --global alias.co checkout`: Cria um alias global para o comando `git checkout`.
  - `git config --global alias.br branch`: Cria um alias global para o comando `git branch`.
  - `git config --global alias.ci commit`: Cria um alias global para o comando `git commit`.
  - `git config --global alias.lg "log --oneline --graph --all`: Cria um alias global para visualizar o histórico de commits em formato gráfico e simplificado.

### 3. Rebase

O **Rebase** é uma maneira de aplicar uma sequência de commits de uma branch em outra. Ele essencialmente "move" ou "rebaseia" os commits da sua branch de origem sobre a nova base de outra branch, como a `main`, criando um histórico linear e sem merges extras.

- Objetivo do Rebase é manter um histórico mais limpo e linear: 
  - Ao usar `git merge`, você cria um commit de merge que reflete a junção de duas linhas de desenvolvimento. 
  - O rebase, por outro lado, integra mudanças de uma branch em outra sem criar esse commit de merge, o que pode deixar o histórico mais legível.
  
**Funcionamento do Rebase:**

- Antes do Rebase:
  - Você está trabalhando em uma branch `feature` que tem commits baseados em uma versão antiga da branch `main`.
  - A branch `main` evoluiu e contém novos commits.
  
- Durante o Rebase:
  - O `git rebase main` "reaplica" os commits da sua `feature` branch em cima dos commits mais recentes da branch `main`, como se a sua branch tivesse sido criada agora a partir da versão mais recente da `main`.

- Depois do Rebase:
  - O histórico fica linear, como se os commits da sua branch tivessem sido feitos diretamente na versão mais recente da `main`.

**Exemplo Visual:**

Antes do Rebase:
```bash
main:    A---B---C---D
                   \
feature:             E---F---G
```

Após git rebase main:
```bash
main:    A---B---C---D
                        \
feature:                 E'---F'---G'
```

> [!WARNING]
> **Cuidados com o Rebase:**
>  - `Histórico compartilhado:` Evite fazer rebase em commits que já foram enviados para um repositório remoto (por exemplo, no GitHub). Isso pode causar problemas para outros desenvolvedores, pois o rebase reescreve o histórico.
>  - `Resolução de conflitos:` Se houver conflitos durante o rebase, o Git irá pausá-lo para que você resolva os conflitos. Após resolver, você precisa continuar com `git rebase --continue`.

### 4. Squash

O **Squash** é uma técnica usada para combinar múltiplos commits em um único commit. Isso é útil quando você tem vários commits pequenos e intermediários (como correções de bugs ou mudanças menores) que deseja agrupar em um único commit, deixando o histórico mais claro e coeso.

**Funcionamento do Squash:**

- Inicie um Rebase Interativo:
  - Você pode usar `git rebase -i HEAD~[n]` onde [n] é o número de commits que você deseja ver na lista.

- Squash na tela de rebase:
  - Quando a tela de rebase interativo aparecer, você verá uma lista de commits recentes. Você pode substituir a palavra pick por squash (ou simplesmente s) nos commits que deseja combinar.

- Confirme as mudanças:
  - Após escolher os commits para `squash`, o Git vai mesclar as mensagens de commit e você pode editá-las para criar uma única mensagem mais significativa.

**Exemplo Visual:**

Antes do Squash:

```bash
main:   A---B---C---D---E---F---G
```

Após Squash (por exemplo, combinando D, E, F):
```bash
main:   A---B---C---D'
```
Agora, os commits D, E e F são combinados em um único commit D'.

## 5. Stash

O **stash** é uma forma de salvar temporariamente suas mudanças não commitadas sem adicioná-las ao commit. Isso é útil quando você precisa mudar de branch, mas ainda não quer fazer commit das mudanças atuais.

### Comandos:
- `git stash`: Guarda as mudanças não commitadas.
- `git stash apply`: Aplica as mudanças que estavam no stash.
- `git stash drop [stash]`: Remove um stash específico.
- `git stash pop`: Aplica e remove o stash da lista.
- `git stash list`: Lista todas as mudanças armazenadas no stash.lista.

### 5. Outros comandos

- Comandos:
  - `git tag [nome]:` Cria uma tag no commit atual.
  - `git blame [arquivo]:` Mostra quem fez cada alteração em um arquivo específico.
  - `git reflog:` Mostra o histórico de referências para commits locais (incluindo aqueles perdidos após resets).

---