<h1 align="center">Felipe Ricarte Magalhães</h1>

<p align="center">
  <strong>Arquiteto de backend na prática</strong><br/>
  Java, Spring Boot, Quarkus e Kotlin · APIs, nuvem, sistemas distribuídos, eventos e observabilidade
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/felipe-ricarte-magalhaes/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?logo=linkedin&logoColor=white" alt="LinkedIn"/></a>&nbsp;
  <a href="mailto:felipericartem@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" alt="Email"/></a>&nbsp;
  <a href="https://github.com/ricartefelipe"><img src="https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white" alt="GitHub"/></a>&nbsp;
  <img src="https://komarev.com/ghpvc/?username=ricartefelipe&style=flat&color=grey" alt="Profile views"/>
</p>

---

Sou arquiteto de software com **mais de 17 anos** de experiência construindo, evoluindo e mantendo sistemas corporativos e plataformas críticas em produção.

Atuo desde a definição da arquitetura até o código: decisões técnicas viram contratos de API, testes, pipelines, métricas e algo que a operação consegue sustentar. Meu eixo principal é o ecossistema **Java** (Spring Boot, Quarkus, Kotlin), com foco em sistemas distribuídos, arquitetura orientada a eventos, multi-tenant e observabilidade.

Não escolho tecnologia por modinha: o contexto (problema, time, operação e custo total) manda na decisão.

Hoje dedico esforço a uma **plataforma B2B de referência**, com control plane, serviços de domínio e frontend integrados, para exercitar multi-tenant, governança de acesso, mensageria e boas práticas de produção.

---

## Princípios na prática

| Princípio | O que significa |
|-----------|-----------------|
| **Isolamento por desenho** | Cada tenant opera com dados segregados via ABAC, sem vazamento entre contextos e sem atalhos frágeis. |
| **Contratos em primeiro lugar** | Integração por eventos tipados (outbox) e REST com esquemas versionados e previsíveis. |
| **Observabilidade desde o início** | Métricas, rastros e logs estruturados entram no desenho, não como complemento depois do go-live. |
| **Idempotência onde há efeito colateral** | Escritas em API e consumidores de fila tratam reprocessamento e duplicidade de forma explícita. |
| **Contexto acima do framework** | Spring Boot, Quarkus, serverless ou uma solução mais simples: depende do cenário, não da tendência. |
| **Produção como critério** | Se não dá para operar, rastrear e evoluir com segurança, a entrega ainda não está madura. |

---

## Arquitetura da plataforma B2B

Plataforma ponta a ponta com quatro repositórios independentes, integração assíncrona (outbox e eventos) e frontend unificado:

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

## Repositórios principais

<table>
  <tr>
    <td width="50%">
      <h3><a href="https://github.com/ricartefelipe/spring-saas-core">spring-saas-core</a></h3>
      <p><strong>Control plane multi-tenant.</strong> Cadastro e ciclo de vida de tenants, papéis e políticas RBAC/ABAC, feature flags com auditoria, emissão e validação de JWT e padrão outbox para publicar eventos de forma consistente com o estado no banco. Centraliza o que é transversal às aplicações B2B sem acoplar regra de negócio de cada domínio.</p>
      <p>
        <img src="https://img.shields.io/badge/Java_21-ED8B00?logo=openjdk&logoColor=white" alt="Java"/>
        <img src="https://img.shields.io/badge/Spring_Boot_3-6DB33F?logo=springboot&logoColor=white" alt="Spring"/>
        <img src="https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white" alt="PG"/>
        <img src="https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white" alt="Redis"/>
      </p>
    </td>
    <td width="50%">
      <h3><a href="https://github.com/ricartefelipe/fluxe-b2b-suite">fluxe-b2b-suite</a></h3>
      <p><strong>Monorepo Nx com três apps Angular.</strong> <em>Shop</em> para catálogo, carrinho e jornada de compra; <em>Ops Portal</em> para operações do dia a dia; <em>Admin Console</em> para governança e configurações sensíveis. Compartilha bibliotecas de UI e clientes HTTP, alinhado ao control plane e às APIs de pedidos e pagamentos.</p>
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
      <p><strong>Serviço de pedidos e estoque B2B.</strong> API NestJS com Prisma sobre PostgreSQL, workers para processamento assíncrono, outbox para consistência com mensageria, limites de taxa e chaves de idempotência em operações críticas. Pensado para conviver com o control plane (identidade e autorização) e publicar eventos consumidos por outros serviços.</p>
      <p>
        <img src="https://img.shields.io/badge/NestJS_10-E0234E?logo=nestjs&logoColor=white" alt="NestJS"/>
        <img src="https://img.shields.io/badge/Prisma-2D3748?logo=prisma&logoColor=white" alt="Prisma"/>
        <img src="https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white" alt="PG"/>
        <img src="https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white" alt="RMQ"/>
      </p>
    </td>
    <td width="50%">
      <h3><a href="https://github.com/ricartefelipe/py-payments-ledger">py-payments-ledger</a></h3>
      <p><strong>Pagamentos com razão contábil em partidas dobradas.</strong> FastAPI e SQLAlchemy modelam lançamentos, integração com Stripe para captura e webhooks, filas para efeitos colaterais e reconciliação. Objetivo: rastreabilidade financeira e consistência entre extrato externo e saldos internos.</p>
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

## Stack

<table>
  <tr>
    <td><strong>Linguagens</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Java_21-ED8B00?logo=openjdk&logoColor=white"/>
      <img src="https://img.shields.io/badge/Kotlin-7F52FF?logo=kotlin&logoColor=white"/>
      <img src="https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white"/>
      <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Frameworks</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Spring_Boot_3-6DB33F?logo=springboot&logoColor=white"/>
      <img src="https://img.shields.io/badge/Quarkus-4695EB?logo=quarkus&logoColor=white"/>
      <img src="https://img.shields.io/badge/NestJS-E0234E?logo=nestjs&logoColor=white"/>
      <img src="https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white"/>
      <img src="https://img.shields.io/badge/Angular-DD0031?logo=angular&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Dados e mensageria</strong></td>
    <td>
      <img src="https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white"/>
      <img src="https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white"/>
      <img src="https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white"/>
      <img src="https://img.shields.io/badge/Kafka-231F20?logo=apachekafka&logoColor=white"/>
      <img src="https://img.shields.io/badge/Liquibase-2962FF?logo=liquibase&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Nuvem</strong></td>
    <td>
      <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonwebservices&logoColor=white"/>
      <img src="https://img.shields.io/badge/GCP-4285F4?logo=googlecloud&logoColor=white"/>
      <img src="https://img.shields.io/badge/Azure-0078D4?logo=microsoftazure&logoColor=white"/>
      <img src="https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white"/>
      <img src="https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Infra e CI/CD</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Terraform-844FBA?logo=terraform&logoColor=white"/>
      <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?logo=githubactions&logoColor=white"/>
      <img src="https://img.shields.io/badge/Railway-0B0D0E?logo=railway&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Segurança</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Keycloak-4D4D4D?logo=keycloak&logoColor=white"/>
      <img src="https://img.shields.io/badge/OAuth2/OIDC-000000?logo=openid&logoColor=white"/>
      <img src="https://img.shields.io/badge/JWT-000000?logo=jsonwebtokens&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td><strong>Observabilidade</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white"/>
      <img src="https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white"/>
      <img src="https://img.shields.io/badge/OpenTelemetry-000000?logo=opentelemetry&logoColor=white"/>
      <img src="https://img.shields.io/badge/OpenAPI-6BA539?logo=openapiinitiative&logoColor=white"/>
    </td>
  </tr>
</table>

---

## Outros projetos

| Repositório | Descrição |
|-------------|-----------|
| [`oficina-springboot-mvp`](https://github.com/ricartefelipe/oficina-springboot-mvp) | MVP em Spring Boot para gestão de oficinas mecânicas: cadastros, ordens de serviço e notificações. Inclui experimentos com feedback em tempo real (WebSocket ou canal parecido) para status de serviço. |
| [`oficina-auth-lambda`](https://github.com/ricartefelipe/oficina-auth-lambda) | Autenticação serverless: validação de CPF, emissão de JWT e integração com API Gateway. Stack com Python, AWS SAM e Terraform para empacotar e versionar a função e permissões. |
| [`oficina-infra-database`](https://github.com/ricartefelipe/oficina-infra-database) | Infraestrutura como código para banco na nuvem: rede (VPC, subnets), RDS, security groups e parâmetros alinhados ao ambiente do MVP da oficina. |
| [`oficina-infra-kubernetes-`](https://github.com/ricartefelipe/oficina-infra-kubernetes-) | Terraform e manifests para subir cluster Kubernetes: Kind em laboratório e desenho preparado para EKS em produção, com foco em rede e add-ons básicos. |
| [`assinaflow`](https://github.com/ricartefelipe/assinaflow) | Fluxo de assinaturas para um serviço de streaming: planos, ciclo de cobrança e regras de ativação/cancelamento, com persistência e APIs para o painel. |
| [`order-service`](https://github.com/ricartefelipe/order-service) | Microserviço de pedidos com cálculo de totais, descontos quando aplicável e persistência em PostgreSQL. Útil como laboratório de contratos REST e testes de integração. |

---

<details>
<summary><strong>Estatísticas no GitHub</strong></summary>
<br/>
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=ricartefelipe&show_icons=true&theme=tokyonight&hide_border=true&count_private=true&include_all_commits=true" alt="Estatísticas do GitHub" height="165"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ricartefelipe&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Linguagens mais usadas" height="165"/>
</p>
<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=ricartefelipe&hide_border=true" alt="Streak" height="165"/>
</p>
</details>
