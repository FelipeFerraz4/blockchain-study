# Estrutura da Blockchain

O ``blockchain`` é composto por uma ``sequência contínua de blocos``, onde ``cada bloco contém um conjunto de informações`` essenciais para garantir a integridade e segurança dos dados armazenados. Esses blocos estão organizados de maneira linear e cronológica, formando uma cadeia de blocos. A seguir, vamos detalhar os principais componentes que formam a estrutura de um bloco no blockchain.

## Estrutura de um Bloco

Um bloco no blockchain contém três partes principais:

- ``Cabeçalho do Bloco`` (Block Header)
- ``Dados`` (Transações ou Informações)
- ``Hash do Bloco``

### Cabeçalho do Bloco (Block Header)

O cabeçalho do bloco contém informações cruciais sobre o bloco e sua posição na cadeia. Ele inclui:

- ``Hash do Bloco Anterior`` (Previous Block Hash)
  - Cada bloco, ``exceto o primeiro (bloco gênese)``, contém um hash que se refere ao bloco anterior na cadeia. 
  - Esse hash é gerado a partir do conteúdo do bloco anterior e serve para garantir a continuidade e a integridade do blockchain.
  - Função: `Se alguém tentar modificar um bloco anterior`, `o hash desse bloco mudaria`, `quebrando a conexão com o próximo bloco` e `sinalizando uma alteração indevida`. Isso torna a falsificação ou modificação de blocos uma tarefa extremamente difícil, pois exigiria recalcular todos os hashes subsequentes.

### Nonce

O `nonce` é um `valor aleatório usado durante o processo de mineração`. Ele é fundamental no mecanismo de `proof of work` (prova de trabalho) utilizado em muitas blockchains. `O minerador ajusta o nonce para gerar um hash` que atenda a um critério específico (geralmente um `número de zeros à frente no hash`).

- Função: O nonce é essencial para a segurança e o consenso na rede. Ele é ajustado repetidamente até que o minerador encontre um valor que resulte em um hash válido, e isso exige um grande esforço computacional.

### Timestamp (Marca Temporal)

O `timestamp` é a `marcação temporal` que indica `quando o bloco foi criado`. Essa informação ajuda a garantir a ordem cronológica dos blocos.

- Função: A marcação temporal é importante para rastrear a sequência de eventos e transações registradas na blockchain.

### Raiz de Merkle (Merkle Root)

A `raiz de Merkle` é o `hash resultante de uma árvore de Merkle`, que organiza todas `as transações de um bloco`. Em vez de armazenar cada transação individualmente no cabeçalho, `as transações são agrupadas e convertidas em um hash único`.

- Função: `A raiz de Merkle permite verificar rapidamente se uma transação específica está incluída no bloco` sem a necessidade de processar todas as transações, economizando tempo e espaço.

## Dados (Transações ou Informações)

A `seção de dados` de um bloco `contém as informações que estão sendo registradas`. Esses dados podem variar dependendo da aplicação do blockchain, mas geralmente incluem:

- `Transações:` No caso do Bitcoin, por exemplo, essas transações são transferências de valor entre contas.
- `Contratos inteligentes:` Em plataformas como Ethereum, o bloco pode conter código de contratos inteligentes, que executam regras de negócios automaticamente.
- `Outros dados:` Blockchains podem ser usados para armazenar qualquer tipo de informação, como registros médicos, títulos de propriedade, etc.

### Estrutura de uma Transação

Cada `transação no bloco` é composta de várias partes, incluindo:

- `Endereço de origem:` Quem está enviando a transação.
- `Endereço de destino:` Quem está recebendo a transação.
- `Montante:` O valor ou dados que estão sendo transferidos.
- `Assinatura digital:` Garante que a transação foi autorizada pelo dono da conta de origem.

## Hash do Bloco

O `hash do bloco` é `um valor único gerado a partir de todas as informações contidas no bloco`, incluindo o cabeçalho e os dados. Este `hash é o identificador único do bloco`, e qualquer alteração mínima no bloco resultará em um hash completamente diferente.

- Função do Hash:
  - `Identidade do Bloco:` O hash serve como uma "impressão digital" do bloco. Qualquer modificação nos dados do bloco ou no cabeçalho (mesmo uma pequena alteração) resultaria em um hash completamente novo, sinalizando uma adulteração.
  - `Conexão entre Blocos:` O hash do bloco atual é calculado usando o hash do bloco anterior. Essa interdependência cria a cadeia que garante a integridade do sistema.

## Exemplo de Hash e Ligação Entre Blocos

Para ilustrar como os blocos se conectam por meio de hashes, imagine o seguinte exemplo simplificado:

Bloco 1:

Dados: Transações X, Y, Z
Hash: 0000abcd
Hash do bloco anterior: 00000000 (pois é o bloco gênese)
Bloco 2:

Dados: Transações A, B, C
Hash do bloco anterior: 0000abcd
Hash: 0000efgh
Bloco 3:

Dados: Transações D, E, F
Hash do bloco anterior: 0000efgh
Hash: 0000ijkl

Se alguém tentasse modificar o Bloco 1, o hash dele mudaria, digamos, para 1111abcd. Isso quebraria a cadeia, já que o Bloco 2 ainda está referenciando o hash antigo (0000abcd). Para consertar, seria necessário recalcular os hashes de todos os blocos subsequentes, o que exigiria um grande poder computacional.

## Funcionamento do Blockchain: Exemplo Visual

```bash
  +---------------------+         +---------------------+         +---------------------+
  |  Bloco 1            |         |  Bloco 2            |         |  Bloco 3            |
  |---------------------|         |---------------------|         |---------------------|
  |  Dados: Tx X, Y     |         |  Dados: Tx A, B     |         |  Dados: Tx D, E     |
  |  Hash: 0000abcd     |         |  Hash: 0000efgh     |         |  Hash: 0000ijkl     |
  |  Hash Ant: 00000000 | ------> |  Hash Ant: 0000abcd | ------> |  Hash Ant: 0000efgh |
  +---------------------+         +---------------------+         +---------------------+
```
## Prova de Trabalho (Proof of Work)

A `prova de trabalho (PoW)` é um `mecanismo de consenso` utilizado por muitas blockchains, como o Bitcoin, para garantir que novos blocos sejam adicionados de forma segura. `Os mineradores competem para achar o hash do bloco com o nonce adequado`, que exige muito poder computacional. Quando um minerador encontra a solução, ele transmite o novo bloco para a rede, onde é validado pelos outros participantes.

## Considerações de Segurança

- `Imutabilidade`: Uma vez que um bloco é adicionado ao blockchain, é quase impossível alterá-lo sem reescrever todos os blocos subsequentes, tornando a cadeia imutável.
- `Descentralização`: O blockchain é mantido por uma rede distribuída de nós, o que elimina o risco de um único ponto de falha.
