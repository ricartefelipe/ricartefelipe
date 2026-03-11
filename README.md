# Felipe Ricarte

Engenheiro de plataforma, construindo infraestrutura B2B SaaS na **Union Solutions**.

Foco em arquitetura multi-tenant, governança (ABAC), contratos entre serviços e observabilidade.

---

### Plataforma B2B — Visao Geral

```mermaid
flowchart LR
    subgraph Frontend
        UI["fluxe-b2b-suite\n(Angular / Nx)"]
    end

    subgraph "Control Plane"
        CORE["spring-saas-core\n(Java / Spring Boot)"]
    end

    subgraph "Domain APIs"
        ORDERS["node-b2b-orders\n(NestJS / Prisma)"]
        PAY["py-payments-ledger\n(FastAPI / SQLAlchemy)"]
    end

    MQ[("RabbitMQ")]

    UI -->|JWT| CORE
    UI -->|REST| ORDERS
    UI -->|REST| PAY
    CORE -.->|outbox| MQ
    MQ -.-> ORDERS
    ORDERS -.->|events| MQ
    MQ -.-> PAY
```

---

### Stack

![Java](https://img.shields.io/badge/Java-21-ED8B00?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2-6DB33F?logo=springboot&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.110-009688?logo=fastapi&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-20-339933?logo=nodedotjs&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-10-E0234E?logo=nestjs&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-21-DD0031?logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-7-DC382D?logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-3-FF6600?logo=rabbitmq&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white)

---

### Projetos

| Repo | O que faz | Stack |
|------|-----------|-------|
| [`spring-saas-core`](https://github.com/ricartefelipe/spring-saas-core) | Control plane multi-tenant: tenants, RBAC/ABAC, feature flags, auditoria, JWT, outbox | Java 21, Spring Boot, PostgreSQL, Redis, RabbitMQ |
| [`fluxe-b2b-suite`](https://github.com/ricartefelipe/fluxe-b2b-suite) | Suite frontend B2B: Shop, Ops Portal, Admin Console | Angular 21, Nx, TypeScript, pnpm |
| [`node-b2b-orders`](https://github.com/ricartefelipe/node-b2b-orders) | API de pedidos e inventario B2B com worker assincrono | NestJS, Prisma, PostgreSQL, Redis, RabbitMQ |
| [`py-payments-ledger`](https://github.com/ricartefelipe/py-payments-ledger) | Motor de pagamentos com ledger contabil double-entry | FastAPI, SQLAlchemy, Stripe, PostgreSQL, RabbitMQ |

---

### Stats

<p>
  <img src="https://github-readme-stats.vercel.app/api?username=ricartefelipe&show_icons=true&theme=default&hide_border=true&count_private=true" alt="Stats" height="160"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ricartefelipe&layout=compact&hide_border=true&langs_count=8" alt="Langs" height="160"/>
</p>
