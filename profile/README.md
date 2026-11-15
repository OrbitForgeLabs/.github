<div align="center">

# OrbitForgeLabs

### Building thoughtful software, one step at a time.

We are an independent software development organization focused on building practical, reliable digital products.

[**Explore our work**](https://github.com/OrbitForgeLabs) · [**Current project: PrepCircle**](https://github.com/OrbitForgeLabs/PrepCircle)

</div>

---

## What we're building

### PrepCircle

A peer-to-peer interview preparation platform designed to help developers find practice partners, schedule reciprocal interview sessions, and exchange feedback.

PrepCircle is being developed incrementally, with a local-first approach and an emphasis on a maintainable foundation.

**Project status:** Early development. The repository currently contains the .NET 10 solution foundation, Aspire AppHost, shared ServiceDefaults, and an Identity API skeleton with local PostgreSQL development infrastructure. Authentication, the remaining backend services, gateway, and frontend are planned for later phases.

> The PrepCircle source repository is currently private. This overview describes the project without exposing its source code.

## Engineering direction

Our current project architecture is built around:

| Area | Technology |
|---|---|
| Backend | .NET 10, ASP.NET Core |
| Frontend | Angular |
| Data | PostgreSQL, Entity Framework Core |
| Messaging | RabbitMQ |
| Gateway | YARP |
| Local orchestration | .NET Aspire |
| Observability | OpenTelemetry |

These technologies represent the project's selected architecture; not every component has been implemented yet.

## How we work

- **Incremental delivery** — build and validate the foundation before expanding.
- **Maintainability** — favor clear boundaries, readable code, and documented decisions.
- **Reliability** — consider health checks, observability, resilience, and failure handling.
- **Security** — use established identity standards and keep credentials out of source control.
- **Cost awareness** — prioritize zero-cost development and infrastructure choices.

## Follow the work

- [OrbitForgeLabs repositories](https://github.com/OrbitForgeLabs)
- [PrepCircle repository](https://github.com/OrbitForgeLabs/PrepCircle)

---

<div align="center">

*Ideas into software. Progress through engineering.*

</div>
