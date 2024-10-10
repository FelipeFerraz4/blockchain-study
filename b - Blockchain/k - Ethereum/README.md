# Ethereum

**Ethereum** é uma plataforma ``descentralizada`` que permite a execução de aplicações descentralizadas (Dapps) e contratos inteligentes (smart contracts) por meio de uma blockchain. Ela foi criada por Vitalik Buterin em 2015 como uma possível evolução do Bitcoin, que foi desenhado para ser uma rede de transações financeiras e armazenamento de valor. Ethereum foi concebido para ser mais flexível, permitindo a execução de lógica complexa e não apenas transações.

## Comparação com o Bitcoin

- **Objetivo** 
  - O Bitcoin foi projetado para ser uma criptomoeda digital, focada em transferências de valor descentralizadas e como uma reserva de valor. Ethereum, por outro lado, foi criado para ser uma plataforma de execução de aplicativos descentralizados e contratos inteligentes, além de também suportar transações de valor.
- **Turing Completo** 
  - O Bitcoin usa uma linguagem de script limitada para suas transações, enquanto o Ethereum oferece a Ethereum Virtual Machine (EVM), que suporta uma linguagem de programação Turing-completa, ou seja, capaz de executar qualquer algoritmo, possibilitando a criação de contratos inteligentes.
- **Tempo de Bloco:** 
  - O tempo de confirmação de um bloco no Ethereum é de cerca de 12 a 15 segundos, enquanto no Bitcoin é em média de 10 minutos.
- **Algoritmo de Consenso:** 
  - Inicialmente, o Ethereum usava o Proof of Work (PoW), similar ao Bitcoin. Entretanto, o Ethereum migrou para Proof of Stake (PoS) em 2022 com o lançamento do Ethereum 2.0, visando eficiência energética e escalabilidade.

## Ether (ETH)

Ether é a criptomoeda nativa da plataforma Ethereum. É usada para diversas finalidades:

- **Taxas de Transação:**
  - Os usuários pagam taxas de transação (GAS) em ETH ao enviar transações ou executar contratos inteligentes.
- **Staking:**
  -  No mecanismo de consenso Proof of Stake, os validadores devem depositar ETH como stake para participar do processo de validação de blocos.
- **Recompensas:** 
  - Validadores recebem ETH como recompensa por seu trabalho de validação.

## Ethereum Accounts e States

Em Ethereum, há dois tipos principais de contas:

- **Externally Owned Accounts (EOAs):**
  -  São controladas por chaves privadas e podem enviar e receber transações. Os EOAs não têm código associado a eles, apenas um saldo.
- **Contract Accounts:**
  - São contas controladas por contratos inteligentes. Elas contêm código e são acionadas por transações recebidas de EOAs ou outros contratos.
- **Cada conta possui um estado na blockchain, que inclui:**
  - ``Nonce:`` Número de transações enviadas a partir dessa conta.
  - ``Saldo:`` A quantidade de Ether (ETH) na conta.
  - ``Código do contrato`` (apenas para contas de contrato).
  - ``Armazenamento:`` Dados armazenados que pertencem a um contrato inteligente.

O estado global da blockchain Ethereum é uma combinação de todos os estados das contas.

## Ethereum Virtual Machine (EVM)

A **EVM** é o ambiente de execução dos contratos inteligentes no Ethereum. Ela é uma máquina virtual descentralizada que transforma o Ethereum em uma plataforma de computação distribuída. Funciona de forma que qualquer nó na rede Ethereum possa executar o código contido em um contrato inteligente.

**Contratos inteligentes:** São programas armazenados na blockchain que executam ações automaticamente quando determinadas condições são atendidas. Eles são escritos principalmente em ``Solidity``, a principal linguagem de programação do Ethereum.

**Turing Completo:** A EVM é Turing-completa, o que significa que, com recursos computacionais suficientes (tempo e memória), pode executar qualquer operação computacional possível.
Cada transação no Ethereum executa uma função ou uma série de funções em um contrato inteligente. A execução de cada operação na EVM tem um custo de computação que é pago com GAS.

## GAS

**GAS** é a unidade que mede a quantidade de esforço computacional necessário para executar operações na Ethereum, como transações ou execuções de contratos inteligentes. O GAS evita que a rede seja sobrecarregada, pois exige que os usuários paguem pela execução do código.

**Custo do GAS:** Varia dependendo da complexidade computacional das operações. Operações mais simples, como adicionar ou subtrair, custam menos GAS, enquanto operações complexas, como loops ou chamadas de contrato, consomem mais.

**GAS Price e GAS Limit:** Quando uma transação é enviada, o remetente define um GAS price (quanto está disposto a pagar por unidade de GAS) e um GAS limit (quantidade máxima de GAS que está disposto a gastar). Se o GAS se esgotar durante a execução de um contrato, a transação falha, mas o usuário ainda paga pelo GAS consumido até o ponto da falha.

## Smart Contracts

**Contratos inteligentes** são scripts programáveis que executam automaticamente ações quando determinadas condições são atendidas. Eles estão na base da funcionalidade do Ethereum e permitem a criação de Dapps.

- **Características principais:**
  - ``Auto-execução:`` Quando as condições definidas no contrato são atendidas, o contrato é automaticamente executado, sem a necessidade de uma parte intermediária.
  - ``Imutabilidade:`` Uma vez que o contrato é implantado na blockchain, ele não pode ser alterado.
  - ``Descentralização:`` Eles são executados de forma descentralizada pela EVM, o que significa que não há uma única entidade que controle a execução.

## Dapps (Aplicações Descentralizadas)

**Dapps** são aplicativos que utilizam contratos inteligentes no backend, mas têm uma interface tradicional para os usuários. Eles rodam em uma rede peer-to-peer e oferecem diversos casos de uso, como finanças descentralizadas (DeFi), jogos, mercados de NFT, e muito mais.

- **Diferenças de uma aplicação centralizada:**
  - **Descentralização:** Os dados e a lógica de um Dapp são distribuídos em uma rede blockchain, ao contrário das aplicações tradicionais que dependem de servidores centralizados.
  - **Transparência:** Os contratos inteligentes usados pelos Dapps são públicos e podem ser auditados.
  - **Resistência à censura:** Dapps não dependem de uma autoridade central e, portanto, são mais difíceis de censurar ou desativar.

## Tokens e Padrões de Token

Ethereum permite a criação de tokens que podem representar ativos digitais, direitos de voto, ou qualquer outra forma de valor. Os tokens são frequentemente baseados em padrões como:

- **ERC-20:** Um padrão para criar tokens fungíveis que podem ser trocados entre si.
- **ERC-721:** Um padrão para criar tokens não fungíveis (NFTs), que são únicos e não intercambiáveis.

## Layer 2 Solutions (Soluções de Camada 2)

Para aumentar a escalabilidade e eficiência da rede Ethereum, várias soluções de camada 2 foram desenvolvidas. Essas soluções operam em cima da blockchain principal e incluem:

- **Rollups:** Agrupam várias transações em uma única transação, reduzindo a carga na blockchain principal.
- **Plasma:** Cria cadeias menores que se conectam à blockchain principal, permitindo a execução de transações de forma mais rápida e barata.
- **State Channels:** Permitem que as partes envolvidas realizem transações fora da cadeia, apenas finalizando no blockchain quando necessário.

## Governança

A governança no Ethereum refere-se ao processo pelo qual as decisões sobre mudanças no protocolo são feitas. A governança é descentralizada e geralmente envolve discussões na comunidade, propostas de melhoria (EIPs - Ethereum Improvement Proposals) e votação por parte dos desenvolvedores e stakeholders da rede.

## Comparação Detalhada com o Bitcoin

- **Escopo:** O Bitcoin é essencialmente uma moeda digital, enquanto o Ethereum oferece uma plataforma de contratos inteligentes que pode ser usada para muitos propósitos, além de transações financeiras.
- **Complexidade das Transações:** No Bitcoin, as transações envolvem mover BTC de uma conta para outra. Em Ethereum, as transações podem envolver a execução de contratos inteligentes, que podem conter lógica complexa e alterar o estado global da rede.
- **Arquitetura Técnica:** O Bitcoin não possui uma máquina virtual como a EVM, limitando sua capacidade de execução de código. Ethereum, por outro lado, pode executar contratos completos com lógica complexa.
- **Mining vs Staking:** O Bitcoin usa Proof of Work (PoW) para mineração, que exige consumo de energia elevado. O Ethereum, após a transição para Proof of Stake (PoS), reduz o consumo energético e permite a validação de blocos com base na quantidade de ETH em stake.

| Característica             | Bitcoin                                         | Ethereum                                      |
|----------------------------|------------------------------------------------|----------------------------------------------|
| **Lançamento**             | 2009                                           | 2015                                         |
| **Objetivo Principal**     | Moeda digital e reserva de valor               | Plataforma para contratos inteligentes e Dapps |
| **Algoritmo de Consenso**  | Proof of Work (PoW)                            | Proof of Stake (PoS) (após The Merge em 2022) |
| **Moeda Nativa**           | Bitcoin (BTC)                                  | Ether (ETH)                                  |
| **Número Máximo de Moedas**| 21 milhões de BTC                              | Sem limite máximo (a emissão é controlada)   |
| **Transações por Segundo** | Aproximadamente 7 transações por segundo      | Varia, mas pode chegar a milhares com soluções de camada 2 |
| **Tempo de Confirmação**  | Cerca de 10 minutos                            | Cerca de 12-15 segundos                       |
| **Contratos Inteligentes** | Não suporta contratos inteligentes              | Suporta contratos inteligentes e Dapps        |
| **Linguagem de Programação**| Não tem uma linguagem de programação nativa   | Solidity (e outras)                          |
| **Escalabilidade**         | Limitada, com soluções em desenvolvimento      | Melhoria contínua com sharding e Layer 2     |
| **Tipo de Token**          | BTC é a única moeda                            | Suporta múltiplos tokens (ERC-20, ERC-721, etc.) |
| **Governança**             | Mudanças propostas por desenvolvedores e mineradores | Mudanças através de EIPs e votação da comunidade |
| **Uso de Energia**         | Alto (mineração PoW)                           | Menor (mineração PoW antes, agora PoS)      |


## Conclusão

Ethereum oferece muito mais flexibilidade para desenvolvedores criarem novas formas de interação econômica e social, especialmente por meio de contratos inteligentes e Dapps, enquanto o Bitcoin é uma rede mais focada em garantir a segurança e a escassez digital de uma moeda descentralizada.
