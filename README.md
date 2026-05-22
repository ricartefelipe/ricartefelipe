# Felipe Ricarte Magalhães

**Senior Backend Engineer · Software Architect (Hands-on)**

Projeto e implemento backends que sobem para produção: contratos claros, integrações que não quebram sob pressão, mensageria e consistência onde importa, e observabilidade suficiente para entender o que falhou antes do cliente perceber.

Mais de 17 anos em tecnologia. Trabalho na fronteira entre desenho e código. Desenho para operação, não para slide. Java e Kotlin são minha base; Spring Boot e Quarkus são onde costumo entregar serviços, APIs e integrações que precisam evoluir com segurança ao longo do tempo.

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

### Plataforma B2B multilocatária (Fluxe)

Plataforma completa de e-commerce B2B com multitenancy, arquitetura orientada a eventos e deploy automatizado.

- **[spring-saas-core](https://github.com/ricartefelipe/spring-saas-core)** — Control plane multi-tenant: gestão de tenants, RBAC/ABAC, feature flags, auditoria, JWT e outbox transacional com RabbitMQ. Java 21 / Spring Boot 3.
- **[node-b2b-orders](https://github.com/ricartefelipe/node-b2b-orders)** — API de pedidos e inventário: NestJS 10, Prisma, PostgreSQL, Redis e RabbitMQ. Outbox pattern, worker assíncrono, idempotência, paginação keyset e circuit breaker.
- **[py-payments-ledger](https://github.com/ricartefelipe/py-payments-ledger)** — Motor de pagamentos com ledger de dupla entrada: FastAPI, SQLAlchemy, Stripe, PostgreSQL e RabbitMQ. Multi-gateway, criptografia at-rest e reconciliação financeira.
- **[fluxe-b2b-suite](https://github.com/ricartefelipe/fluxe-b2b-suite)** — Suite frontend B2B: Loja, Portal de Operações e Console de Administração. Angular 21 / Nx monorepo com integração aos três backends.

### Outros projetos

### [archlens-ai](https://github.com/ricartefelipe/archlens-ai)

Plataforma multi-tenant para governança e diagnóstico arquitetural: ingestão de repositórios, análise estática de artefatos (código, contratos OpenAPI, migrations, Docker, pipelines), relatórios com evidências rastreáveis, registro de decisões (ADR), recuperação contextual em documentação (RAG), processamento assíncrono com RabbitMQ, OIDC com Keycloak, worker Python/FastAPI e interface Next.js. Backend Quarkus 3, PostgreSQL com pgvector, Liquibase, Redis, Docker Compose.

### [comercial-cloud](https://github.com/ricartefelipe/comercial-cloud)

Plataforma SaaS multitenant para PDV e retaguarda web: vendas no balcão com busca rápida, carrinho e pagamentos; gestão de produtos, estoque, clientes, caixa, financeiro e dashboard. Isolamento por tenant, arquitetura hexagonal no backend Quarkus 3 (Java 21), Hibernate Panache, Liquibase, OpenAPI, frontend Next.js 14 com PDV dedicado, PostgreSQL e Docker Compose. Preparado para evoluir para JWT/OIDC (Keycloak).

### [cards-api](https://github.com/ricartefelipe/cards-api)

API REST (Quarkus) para criação de contas bancárias e emissão de cartões físicos e virtuais, com simulação local de processadora e CVV em memória.

### [assinaflow](https://github.com/ricartefelipe/assinaflow)

Sistema de gestão de assinaturas voltado a um cenário de streaming, com foco em regras de negócio, operação e evolução segura.

### [order-service](https://github.com/ricartefelipe/order-service)

Microserviço de pedidos com persistência em PostgreSQL, cálculo de totais e APIs voltadas a integração e consulta.

### [oficina-springboot-mvp](https://github.com/ricartefelipe/oficina-springboot-mvp)

Sistema para gestão de serviços em oficinas mecânicas, com ênfase em fluxo operacional e feedback em tempo real para clientes.

### [oficina-app](https://github.com/ricartefelipe/oficina-app)

Aplicação Spring Boot com Dockerfile, manifests Helm, CI de build/imagem e deploy em Kubernetes. Inclui autenticação via Lambda serverless (Python) e infraestrutura como código com Terraform.

### [oficina-auth-lambda](https://github.com/ricartefelipe/oficina-auth-lambda)

Função serverless de autenticação (CPF + JWT) em Python, com deploy via SAM/Terraform na AWS Lambda e testes automatizados.

### [oficina-infra-kubernetes-](https://github.com/ricartefelipe/oficina-infra-kubernetes-)

Terraform do cluster Kubernetes: stack Kind para laboratório local e estrutura preparada para EKS em nuvem.

### [oficina-infra-database](https://github.com/ricartefelipe/oficina-infra-database)

Terraform da base de dados na nuvem: VPC, subnets, RDS PostgreSQL, security groups e configurações de rede.

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
