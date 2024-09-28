# Guia do Git 2

## Conceitos Avançados

### 1. Aliases

Os **Aliases** são atalhos para comandos Git, permitindo a execução de comandos comuns de forma mais rápida.

- Principais Aliases:
  - `git config --global alias.st status`: Cria um alias global para o comando `git status`.
  - `git config --global alias.co checkout`: Cria um alias global para o comando `git checkout`.
  - `git config --global alias.br branch`: Cria um alias global para o comando `git branch`.
  - `git config --global alias.ci commit`: Cria um alias global para o comando `git commit`.
  - `git config --global alias.lg "log --oneline --graph --all`: Cria um alias global para visualizar o histórico de commits em formato gráfico e simplificado.

### 2. Rebase

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

### 3. Squash

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