# Felipe Ricarte Magalhães

**Hands-on Software Architect · Senior Backend Engineer**

Projeto e implemento backends e plataformas que precisam operar em produção com segurança, rastreabilidade e capacidade de evolução.

Tenho mais de 17 anos de experiência em tecnologia, atuando entre arquitetura e implementação. Meu foco principal é backend, sistemas distribuídos, integrações corporativas, mensageria, multitenancy, segurança, observabilidade e confiabilidade operacional.

Trabalho com Java e Kotlin como base principal, usando Spring Boot e Quarkus para entregar APIs, serviços e integrações que precisam evoluir sem comprometer estabilidade, operação e governança.

## Atuação principal

- Backend e APIs em ambientes corporativos críticos
- Sistemas distribuídos e contratos entre serviços
- Arquitetura orientada a eventos quando o domínio exige assincronismo
- Mensageria, fluxos transacionais, idempotência, retry, DLQ e reprocessamento
- Multitenancy, segurança aplicada, identidade, autorização e auditoria
- Observabilidade com métricas, logs estruturados, tracing e correlação
- Evolução segura em produção com migrations, versionamento, feature flags e rollback planejado

## Stack principal

**Linguagens e frameworks:** Java · Kotlin · Spring Boot · Quarkus

**Dados e migrações:** PostgreSQL · Liquibase · Redis

**Integração e contratos:** REST · OpenAPI/Swagger · RabbitMQ · Kafka · eventos · outbox · idempotência

**Segurança e identidade:** Keycloak · OAuth2/OIDC · JWT · RBAC/ABAC

**Execução e nuvem:** Docker · Kubernetes · AWS · GCP · Azure · CI/CD · automação de deploy

Também tenho experiência com Node.js, Python, Ruby, C e frontend com Angular, Vue, React, Ionic e Flutter. Isso apoia revisão ponta a ponta, mas meu foco principal continua sendo backend e arquitetura aplicada.

---

## Arquitetura de referência: Fluxe B2B Platform

Plataforma B2B multitenant composta por backend de governança, pedidos, pagamentos e suite frontend integrada.

### spring-saas-core

Serviço central de governança multitenant para SaaS B2B.

Inclui gestão de tenants, RBAC/ABAC, feature flags, auditoria, JWT, outbox transacional com RabbitMQ, PostgreSQL, Liquibase, observabilidade com Micrometer/Prometheus e documentação OpenAPI.

Stack: Java 21 · Spring Boot 3 · PostgreSQL · Redis · RabbitMQ · Docker · OpenAPI

### node-b2b-orders

API de pedidos e inventário para cenário B2B.

Inclui outbox pattern, worker assíncrono, idempotência, paginação keyset, Redis, RabbitMQ, PostgreSQL, ABAC e circuit breaker.

Stack: Node.js · NestJS · Prisma · PostgreSQL · Redis · RabbitMQ

### py-payments-ledger

Motor de pagamentos com ledger de dupla entrada.

Inclui multi-gateway, reconciliação financeira, criptografia at-rest, idempotência, outbox, PostgreSQL e RabbitMQ.

Stack: Python · FastAPI · SQLAlchemy · PostgreSQL · RabbitMQ

### fluxe-b2b-suite

Suite frontend B2B com loja, portal de operações e console administrativo.

Integra os backends de governança, pedidos e pagamentos em uma experiência única para operação B2B.

Stack: Angular · Nx · TypeScript · SSR · integração com APIs REST

---

## Plataformas SaaS e arquitetura aplicada

### archlens-ai

Plataforma multitenant para governança e diagnóstico arquitetural.

Inclui ingestão de repositórios, análise estática de código, contratos OpenAPI, migrations, Docker, pipelines, relatórios com evidências rastreáveis, ADRs, RAG, processamento assíncrono com RabbitMQ, Keycloak, worker Python/FastAPI e interface Next.js.

Stack: Quarkus 3 · Java 21 · PostgreSQL/pgvector · Liquibase · Redis · RabbitMQ · Keycloak · Next.js · Python

### comercial-cloud

Plataforma SaaS multitenant para PDV e retaguarda web.

Inclui fluxo operacional de varejo com produtos, estoque, caixa, vendas, financeiro, dashboard, isolamento por tenant, trilha de auditoria, erros padronizados com correlation id, contratos OpenAPI e migrations Liquibase.

Stack: Quarkus 3 · Java 21 · PostgreSQL · Next.js · Docker · Keycloak

---

## Cloud, infraestrutura e deploy

### oficina-app

Aplicação Spring Boot com Dockerfile, manifests Helm, CI de build/imagem e deploy em Kubernetes.

### oficina-auth-lambda

Função serverless de autenticação com CPF e JWT usando Python, AWS Lambda, SAM/Terraform, testes e CI.

### oficina-infra-kubernetes

Infraestrutura como código para cluster Kubernetes, com laboratório local em Kind e estrutura preparada para EKS.

### oficina-infra-database

Infraestrutura como código para banco de dados em nuvem, incluindo VPC, subnets, RDS PostgreSQL e security groups.

---

## Como eu costumo trabalhar

- Modelo de domínio e contratos antes de espalhar complexidade entre serviços
- Integrações tratadas com limites claros, rastreabilidade e operações repetíveis
- Mensageria aplicada quando resolve problema real de acoplamento, resiliência ou fluxo assíncrono
- Mudanças em produção planejadas com migrations, versionamento, feature flags e rollback
- Observabilidade e segurança como requisitos estruturais do sistema
- Preferência por sistemas previsíveis, operáveis e fáceis de diagnosticar

## Contato

- LinkedIn: https://www.linkedin.com/in/felipe-ricarte-magalhaes/
- GitHub: https://github.com/ricartefelipe
