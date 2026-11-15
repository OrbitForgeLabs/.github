<div align="center">
  <img src="assets/orbitforge-banner.svg" alt="OrbitForgeLabs — Engineering with intention" width="100%" />

  <h3>Thoughtful software. Practical products. Reliable foundations.</h3>

  <p>
    <a href="https://github.com/OrbitForgeLabs">Repositories</a>
    &nbsp;·&nbsp;
    <a href="#featured-product">Featured product</a>
    &nbsp;·&nbsp;
    <a href="#engineering-approach">Engineering approach</a>
  </p>
</div>

---

## Who we are

**OrbitForgeLabs** is an independent software development organization focused on building useful digital products through deliberate engineering, clear architecture and incremental delivery.

We value practical solutions over unnecessary complexity, and strong foundations over rushing to features.

<a id="featured-product"></a>

## Featured product

<div align="center">
  <h3>PrepCircle</h3>
  <p><strong>Peer-to-peer interview practice for developers.</strong></p>
  <p>Find practice partners, arrange reciprocal interview sessions, switch between interviewer and candidate roles, and exchange structured feedback.</p>
  <p>
    <img src="https://img.shields.io/badge/Product-in_development-2563EB?style=for-the-badge" alt="Product in development" />
    <img src="https://img.shields.io/badge/Approach-local--first-0F766E?style=for-the-badge" alt="Local first approach" />
  </p>
</div>

PrepCircle is being built in stages. Its source repository is private while the product is under development; this page shares the product direction and a high-level view of its engineering foundation.

## Architecture at a glance

The diagram distinguishes the foundation already present in the repository from components selected for later phases.

```mermaid
flowchart LR
    DEV["Developers"]
    WEB["Angular web app<br/>Planned"]
    GATE["YARP API Gateway<br/>Planned"]
    ID["Identity API<br/>Foundation in place"]
    DB[("PostgreSQL<br/>Local setup configured")]
    ASPIRE[".NET Aspire AppHost<br/>Local orchestration"]
    DEFAULTS["ServiceDefaults<br/>Health · Telemetry · Resilience"]
    SERVICES["Profile · Matching<br/>Interview · Notification<br/>Planned services"]
    MQ["RabbitMQ<br/>Planned messaging"]

    DEV --> WEB
    WEB --> GATE
    GATE --> ID
    ID --> DB
    ASPIRE -. orchestrates .-> ID
    DEFAULTS -. shared defaults .-> ID
    GATE -. future routing .-> SERVICES
    SERVICES -. future events .-> MQ

    classDef present fill:#123B32,stroke:#34D399,color:#ECFDF5,stroke-width:1.5px
    classDef planned fill:#172B4D,stroke:#60A5FA,color:#EFF6FF,stroke-width:1.5px
    classDef infra fill:#29234B,stroke:#A78BFA,color:#F5F3FF,stroke-width:1.5px
    classDef actor fill:#263445,stroke:#94A3B8,color:#F8FAFC,stroke-width:1.5px

    class ID,DB,ASPIRE,DEFAULTS present
    class WEB,GATE,SERVICES,MQ planned
    class DEV actor
```

<sub>Green indicates the current foundation; blue indicates planned components. The diagram is an architectural direction, not a claim that every service is already implemented.</sub>

## Project foundation

The current repository baseline includes:

| Area | Current state |
|---|---|
| .NET solution | .NET 10 solution and shared build configuration |
| Local orchestration | .NET Aspire AppHost and ServiceDefaults |
| Identity | Identity API skeleton registered with Aspire |
| Database | Dedicated PostgreSQL 17 local Compose setup |
| Data access | EF Core 10 / Npgsql connection configured for Identity |
| Health | PostgreSQL connectivity health check |

### Planned in later phases

- Identity authentication using ASP.NET Core Identity and OpenIddict, with EF Core migrations.
- YARP as the public API gateway.
- Profile, Matching, Interview and Notification services, each owning its database.
- RabbitMQ for asynchronous integration events when a consuming service needs them.
- Angular frontend, initially running separately from Aspire.

No delivery dates are published; implementation will proceed incrementally as each foundation is validated.

## Technology direction

<div align="center">

**Backend & API**

<img src="https://img.shields.io/badge/.NET_10-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt=".NET 10" />
<img src="https://img.shields.io/badge/ASP.NET_Core-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="ASP.NET Core" />
<img src="https://img.shields.io/badge/YARP-planned-64748B?style=flat-square" alt="YARP planned" />

**Frontend**

<img src="https://img.shields.io/badge/Angular-planned-DD0031?style=flat-square&logo=angular&logoColor=white" alt="Angular planned" />

**Data & messaging**

<img src="https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL" />
<img src="https://img.shields.io/badge/EF_Core_10-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="Entity Framework Core 10" />
<img src="https://img.shields.io/badge/RabbitMQ-planned-FF6600?style=flat-square&logo=rabbitmq&logoColor=white" alt="RabbitMQ planned" />

**Platform & observability**

<img src="https://img.shields.io/badge/.NET_Aspire-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt=".NET Aspire" />
<img src="https://img.shields.io/badge/OpenTelemetry-7B3FE4?style=flat-square&logo=opentelemetry&logoColor=white" alt="OpenTelemetry" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions" />

</div>

<sub>Badges communicate the selected project stack. Refer to the foundation and roadmap sections above for implementation status.</sub>

<a id="engineering-approach"></a>

## Engineering approach

| Principle | How it guides our work |
|---|---|
| Incremental delivery | Establish and validate foundations before expanding scope. |
| Clear boundaries | Keep service responsibilities and data ownership explicit. |
| Reliability | Design for health checks, observability, resilience and failure handling. |
| Security by design | Keep secrets out of source control and use established identity standards. |
| Cost awareness | Prefer local development and zero-cost, open-source infrastructure. |
| Maintainability | Favor readable code, documented decisions and useful abstractions. |

## Explore

- [Browse OrbitForgeLabs repositories](https://github.com/OrbitForgeLabs)
- [Read about GitHub organization profiles](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/customizing-your-organizations-profile)

<div align="center">

---

**ORBITFORGELABS**

*Engineering with intention. Building with purpose.*

</div>
