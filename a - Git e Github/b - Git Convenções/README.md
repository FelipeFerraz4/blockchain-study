# Guia do Git

## Convenções do git

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

### 2. Nomenclatura de Branches

- **Estrutura de Nomenclatura de Branches:**
  ```bash
  <prefixo da branch>/<descrição curta>
  ```
  - **Prefixo de tipo de branch:** Utilizar um prefixo para indicar o tipo de trabalho realizado no branch.

  - **Descrição clara:** O nome do branch deve ser descritivo, indicando o propósito da mudança. Use palavras separadas por hífen `(-)` ou barras `(/)`.
  
  - **Prefixos Comums:**
    - `feat:` Uma nova funcionalidade para o projeto.
    - `fix:` Correção de um bug.
    - `chore:` Alterações de manutenção ou tarefas que não afetam o código de produção (por exemplo, mudanças de configuração).
    - `docs:` Alterações na documentação.
    - `style:` Mudanças relacionadas à formatação de código (espaços em branco, ponto e vírgula, etc.) que não alteram a lógica.
    - `refactor:` Mudança de código que não corrige um bug nem adiciona uma funcionalidade nova.
    - `test:` Adição ou correção de testes.
    - `perf:` Melhorias de performance no código.
    - `build:` Alterações que afetam o sistema de build ou dependências externas.
    - `ci:` Mudanças relacionadas à configuração de CI (integração contínua).
    - `hotfix:` Correções rápidas e urgentes em produção.
    - `revert:` Reversão de um commit anterior.
    - `security:` Alterações que resolvem vulnerabilidades de segurança.
    - `release:` Criação ou preparação de uma nova versão do sistema.
    - `localization:` Atualizações ou adições relacionadas à localização e internacionalização.
    - `i18n:` Atualizações relacionadas à internacionalização (i18n).
    - `l10n:` Atualizações relacionadas à localização (l10n).
    - `env:` Mudanças relacionadas a variáveis de ambiente ou configuração.
  
  - **Exemplos de Nomenclatura de Branches:**
    - feat/adicionar-sistema-de-notificacoes
    - fix/123-resolver-erro-no-carrinho
    - chore/configurar-ci
    - docs/atualizar-manual-usuario
    - hotfix/corrigir-crash-app 