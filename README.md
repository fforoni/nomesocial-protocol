# nome.social 🇧🇷 (en)

*Sovereign identity layer for Brazil with ENS, enabling Proof of Humanity via the PIX payment system.*

**Your digital identity on the new internet. Verified by Brazil.**

[Landing Page (coming soon)](nomesocial.org) - [Whitepaper (coming soon)](nomesocial.org/whitepaper)

## Vision

Our mission is to establish the decentralized identity standard for Brazil by onboarding millions of users to the ENS ecosystem through a solution that integrates, rather than extracts. We build a bridge between Brazil's trusted financial infrastructure and the future of Web3.

## Architecture

The protocol utilizes a three-component architecture to ensure security and scalability, built on **Base (L2)**:

1.  **On-Chain Infrastructure:** Subdomain registrar contracts based on the battle-tested [NameKit.io](https://www.namekit.io/) and a contract for the verification Soulbound Token (SBT).
2.  **Backend (Node.js):** A server that listens for webhooks from the PIX API, validates the uniqueness of the CPF, and securely triggers the on-chain transactions.
3.  **Frontend (Next.js):** The web interface for the user to register and manage their identity.

See our detailed technical architecture in [`ARCHITECTURE.md`](./ARCHITECTURE.md).

## Project Status

This project is under active development. We intend to submit a grant proposal to the **ENS Ecosystem Working Group** to accelerate the MVP construction, perform security audits, and launch on mainnet in Q1 2026.

## Contributing

We are in the early stages of formalizing the project. The best place to contribute right now is by reading our Whitepaper and participating in the upcoming discussion on the ENS DAO Forum.

---

# nome.social 🇧🇷 (pt-br)

*Camada de identidade soberana para o Brasil com a ENS, habilitando a Prova de Humanidade através do PIX.*

**Sua identidade digital na nova internet. Verificada pelo Brasil.**

[Landing Page (em breve)](nomesocial.org) - [Whitepaper (em breve)](nomesocial.org/whitepaper)

## Visão

Nossa missão é estabelecer o padrão de identidade descentralizada para o Brasil, onboardando milhões de usuários para o ecossistema ENS através de uma solução que integra, em vez de extrair. Construímos uma ponte entre a infraestrutura financeira confiável do Brasil e o futuro da Web3.

## Arquitetura

O protocolo utiliza uma arquitetura de três componentes principais para garantir segurança e escalabilidade, construído sobre a **Base (L2)**:

1.  **Infraestrutura On-Chain:** Contratos de subdomínio baseados no [NameKit.io](https://www.namekit.io/) e um contrato para o Soulbound Token (SBT) de verificação.
2.  **Backend (Node.js):** Um servidor que escuta webhooks da API PIX, valida a unicidade do CPF e aciona as transações on-chain de forma segura.
3.  **Frontend (Next.js):** A interface web para o usuário se registrar e gerenciar sua identidade.

Veja nossa arquitetura técnica detalhada em [`ARCHITECTURE.md`](./ARCHITECTURE.md).

## Status do Projeto

Este projeto está em desenvolvimento ativo. Nossa intenção é submeter uma proposta de grant para o **ENS Ecosystem Working Group** para acelerar a construção do MVP, realizar auditorias de segurança e lançar em mainnet no Q1 2026.

## Contribuindo

Estamos no estágio inicial de formalização do projeto. O melhor lugar para contribuir no momento é lendo nosso Whitepaper e participando da futura discussão no Fórum da ENS DAO.