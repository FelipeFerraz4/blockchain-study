# Assinatura Digital em Blockchain

## O que é uma Assinatura Digital?

Uma `assinatura digital` é um método criptográfico utilizado para garantir a autenticidade e a integridade de uma mensagem, documento ou transação digital. Ela funciona de forma semelhante a uma assinatura manuscrita, garantindo que o remetente da mensagem seja quem ele afirma ser e que a mensagem não tenha sido alterada.

## Como Funciona a Assinatura Digital em Blockchain?

No contexto de uma `blockchain`, a assinatura digital é essencial para validar transações. Cada participante da rede possui um par de chaves criptográficas: uma chave pública e uma chave privada. A chave privada é usada para `assinar` transações, enquanto a chave pública é usada para `verificar` essas assinaturas.

### Passos de Funcionamento:

1. **Geração do Par de Chaves**: 
   - Cada usuário da blockchain possui um par de chaves, gerado por um algoritmo criptográfico (geralmente ECDSA ou RSA). A chave privada é mantida em segredo, enquanto a chave pública é compartilhada.

2. **Assinatura da Transação**:
   - Quando um usuário cria uma transação, ele usa sua chave privada para gerar uma assinatura digital.
   - A assinatura é gerada aplicando um `algoritmo de hash` à transação e, em seguida, criptografando o hash com a chave privada do usuário. O resultado é a assinatura.

3. **Verificação da Assinatura**:
   - Quando a transação é transmitida à rede, os nós (computadores que validam transações) usam a chave pública do remetente para verificar a assinatura.
   - O nó aplica o mesmo algoritmo de hash à transação e compara o resultado com o hash criptografado contido na assinatura. Se os dois forem iguais, a assinatura é válida e a transação é considerada autêntica.

## Uso da Assinatura Digital na Blockchain

As assinaturas digitais são usadas na blockchain para:

- **Validação de Transações**: Cada transação é assinada digitalmente pelo remetente para garantir que ela foi iniciada por ele e não por um terceiro.
- **Confiança Descentralizada**: Como as assinaturas digitais dependem de pares de chaves assimétricos (pública e privada), não há necessidade de uma autoridade central para verificar a autenticidade das transações.
- **Segurança em Contratos Inteligentes**: Em blockchains que utilizam contratos inteligentes (como o Ethereum), as assinaturas digitais são fundamentais para garantir que somente os usuários autorizados possam interagir com os contratos.
- **Prova de Propriedade**: Ao assinar digitalmente uma transação, o usuário prova que é o legítimo proprietário dos fundos ou ativos que deseja transferir.

## Diferença entre Assinatura Digital (Assimétrica) e Assinatura Simétrica

### Assinatura Digital (Criptografia Assimétrica)

Na criptografia assimétrica, são utilizadas duas chaves diferentes: uma `chave privada` e uma `chave pública`.

- **Chave Privada**: Mantida em segredo pelo proprietário e usada para `assinar` digitalmente as transações.
- **Chave Pública**: Disponibilizada publicamente e usada pelos outros membros da rede para `verificar` as assinaturas digitais.

#### Vantagens da Assinatura Digital (Assimétrica):
- **Segurança Elevada**: Mesmo que a chave pública seja conhecida por todos, sem a chave privada, ninguém consegue forjar assinaturas.
- **Não-Repúdio**: Como só o detentor da chave privada pode assinar uma transação, ele não pode negar posteriormente ter realizado essa assinatura.
- **Aplicação em Redes Descentralizadas**: Muito adequada para sistemas como blockchain, onde não há uma autoridade central para verificar transações.

### Assinatura Simétrica

Na criptografia simétrica, o remetente e o destinatário utilizam a `mesma chave secreta` para assinar e verificar transações.

- **Chave Compartilhada**: Uma única chave é usada para ambos os processos de assinatura e verificação.
  
#### Desvantagens da Assinatura Simétrica:
- **Menor Segurança**: Como ambas as partes compartilham a mesma chave, se a chave for comprometida, tanto a autenticidade quanto a integridade das transações estarão em risco.
- **Escalabilidade Limitada**: Para sistemas com muitos participantes (como a blockchain), a gestão e o compartilhamento de chaves seguras se tornam inviáveis.
- **Não-Repúdio não Garantido**: O remetente pode alegar que o destinatário forjou a assinatura, uma vez que ambos têm acesso à mesma chave.

### Diferença Chave:

- **Assimétrica (Usada em Blockchain)**: Usa duas chaves diferentes (pública e privada), o que proporciona maior segurança e independência. Cada usuário da blockchain tem um par único de chaves.
- **Simétrica**: Usa uma chave única compartilhada entre as partes, o que não é adequado para sistemas descentralizados como blockchain.

## Conclusão

A **assinatura digital baseada em criptografia assimétrica** é um componente fundamental da tecnologia blockchain, permitindo a verificação descentralizada e segura de transações sem a necessidade de confiança em intermediários. Ao contrário da criptografia simétrica, que é mais simples mas menos segura, a criptografia assimétrica garante que somente o legítimo proprietário da chave privada possa realizar transações, tornando o processo seguro, escalável e confiável em grandes redes distribuídas.
