# Guia do Git Flow

O **Git Flow** é um modelo de ramificação para Git, popularizado por Vincent Driessen. Ele define um fluxo de trabalho robusto que ajuda a gerenciar projetos maiores por meio de uma estrutura organizada de ramificações.

> [!NOTE]
> Você pode automatizar o Git Flow usando a extensão `git-flow`. Aqui estão alguns comandos que facilitam o processo:
> Para inicializar a extensão do Git Flow no seu repositório e criar a branch main e develop:
> ```bash
> git flow init
> ```

## Ramificações no Git Flow

O Git Flow utiliza duas ramificações principais e várias ramificações de suporte:

### Ramificações Principais

1. **`main`** (ou `master`):
   - Esta ramificação contém o código pronto para produção.
   - Deve sempre refletir uma versão estável e pronta para ser lançada.

2. **`develop`**:
   - Esta ramificação contém as últimas alterações de desenvolvimento.
   - É a base para todas as ramificações de novas funcionalidades e é usada para integrar o trabalho em andamento.

### Ramificações de Suporte

1. **Ramificações de Funcionalidade (`feature/*`)**:
   - Essas ramificações são criadas a partir da `develop` para trabalhar em funcionalidades ou tarefas específicas.
   - Quando uma funcionalidade está completa, a ramificação é mesclada de volta na `develop`.
   - Comandos:
     - `git flow feature start nome-da-funcionalidade`: Cria uma nova ramificação da `develop` para iniciar o desenvolvimento de uma nova funcionalidade.
     - `git flow feature finish nome-da-funcionalidade`: Mescla a branch da funcionalidade com a branch `develop` e deleta a branch.

2. **Ramificações de Lançamento (`release/*`)**:
   - Essas ramificações são criadas quando uma nova versão está pronta para ser preparada para a produção.
   - Elas são usadas para testes e correções de bugs antes de serem mescladas na `main`.
   - Comandos:
     - `git flow release start v1.0.0`: Cria uma nova ramificação de `release` a partir da `develop` para preparar o lançamento de uma nova versão.
     - `git flow release finish v1.0.0`: Mescla a branch `release` nas branches `main` e `develop`, cria uma tag da versão e deleta a branch `release`.

3. **Ramificações de Correção Rápida (`hotfix/*`)**:
   - Essas ramificações são utilizadas para correções urgentes na versão de produção.
   - Elas são criadas a partir da `main` e, uma vez corrigidas, são mescladas de volta tanto na `main` quanto na `develop`.
   - Comandos:
     - `git flow hotfix start nome-da-correção`: Cria uma nova ramificação de `hotfix` a partir da `main` para corrigir um bug crítico.
     - `git flow hotfix finish nome-da-correção`: Mescla a branch `hotfix` nas branches `main` e `develop`, cria uma tag da correção e deleta a branch `hotfix`.

4. **Ramificações de Correção de Bug (`bugfix/*`)**:
   - Essas ramificações são criadas para corrigir bugs específicos encontrados durante o desenvolvimento.
   - Elas são criadas a partir da `develop` e, uma vez resolvido o bug, são mescladas de volta na `develop`.
   - Comandos:
     - `git flow bugfix start nome-do-bug`: Cria uma nova ramificação de `bugfix` a partir da `develop` para corrigir um bug.
     - `git flow bugfix finish nome-do-bug`: Mescla a branch `bugfix` de volta na branch `develop` e deleta a branch.

## Vantagens do Git Flow
- **Desenvolvimento Paralelo**: Suporta o desenvolvimento simultâneo de várias funcionalidades.
- **Correções de Produção Isoladas**: Correções críticas podem ser feitas rapidamente sem interromper o trabalho em andamento.
- **Lançamentos Estruturados**: Preparação controlada para lançar novas versões em produção.
- **Tagueamento de Versões**: Cada lançamento é marcado, facilitando o acesso a versões específicas.

## Quando Não Usar o Git Flow
``Projetos menores`` ou que ``utilizam integração/desenvolvimento contínuos`` podem se beneficiar mais de fluxos de trabalho mais simples, como desenvolvimento baseado em `trunk`.

## Conclusão
O Git Flow é um fluxo de trabalho poderoso para gerenciar ``projetos em larga escala``, com uma estrutura clara de ramificações e gerenciamento de lançamentos. Ao separar o desenvolvimento contínuo de versões estáveis e correções rápidas, as equipes podem trabalhar de forma mais eficiente e manter um código mais limpo.