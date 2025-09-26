# nome.social Protocol Architecture (en)

This document describes the data flow and interaction between the components of the `nome.social` protocol. Our architecture leverages a professional, third-party stack to de-risk execution and focus on our core innovation.

## Flow Diagram
```
[User at Frontend] --(1. Requests Name)--> [Backend]
^                                         |
|                                         | (2. Generates PIX QR Code)
|                                         |
+-------(3. Pays R$0.01 via Bank App)------+
|
|
[Third-party PIX API (e.g., Avenia)] --(4. Sends Webhook)--> [Backend]
|
| (5. Validates CPF, Checks Uniqueness)
|
+----(6. Calls API)----> [ENS.node Service]
|
+--> [Smart Contracts on Base L2]
|
+--> [EAS Contract: Creates Attestation]
|
+--> [NameKit Registrar: Registers user.nomes.eth]
```

## Component Details

### 1. Frontend (Next.js / Vercel)
* **Responsibility:** User Interface.
* **Functions:** Onboards the user via an Account Abstraction provider (**Openfort**), displays the PIX QR Code, and confirms the registration's success by checking for the on-chain attestation and subdomain.

### 2. Backend (Node.js)
* **Responsibility:** Orchestration and business logic.
* **Functions:**
    * **PIX Integration:** Integrates with a provider like **Avenia** to generate charges and receive confirmation webhooks.
    * **Verification Logic:** Validates the uniqueness of the payer's CPF by checking an internal database of salted hashes.
    * **Security:** Integrates with **NameGuard** to check the requested subdomain for security risks before registration.
    * **On-Chain Integration:** Makes a secure API call to the **ENS.node** service to trigger the on-chain transactions.

### 3. On-Chain Infrastructure (Base L2)
* **Responsibility:** Registration and persistence of digital assets.
* **Components:**
    * **ENS.node:** A managed API service from NameHash Labs that abstracts away the complexity of direct interaction with the smart contracts.
    * **`.nomes.eth` Registrar:** The smart contract, based on **NameKit**, which controls the registration and renewal rules for the subdomains.
    * **Ethereum Attestation Service (EAS):** The public, open-source contract used to issue the on-chain "Proof of Humanity" certificate for verified users, ensuring interoperability.

---

# Arquitetura do Protocolo nome.social (pt-br)

Este documento descreve o fluxo de dados e a interação entre os componentes do protocolo `nome.social`. Nossa arquitetura alavanca uma stack profissional de terceiros para mitigar riscos de execução e focar em nossa inovação principal.

## Diagrama de Fluxo

```
[Usuário no Frontend] --(1. Solicita Nome)--> [Backend]
^                                            |
|                                            | (2. Gera QR Code PIX)
|                                            |
+-------(3. Paga R$0,01 com App do Banco)-----+
|
|
[API PIX de Terceiros (ex: Avenia)] --(4. Envia Webhook)--> [Backend]
|
| (5. Valida CPF, Checa Unicidade)
|
+----(6. Chama API)----> [ENS.node Service]
|
+--> [Smart Contracts na Base L2]
|
+--> [Contrato EAS: Cria Atestação]
|
+--> [Registrador NameKit: Registra usuario.nomes.eth]
```

## Detalhes dos Componentes

### 1. Frontend (Next.js / Vercel)
* **Responsabilidade:** Interface do usuário.
* **Funções:** Faz o onboarding do usuário através de um provedor de Abstração de Conta (**Openfort**), exibe o QR Code PIX e confirma o sucesso do registro ao verificar a atestação e o subdomínio on-chain.

### 2. Backend (Node.js)
* **Responsabilidade:** Orquestração e lógica de negócio.
* **Funções:**
    * **Integração PIX:** Integra-se com um provedor como a **Avenia** para gerar cobranças e receber webhooks de confirmação.
    * **Lógica de Verificação:** Valida a unicidade do CPF do pagador consultando um banco de dados interno de hashes com "salt".
    * **Segurança:** Integra-se com o **NameGuard** para verificar o subdomínio solicitado em busca de riscos de segurança antes do registro.
    * **Integração On-Chain:** Faz uma chamada de API segura para o serviço **ENS.node** para acionar as transações on-chain.

### 3. Infraestrutura On-Chain (Base L2)
* **Responsabilidade:** Registro e persistência dos ativos digitais.
* **Componentes:**
    * **ENS.node:** Um serviço de API gerenciado da NameHash Labs que abstrai a complexidade da interação direta com os smart contracts.
    * **Registrador `.nomes.eth`:** O smart contract, baseado no **NameKit**, que controla as regras de registro e renovação dos subdomínios.
    * **Ethereum Attestation Service (EAS):** O contrato público e open-source usado para emitir o certificado on-chain de "Prova de Humanidade" para usuários verificados, garantindo interoperabilidade.
