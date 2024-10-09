# Proof of Work (PoW) e Mining Pools

## O que é Proof of Work (PoW)?

**Proof of Work (PoW)** é um mecanismo de consenso usado por muitas criptomoedas, incluindo o Bitcoin, para garantir a segurança e integridade de suas redes. O conceito de PoW foi originalmente introduzido por Cynthia Dwork e Moni Naor em 1993, mas foi popularizado pelo uso no Bitcoin por Satoshi Nakamoto em 2008.

- **No sistema PoW:** os `mineradores` competem entre si para resolver complexos problemas matemáticos que requerem uma grande quantidade de poder computacional. Esses problemas são parte do processo de criação de novos blocos para adicionar à blockchain. O primeiro minerador a resolver o problema é recompensado com uma quantidade de criptomoeda (por exemplo, Bitcoins no caso do Bitcoin) e o novo bloco é adicionado à cadeia.

- **O processo de PoW:** é altamente seguro porque resolver os problemas é difícil e requer muito esforço computacional, mas verificar a solução é simples. Como resultado, torna-se extremamente difícil para atacantes comprometerem a rede, pois exigiria uma quantidade imensa de poder computacional para alterar o histórico de transações.

## Como o Proof of Work Funciona?

No sistema de `Proof of Work`, o "problema" que os `mineradores` precisam resolver é um processo chamado de `Hashing`. Vamos explorar como isso funciona:

### O Que é Hashing?

- **Hashing** é o processo de pegar uma entrada de dados de qualquer tamanho (como o conteúdo de um bloco na blockchain) e passar por uma função criptográfica que gera uma saída de `tamanho fixo`. No Bitcoin, por exemplo, usa-se o `SHA-256`, uma função de hash que gera uma sequência de `256 bits` (ou 64 caracteres hexadecimais).

- A propriedade chave dessa função é que `pequenas mudanças na entrada produzem saídas completamente diferentes` de maneira imprevisível. Isso é o que torna a mineração viável como mecanismo de segurança.

### O Problema que os Mineradores Precisam Resolver

Para entender o problema que os mineradores precisam resolver, primeiro é importante entender o conceito de `hash` e `dificuldade`:

- **Bloco de Transações:** Cada bloco de uma blockchain contém um conjunto de transações. Junto com essas transações, outros dados, como o hash do bloco anterior e um número chamado de nonce (explicado abaixo), também estão presentes.

- **O Hash do Bloco:** O trabalho dos mineradores é gerar um hash para esse bloco que satisfaça uma condição específica: o hash precisa ser menor ou igual a um certo valor-alvo predefinido, chamado de target. Este valor-alvo é ajustado de acordo com a dificuldade da rede, que é dinâmica e muda conforme o poder computacional total da rede.

- **Dificuldade:** A dificuldade é ajustada automaticamente pela rede para garantir que os blocos sejam minerados em intervalos consistentes (por exemplo, a cada 10 minutos no caso do Bitcoin). Quando há mais mineradores na rede, a dificuldade aumenta; quando há menos mineradores, a dificuldade diminui. Essa dificuldade define quantos zeros à esquerda o hash precisa ter para ser considerado válido.

### O Processo de Mineração

- **Montagem do Bloco:** O minerador reúne um conjunto de transações válidas, o hash do bloco anterior, e começa a trabalhar no bloco atual.

- **Cálculo do Hash:** O minerador cria um hash usando os dados do bloco (incluindo transações) e um número chamado nonce. O nonce é uma variável que os mineradores podem modificar para gerar diferentes hashes a partir do mesmo conjunto de dados de transações.

- **Teste do Hash:** O minerador então verifica se o hash gerado é menor ou igual ao valor-alvo de dificuldade da rede. Isso é feito ao comparar o hash do bloco com o "target". Se o hash não atende à condição de dificuldade (por exemplo, não começa com o número suficiente de zeros), o minerador altera o nonce e tenta novamente.

- **Repetição:** Esse processo é repetido bilhões ou até trilhões de vezes por segundo em grandes fazendas de mineração, até que um minerador finalmente encontre um hash que satisfaça a condição de dificuldade. Este processo é essencialmente um jogo de tentativa e erro.

- **Bloco Resolvido:** Quando um minerador encontra um hash válido, o bloco é resolvido, e o minerador que encontrou o hash válido envia o bloco para a rede. Os outros nós (computadores) da rede verificam a validade do bloco (incluindo se o hash e as transações são corretas), e se tudo estiver certo, o bloco é adicionado à blockchain.

### Exemplo

Vamos imaginar um exemplo de mineração com hashes de 3 dígitos para entender melhor o processo. Suponha que a função de hash seja muito mais simples e gere números de três dígitos, e a dificuldade da rede exige que o hash comece com pelo menos dois zeros, ou seja, o hash final deve ser algo como 00X onde X pode ser qualquer número.

- **Aqui está o processo:**
  1. O minerador pega o bloco de transações, e começa com um nonce de 0.
  2. O hash resultante é calculado. Suponha que o hash resultante seja 435, o que não é válido porque não começa com dois zeros.
  3. O minerador então incrementa o nonce para 1 e calcula o hash novamente.
  4. Após várias tentativas, o minerador encontra um nonce que gera um hash como 003. Esse hash atende à condição de dificuldade (começa com dois zeros), e o minerador consegue resolver o bloco.

### Importância do Nonce

O nonce é um número aleatório que o minerador altera em cada tentativa de encontrar um hash válido. Como o hash gerado é muito sensível a qualquer mudança nos dados de entrada, mudar o nonce a cada tentativa resulta em um hash completamente diferente, permitindo que o minerador continue gerando novas tentativas até que um hash válido seja encontrado.

### Dificuldade e Alvo

A dificuldade é ajustada para garantir que os blocos sejam minerados em intervalos regulares. Isso é importante para manter a estabilidade da blockchain. O alvo (ou target) é simplesmente o valor numérico que o hash gerado deve ser menor ou igual. Quanto mais difícil a mineração, mais zeros à esquerda o hash precisa ter, tornando a busca por um hash válido mais trabalhosa e demorada.

- **Por exemplo**:
  - Se a dificuldade é baixa, o hash pode ser algo como 0XXXXXXX, com apenas um zero à esquerda.
  - Se a dificuldade é alta, o hash pode precisar ser algo como 0000XXXX, com quatro zeros à esquerda.

### Consumo de Energia e Poder Computacional

Resolver o problema de PoW requer uma grande quantidade de tentativas, o que significa que os mineradores precisam de hardware especializado (geralmente ASICs – Application-Specific Integrated Circuits) e muita energia elétrica. Esse é um dos principais pontos de crítica ao sistema PoW: o consumo de energia para manter a rede segura pode ser muito elevado.

### Segurança do Proof of Work

O PoW é seguro porque é extremamente difícil para um invasor resolver o problema e falsificar um bloco. No entanto, uma vez que o bloco é resolvido, verificar a solução é simples. Para manipular a blockchain, um atacante precisaria controlar mais de 50% do poder computacional da rede, o que é chamado de ataque de 51%, e, mesmo assim, seria caro e logisticamente difícil de ser realizado em redes grandes como a do Bitcoin.

## Recompensas dos Mineradores

Os mineradores são recompensados de duas maneiras principais por seu trabalho em blockchains baseadas no Proof of Work (PoW), como o Bitcoin. Essas recompensas são a base de incentivo para os mineradores continuarem validando e protegendo a rede.

### Recompensa de Bloco (Block Reward)

A recompensa de bloco é o incentivo principal que os mineradores recebem por adicionar um novo bloco à blockchain. Quando um minerador resolve o problema matemático (encontra um hash válido), ele tem o direito de adicionar um novo bloco à blockchain, e, em troca, recebe uma quantidade predefinida de criptomoeda recém-criada.

- **Como Funciona a Recompensa de Bloco:**
  - **Emissão de Moedas Novas:** A cada novo bloco minerado, um número fixo de novas moedas é criado e concedido ao minerador. No caso do Bitcoin, essa recompensa é chamada de block reward e é a principal forma de emissão de novos Bitcoins.
  - **Halving:** No Bitcoin, a recompensa por bloco é reduzida pela metade aproximadamente a cada quatro anos (ou a cada 210.000 blocos minerados), em um evento conhecido como halving. Isso é programado para controlar a inflação e reduzir gradualmente a emissão de novos Bitcoins até que o suprimento total de 21 milhões de Bitcoins seja atingido.
    1. Quando o Bitcoin foi criado em 2009, a recompensa era de 50 BTC por bloco.
    2. Após o primeiro halving em 2012, a recompensa caiu para 25 BTC.
    3. No segundo halving em 2016, caiu para 12,5 BTC.
    4. Em 2024, após o quarto halving, a recompensa passou a ser 3,125 BTC.
    5. O próximo halving, previsto para 2028, reduzirá a recompensa para 1,5625 BTC.

- **Finalidade da Recompensa de Bloco:**
  - **Incentivar a Mineração Inicial:** Nos primeiros anos de uma criptomoeda, as recompensas de bloco são elevadas para incentivar os mineradores a dedicar poder computacional à rede.
  - **Redução Gradual da Emissão:** O mecanismo de halving ajuda a controlar a inflação da moeda e cria um suprimento limitado, o que ajuda a aumentar o valor da criptomoeda ao longo do tempo, já que a oferta se torna escassa.

- **Fim das Recompensas de Bloco:** No Bitcoin, quando todos os 21 milhões de Bitcoins forem minerados (previsto para ocorrer por volta de 2140), não haverá mais recompensas de bloco. Nesse ponto, os mineradores dependerão exclusivamente das taxas de transação para serem recompensados (ver a seguir).

### Taxas de Transação (Transaction Fees)

Além da recompensa de bloco, os mineradores também ganham taxas de transação. Cada vez que uma transação é realizada na rede, o remetente geralmente paga uma pequena taxa para incentivar os mineradores a priorizar essa transação no próximo bloco a ser minerado.

- **Como Funcionam as Taxas de Transação:**
  - **Incluídas em Cada Bloco:** Quando um minerador resolve um bloco, ele coleta todas as transações que serão incluídas nesse bloco, e as taxas associadas a cada transação vão diretamente para o minerador.
  - **Competição entre Transações:** Quando a rede está congestionada, usuários podem oferecer taxas mais altas para garantir que suas transações sejam incluídas mais rapidamente, criando uma espécie de "leilão" de taxas, onde transações com taxas maiores são incluídas primeiro nos blocos minerados.
- **Finalidade da Recompensa de Bloco:**
  - **Incentivo a Processar Transações:** Como a capacidade de cada bloco é limitada (no caso do Bitcoin, cada bloco tem aproximadamente 1 MB de tamanho), as taxas de transação incentivam os mineradores a incluir transações de maior valor (taxas mais altas) para maximizar seus ganhos.
    - À medida que a recompensa de bloco diminui com o tempo (devido ao halving), as taxas de transação se tornam uma fonte cada vez mais importante de receita para os mineradores. Em um futuro onde a recompensa de bloco não será mais emitida (após todos os Bitcoins serem minerados), os mineradores dependerão exclusivamente das taxas de transação como forma de remuneração.

O sistema de recompensas garante que os mineradores tenham um forte incentivo econômico para continuar validando transações e mantendo a segurança da rede, mesmo que o sistema se torne mais competitivo e a recompensa de bloco diminua com o tempo.

### Exemplo de Recompensa em um Bloco de Bitcoin

Suponha que um minerador tenha acabado de encontrar um hash válido e resolver o próximo bloco na blockchain do Bitcoin. O minerador é recompensado da seguinte forma:

- **Recompensa de Bloco:** O minerador recebe 6,25 BTC (considerando o período após o halving de 2020).
- **Taxas de Transação:** Além dos 6,25 BTC, o minerador também recebe todas as taxas associadas às transações incluídas no bloco. Por exemplo, se as transações no bloco totalizam 0,5 BTC em taxas, o minerador ganha um total de 6,75 BTC (6,25 BTC de recompensa + 0,5 BTC de taxas).
Essa recompensa é então enviada diretamente para o endereço de carteira do minerador, e ele pode dispor dessa quantia como preferir.

## O que são Mining Pools?

**Mining Pools** são grupos de mineradores que trabalham juntos para resolver problemas no sistema Proof of Work e dividir as recompensas de maneira proporcional ao poder de mineração que cada um contribuiu. Como a dificuldade de mineração aumenta com o tempo, é cada vez mais difícil para mineradores individuais competirem sozinhos. Os pools permitem que pequenos mineradores juntem suas forças e aumentem suas chances de ganhar recompensas.

### Como os Mining Pools Funcionam?

- **Contribuição de Poder Computacional**: Cada minerador em um pool contribui com seu poder computacional (hashrate) para resolver os problemas matemáticos.

- **Distribuição Proporcional:** Cada minerador no pool contribui com uma quantidade de poder computacional para tentar resolver o bloco. Quando o pool encontra um bloco válido, a recompensa é distribuída proporcionalmente ao hashrate que cada minerador forneceu durante o processo.

- **Taxas do Pool:** Os pools de mineração geralmente cobram uma pequena taxa de administração (geralmente entre 1% e 3%) para organizar o pool, e essa taxa é deduzida antes da distribuição das recompensas.

- **Pagamentos Regulares:** Ao contrário de minerar sozinho, onde o minerador pode esperar por meses ou anos para resolver um bloco e ganhar uma grande recompensa, os participantes de pools recebem pagamentos menores, mas de forma mais regular, à medida que o pool encontra blocos.

### Vantagens dos Mining Pools:

- **Recompensas mais consistentes**: Em vez de depender de resolver um bloco sozinho, mineradores em pools recebem pequenas porções de recompensas de forma mais regular.
- **Redução de variância**: A chance de resolver um bloco pode ser muito baixa para mineradores individuais, mas em um pool, as recompensas são distribuídas de forma mais previsível.

### Desvantagens dos Mining Pools:

- **Centralização do poder de mineração**: Pools grandes podem acumular muito poder computacional, o que pode ameaçar a descentralização da rede.
- **Taxas de administração**: Os pools frequentemente cobram uma pequena porcentagem das recompensas dos mineradores como taxa pelo serviço oferecido.

## Exemplo de Funcionamento do Proof of Work e Mining Pools:

1. Imagine que você é um minerador solo tentando minerar Bitcoins. Para isso, você precisa resolver um problema criptográfico extremamente difícil. A chance de você ser o primeiro a resolver o problema e receber a recompensa pode ser muito pequena, especialmente com mineradores maiores competindo. Se você se juntar a um pool de mineração, sua máquina irá contribuir com seu poder de mineração, e se alguém no pool resolver o problema, você receberá uma parte da recompensa com base no quanto contribuiu, garantindo uma renda mais previsível, mesmo que menor.

2. Se um pool de mineração resolve um bloco e recebe uma recompensa de 6,25 BTC mais 0,5 BTC em taxas de transação (total de 6,75 BTC):

3. Se você contribuiu com 5% do poder computacional do pool, você receberia 5% de 6,75 BTC, o que equivale a 0,3375 BTC.

## Conclusão

O Proof of Work é uma peça central das criptomoedas que assegura a integridade e a segurança das transações. Embora seja eficiente em termos de segurança, seu consumo de energia e tendência à centralização em grandes mineradores são desafios contínuos. Os Mining Pools surgem como uma solução para permitir que mineradores menores ainda possam participar e lucrar, embora isso também venha com suas próprias preocupações sobre a centralização do poder computacional.
Se o pool cobra uma taxa de 2%, você receberia 0,33075 BTC após a dedução da taxa do pool.