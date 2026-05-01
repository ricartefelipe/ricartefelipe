<h1 align="center">Felipe Ricarte Magalhães</h1>

<p align="center">
  <strong>Staff Software Engineer</strong> &nbsp;·&nbsp; Backend Architecture &nbsp;·&nbsp; Multi-tenant SaaS
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/felipe-ricarte-magalhaes/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?logo=linkedin&logoColor=white" alt="LinkedIn"/></a>&nbsp;
  <a href="mailto:felipericartem@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" alt="Email"/></a>&nbsp;
  <img src="https://komarev.com/ghpvc/?username=ricartefelipe&style=flat&color=grey" alt="Profile views"/>
</p>

---

Engenheiro de software com foco em **sistemas distribuídos B2B**, arquitetura multi-tenant e governança de acesso. Projeto, implemento e opero plataformas SaaS que precisam escalar com isolamento de dados, auditoria completa e contratos claros entre serviços.

Atualmente construindo uma plataforma B2B completa — do control plane ao frontend — como portfólio de engenharia de referência.

---

## Princípios de Engenharia

| Princípio | Na Prática |
|-----------|-----------|
| **Isolamento por design** | Cada tenant opera com dados completamente segregados via ABAC — sem vazamento, sem workaround |
| **Contratos primeiro** | Serviços se comunicam por eventos tipados (outbox pattern) e REST com schemas versionados |
| **Observabilidade nativa** | Métricas, traces e logs estruturados desde o dia zero — não como afterthought |
| **Idempotência obrigatória** | Todo endpoint de escrita e todo consumer de fila são idempotentes por contrato |

---

## Arquitetura da Plataforma B2B

Uma plataforma end-to-end com 4 repositórios independentes, comunicação assíncrona via outbox/event-driven, e frontend unificado:

```mermaid
flowchart LR
    subgraph "Frontend · Angular / Nx"
        SHOP["Shop"]
        OPS["Ops Portal"]
        ADMIN["Admin Console"]
    end

    subgraph "Control Plane · Java / Spring Boot"
        CORE["spring-saas-core"]
        AUTH["JWT + ABAC"]
        FLAGS["Feature Flags"]
        AUDIT["Audit Log"]
    end

    subgraph "Domain Services"
        ORDERS["node-b2b-orders\n NestJS / Prisma"]
        PAY["py-payments-ledger\n FastAPI / SQLAlchemy"]
    end

    MQ[("RabbitMQ\n(outbox → events)")]

    SHOP & OPS & ADMIN -->|"REST + JWT"| CORE
    SHOP & OPS -->|REST| ORDERS
    SHOP -->|REST| PAY
    CORE -.->|outbox| MQ
    MQ -.-> ORDERS
    ORDERS -.->|domain events| MQ
    MQ -.-> PAY
```

---

## Repositórios Principais

<table>
  <tr>
    <td width="50%">
      <h3><a href="https://github.com/ricartefelipe/spring-saas-core">spring-saas-core</a></h3>
      <p>Control plane multi-tenant: gestão de tenants, RBAC/ABAC, feature flags, auditoria, emissão de JWT e outbox para eventos.</p>
      <p>
        <img src="https://img.shields.io/badge/Java_21-ED8B00?logo=openjdk&logoColor=white" alt="Java"/>
        <img src="https://img.shields.io/badge/Spring_Boot_3-6DB33F?logo=springboot&logoColor=white" alt="Spring"/>
        <img src="https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white" alt="PG"/>
        <img src="https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white" alt="Redis"/>
      </p>
    </td>
    <td width="50%">
      <h3><a href="https://github.com/ricartefelipe/fluxe-b2b-suite">fluxe-b2b-suite</a></h3>
      <p>Suite frontend B2B com 3 aplicações: Shop (catálogo + carrinho), Ops Portal (gestão operacional) e Admin Console (governança).</p>
      <p>
        <img src="https://img.shields.io/badge/Angular_21-DD0031?logo=angular&logoColor=white" alt="Angular"/>
        <img src="https://img.shields.io/badge/Nx-143055?logo=nx&logoColor=white" alt="Nx"/>
        <img src="https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white" alt="TS"/>
        <img src="https://img.shields.io/badge/pnpm-F69220?logo=pnpm&logoColor=white" alt="pnpm"/>
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3><a href="https://github.com/ricartefelipe/node-b2b-orders">node-b2b-orders</a></h3>
      <p>API de pedidos e inventário B2B com worker assíncrono, outbox pattern, rate limiting e idempotência nativa.</p>
      <p>
        <img src="https://img.shields.io/badge/NestJS_10-E0234E?logo=nestjs&logoColor=white" alt="NestJS"/>
        <img src="https://img.shields.io/badge/Prisma-2D3748?logo=prisma&logoColor=white" alt="Prisma"/>
        <img src="https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white" alt="PG"/>
        <img src="https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white" alt="RMQ"/>
      </p>
    </td>
    <td width="50%">
      <h3><a href="https://github.com/ricartefelipe/py-payments-ledger">py-payments-ledger</a></h3>
      <p>Motor de pagamentos com ledger contábil double-entry, integração Stripe e reconciliação automática.</p>
      <p>
        <img src="https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white" alt="FastAPI"/>
        <img src="https://img.shields.io/badge/SQLAlchemy-D71F00?logo=python&logoColor=white" alt="SQLAlchemy"/>
        <img src="https://img.shields.io/badge/Stripe-635BFF?logo=stripe&logoColor=white" alt="Stripe"/>
        <img src="https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white" alt="PG"/>
      </p>
    </td>
  </tr>
</table>

---

## Stack Completa

<table>
  <tr>
    <td><strong>Linguagens</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Java_21-ED8B00?logo=openjdk&logoColor=white"/>
      <img src="https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white"/>
      <img src="https://img.shields.io/badge/Python_3.12-3776AB?logo=python&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Frameworks</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Spring_Boot_3-6DB33F?logo=springboot&logoColor=white"/>
      <img src="https://img.shields.io/badge/NestJS_10-E0234E?logo=nestjs&logoColor=white"/>
      <img src="https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white"/>
      <img src="https://img.shields.io/badge/Angular_21-DD0031?logo=angular&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Dados</strong></td>
    <td>
      <img src="https://img.shields.io/badge/PostgreSQL_16-336791?logo=postgresql&logoColor=white"/>
      <img src="https://img.shields.io/badge/Redis_7-DC382D?logo=redis&logoColor=white"/>
      <img src="https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Infra & Ops</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white"/>
      <img src="https://img.shields.io/badge/Terraform-844FBA?logo=terraform&logoColor=white"/>
      <img src="https://img.shields.io/badge/Railway-0B0D0E?logo=railway&logoColor=white"/>
      <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?logo=githubactions&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Observabilidade</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white"/>
      <img src="https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white"/>
      <img src="https://img.shields.io/badge/OpenTelemetry-000000?logo=opentelemetry&logoColor=white"/>
    </td>
  </tr>
</table>

---

## Outros Projetos

| Repo | Descrição |
|------|-----------|
| [`oficina-springboot-mvp`](https://github.com/ricartefelipe/oficina-springboot-mvp) | Sistema de gerenciamento de oficinas mecânicas com feedback em tempo real |
| [`oficina-auth-lambda`](https://github.com/ricartefelipe/oficina-auth-lambda) | Função serverless de autenticação (CPF, JWT) — Python, SAM, Terraform |
| [`oficina-infra-database`](https://github.com/ricartefelipe/oficina-infra-database) | IaC para banco de dados na nuvem (VPC, subnets, RDS, Security Groups) |
| [`oficina-infra-kubernetes-`](https://github.com/ricartefelipe/oficina-infra-kubernetes-) | IaC para cluster Kubernetes (Kind para lab, EKS para produção) |
| [`assinaflow`](https://github.com/ricartefelipe/assinaflow) | Sistema de gestão de assinaturas para serviço de streaming |
| [`order-service`](https://github.com/ricartefelipe/order-service) | Microserviço de pedidos com cálculo de totais e persistência PostgreSQL |

---

<details>
<summary><strong>GitHub Stats</strong></summary>
<br/>
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=ricartefelipe&show_icons=true&theme=default&hide_border=true&count_private=true" alt="Stats" height="165"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ricartefelipe&layout=compact&hide_border=true&langs_count=8" alt="Langs" height="165"/>
</p>
<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=ricartefelipe&hide_border=true" alt="Streak" height="165"/>
</p>
</details>
