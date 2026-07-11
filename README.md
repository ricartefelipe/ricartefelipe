# Felipe Ricarte Magalhães

**Hands-on Software Architect · Senior Backend Engineer**

Projeto e implemento backends, plataformas e integrações que precisam operar em produção com segurança, rastreabilidade, confiabilidade e capacidade de evolução.

Tenho mais de 17 anos de experiência em tecnologia, atuando entre arquitetura, desenvolvimento e sustentação de sistemas corporativos, financeiros, bancários e distribuídos. Minha atuação combina desenho técnico, implementação, integração entre sistemas, mensageria, observabilidade, segurança aplicada e apoio técnico a times em ambientes críticos.

Minha base principal é **Java e Kotlin**, com forte atuação em **Spring Boot, Quarkus, APIs, microsserviços, BFFs, mensageria, bancos relacionais/NoSQL, cloud, containers, segurança, testes e observabilidade**.

---

## Repositórios em destaque

Estes são os principais projetos públicos que representam meu foco atual em arquitetura aplicada, backend, sistemas distribuídos, segurança, mensageria, cloud e confiabilidade operacional.

| Projeto | Foco principal |
|---|---|
| **archlens-ai** | IA aplicada à engenharia de software, análise arquitetural, RAG, processamento assíncrono e governança técnica |
| **spring-saas-core** | SaaS B2B multitenant, RBAC/ABAC, feature flags, auditoria, outbox e observabilidade |
| **assinaflow** | Gestão de assinaturas, renovação automática, concorrência, idempotência, RabbitMQ, Redis e Testcontainers |
| **cards-api** | API financeira de contas e cartões, Keycloak, OAuth2/OIDC, JWT, webhooks e segurança aplicada |
| **py-payments-ledger** | Motor de pagamentos com ledger de dupla entrada, reconciliação financeira, idempotência e outbox |
| **node-b2b-orders** | Pedidos e inventário B2B, outbox, worker assíncrono, Redis, RabbitMQ, ABAC e circuit breaker |

---

## Atuação principal

- Backend Java/Kotlin em ambientes corporativos críticos
- Arquitetura hands-on, com participação em desenho, código e evolução técnica
- APIs REST, contratos, integrações corporativas e BFFs
- Sistemas distribuídos, microsserviços e comunicação assíncrona
- Mensageria, eventos, outbox, idempotência, retry, DLQ e reprocessamento
- SQL, NoSQL, cache, read models e estratégias de persistência
- Segurança aplicada, identidade, autorização, auditoria e rastreabilidade
- Observabilidade com logs estruturados, métricas, tracing e correlação
- Evolução segura em produção com migrations, versionamento, feature flags e rollback
- Apoio técnico a times, revisão de soluções e decisões arquiteturais

---

## Stack principal

**Linguagens e frameworks**  
Java · Kotlin · Spring Boot · Quarkus · Node.js · Python

**Dados, cache e migrações**  
PostgreSQL · SQL Server · MariaDB · MongoDB · Redis · Liquibase · Flyway

**Integração e mensageria**  
REST · OpenAPI/Swagger · Kafka · RabbitMQ · AWS SQS · GCP Pub/Sub · eventos · outbox · idempotência

**Segurança e identidade**  
Keycloak · OAuth2/OIDC · JWT · RBAC/ABAC · auditoria · segurança aplicada a APIs

**Cloud, containers e execução**  
Docker · Kubernetes · OpenShift · AWS · GCP · Azure · CI/CD · automação de deploy

**Observabilidade, testes e qualidade**  
Micrometer · Prometheus · Grafana · Datadog · New Relic · ELK · OpenTelemetry · JUnit · Mockito · Testcontainers · JaCoCo · Sonar

Também tenho experiência com frontend e mobile híbrido em contextos de integração e apoio ponta a ponta, incluindo Angular, React, Vue, Ionic e Flutter. Meu foco principal, porém, continua sendo backend, arquitetura aplicada e sistemas distribuídos.

---

## Projetos selecionados

### Plataformas SaaS, multitenancy e arquitetura aplicada

| Projeto | Descrição | Stack |
|---|---|---|
| **archlens-ai** | Plataforma multitenant para governança e diagnóstico arquitetural, com ingestão de repositórios, análise estática de código, contratos OpenAPI, ADRs, RAG, processamento assíncrono e relatórios com evidências rastreáveis. | Quarkus 3 · Java 21 · PostgreSQL/pgvector · Redis · RabbitMQ · Keycloak · Next.js · Python |
| **spring-saas-core** | Serviço central de governança multitenant para SaaS B2B, com tenants, RBAC/ABAC, feature flags, auditoria, JWT, outbox transacional, observabilidade e documentação OpenAPI. | Java 21 · Spring Boot 3 · PostgreSQL · Redis · RabbitMQ · Docker |
| **comercial-cloud** | Plataforma SaaS multitenant para PDV e retaguarda web, com produtos, estoque, caixa, vendas, financeiro, dashboard, isolamento por tenant, auditoria, OpenAPI e migrations. | Quarkus 3 · Java 21 · PostgreSQL · Next.js · Docker · Keycloak |

---

### Sistemas transacionais, mensageria e confiabilidade operacional

| Projeto | Descrição | Stack |
|---|---|---|
| **assinaflow** | Sistema de gestão de assinaturas para streaming, com renovação automática, cancelamento no fim do ciclo, retry determinístico de cobrança, proteção contra concorrência, idempotência no consumidor e execução segura em múltiplas instâncias. | Java 21 · Spring Boot 3 · PostgreSQL · Liquibase · RabbitMQ · Redis · Testcontainers · Prometheus |
| **py-payments-ledger** | Motor de pagamentos com ledger de dupla entrada, multi-gateway, reconciliação financeira, criptografia at-rest, idempotência, outbox e persistência transacional. | Python · FastAPI · SQLAlchemy · PostgreSQL · RabbitMQ |
| **node-b2b-orders** | API de pedidos e inventário para cenário B2B, com outbox pattern, worker assíncrono, idempotência, paginação keyset, Redis, RabbitMQ, PostgreSQL, ABAC e circuit breaker. | Node.js · NestJS · Prisma · PostgreSQL · Redis · RabbitMQ |
| **order-service** | Microserviço de pedidos com foco em recebimento, processamento, cálculo de totais e organização de fluxo transacional. | Java/Spring · APIs REST · persistência · integração |

---

### APIs financeiras, cartões e segurança aplicada

| Projeto | Descrição | Stack |
|---|---|---|
| **cards-api** | API REST para gestão de contas, clientes e cartões físicos/virtuais, com autenticação OAuth2/JWT via Keycloak, webhooks com API Key, integração simulada com transportadora/processadora e consulta de CVV sob demanda sem persistência sensível. | Quarkus · Java 21 · MariaDB · Flyway · Keycloak · OAuth2/OIDC · JWT · Docker · JaCoCo |
| **oficina-auth-lambda** | Função serverless de autenticação com CPF e JWT, usando AWS Lambda, SAM/Terraform, testes e CI. | Python · AWS Lambda · SAM · Terraform · JWT |

---

### B2B, frontend integrado e experiência operacional

| Projeto | Descrição | Stack |
|---|---|---|
| **fluxe-b2b-suite** | Suite frontend B2B com loja, portal de operações e console administrativo, integrando governança, pedidos e pagamentos em uma experiência operacional única. | Angular · Nx · TypeScript · SSR · APIs REST |

---

### Ecossistema Oficina e laboratórios cloud-native

| Projeto | Descrição | Stack |
|---|---|---|
| **oficina-app** | Aplicação Spring Boot com Dockerfile, manifests Helm, CI de build/imagem e deploy em Kubernetes. | Java · Spring Boot · Docker · Helm · Kubernetes |
| **oficina-execution-service** | Serviço de execução dentro do domínio de oficina, separado por responsabilidade e preparado para integração com outros serviços do ecossistema. | Java · Spring Boot · APIs REST |
| **oficina-billing-service** | Serviço de cobrança/faturamento dentro do ecossistema de oficina, isolando regras e responsabilidades financeiras do domínio. | Java · Spring Boot · APIs REST |
| **oficina-car-service** | Serviço responsável por dados e operações relacionadas a veículos no contexto de oficina. | Java · Spring Boot · APIs REST |
| **oficina-springboot-mvc** | Sistema de gerenciamento de serviços em oficinas mecânicas, com abordagem MVC e organização tradicional de aplicação web. | Java · Spring Boot MVC |

---

### Infraestrutura, automação e apoio técnico

| Projeto | Descrição | Stack |
|---|---|---|
| **oficina-infra-kubernetes** | Infraestrutura como código para cluster Kubernetes, com laboratório local em Kind e estrutura preparada para EKS. | Kubernetes · Kind · EKS · Terraform |
| **oficina-infra-database** | Infraestrutura como código para banco de dados em nuvem, incluindo VPC, subnets, RDS PostgreSQL e security groups. | AWS · RDS · PostgreSQL · Terraform |

---

## Como eu costumo trabalhar

- Começo pelo domínio, fluxo de negócio, integrações e riscos antes de escolher tecnologia
- Prefiro contratos claros, responsabilidades bem separadas e sistemas fáceis de operar
- Uso mensageria quando ela resolve acoplamento, resiliência, volume ou fluxo assíncrono real
- Trato idempotência, retry, DLQ e reprocessamento como requisitos de sistemas distribuídos
- Considero observabilidade, segurança e rastreabilidade como parte estrutural da arquitetura
- Evito complexidade gratuita, mas também evito simplificações que escondem acoplamento ou risco
- Busco arquiteturas evolutivas, previsíveis e sustentáveis em produção

---

## Interesses técnicos atuais

- Arquitetura de sistemas distribuídos
- Modernização de aplicações corporativas
- Plataformas internas e engenharia de software aplicada
- Event-driven architecture, outbox, idempotência e consistência operacional
- Observabilidade, confiabilidade e sustentação de sistemas críticos
- IA aplicada à engenharia de software, análise de código, RAG e automação técnica

---

## Contato

- LinkedIn: https://www.linkedin.com/in/felipe-ricarte-magalhaes/
- GitHub: https://github.com/ricartefelipe
