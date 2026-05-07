# Felipe Ricarte Magalhães

**Senior Backend Engineer · Software Architect (Hands-on)**

Projeto e implemento backends que sobem para produção: contratos claros, integrações que não quebram sob pressão, mensageria e consistência onde importa, e observabilidade suficiente para entender o que falhou antes do cliente perceber.

Mais de 17 anos em tecnologia. Trabalho na fronteira entre desenho e código — desenho para operação, não para slide. Java e Kotlin são minha base; Spring Boot e Quarkus são onde costumo entregar serviços, APIs e integrações que precisam evoluir com segurança ao longo do tempo.

## Atuação principal

- Backend e APIs em ambientes corporativos e integrações críticas
- Sistemas distribuídos, contratos entre serviços e arquitetura orientada a eventos quando o domínio pede assincronismo
- Mensageria, fluxos transacionais, multitenancy e segurança aplicada, incluindo identidade, autorização e trilhas de auditoria
- Confiabilidade em produção: falhas esperadas, reprocessamento idempotente, evolução de schema e rollout sem surpresa
- Observabilidade pensada como parte do sistema, com métricas, logs e correlação para troubleshooting real

## Stack principal

**Linguagens e frameworks:** Java · Kotlin · Spring Boot · Quarkus

**Dados e migrações:** PostgreSQL · Liquibase · Redis

**Integração e contratos:** REST/OpenAPI (Swagger) · mensageria (RabbitMQ, Kafka e padrões assíncronos) · integrações síncronas e assíncronas

**Segurança e identidade:** Keycloak · OAuth2/OIDC · JWT · modelos de autorização alinhados ao domínio

**Execução e nuvem:** Docker · ambientes cloud e automação de deploy conforme o projeto

Quando o problema pede outra ferramenta, já trabalhei também com Node.js, Python, Ruby, C e frontend com Angular, Vue, React, Ionic e Flutter. Isso ajuda em integração e revisão de ponta a ponta, mas o foco do meu trabalho continua sendo backend e arquitetura aplicada.

## Projetos em destaque

### [order-service](https://github.com/ricartefelipe/order-service)

Microserviço de pedidos com persistência em PostgreSQL, cálculo de totais e APIs voltadas a integração e consulta.

### [assinaflow](https://github.com/ricartefelipe/assinaflow)

Sistema de gestão de assinaturas voltado a um cenário de streaming, com foco em regras de negócio, operação e evolução segura.

### [oficina-springboot-mvp](https://github.com/ricartefelipe/oficina-springboot-mvp)

Sistema para gestão de serviços em oficinas mecânicas, com ênfase em fluxo operacional e feedback em tempo real para clientes.

### [cards-api](https://github.com/ricartefelipe/cards-api)

API para criação de contas bancárias e emissão de cartões físicos e virtuais.

### [py-payments-ledger](https://github.com/ricartefelipe/py-payments-ledger)

Motor de pagamentos com ledger em partidas dobradas, usando FastAPI, SQLAlchemy, Stripe, PostgreSQL e RabbitMQ, com preocupações como outbox, idempotência, ABAC e multi-tenant.

## Como eu costumo trabalhar

- Modelo de domínio e contratos antes de espalhar complexidade entre serviços
- Caos de integração tratado com mensageria, limites claros e operações repetíveis, incluindo retry, DLQ e reprocessamento quando faz sentido
- Mudanças em produção planejadas: migrações, feature flags quando aplicável e rollback pensado de verdade
- Observabilidade e segurança como requisito, não como capítulo opcional no fim do projeto
- Prefiro sistemas previsíveis e operáveis a soluções bonitas que ninguém consegue depurar às três da manhã

## Contato

- [LinkedIn](https://www.linkedin.com/in/felipe-ricarte-magalhaes/)
- [GitHub](https://github.com/ricartefelipe)
- Email: [felipericartem@gmail.com](mailto:felipericartem@gmail.com)
