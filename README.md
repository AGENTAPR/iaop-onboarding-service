# iaop-onboarding-service

Agent onboarding, KYC, document verification, agreements, and onboarding workflows.

## Purpose

iaop-onboarding-service is part of the **Insurance Agent Operating Platform (IAOP)**, an enterprise
insurance agent lifecycle platform. It owns the **Onboarding** bounded context
(or platform capability) within the IAOP microservices landscape.

## Bounded Context / Ownership

- **Bounded context:** Onboarding
- **Owner:** AGENTAPR
- **Category:** microservice

## Technical Stack

Rust, Axum, PostgreSQL

## Architecture Principles

- Domain-Driven Design (DDD) with explicit bounded contexts
- Hexagonal architecture (ports and adapters)
- Event-driven integration via versioned contracts
- PostgreSQL as the system of record where applicable
- Identity and access via Keycloak
- Workflow orchestration via Flowable BPM where applicable

## Responsibilities

- Agent onboarding orchestration
- KYC and identity verification
- Document verification and storage references
- Agreement and contract management
- Onboarding workflow state

## Non-Responsibilities

- Recruitment and candidate sourcing
- Agent registry and lifecycle
- Workflow engine internals

## Related Repositories

- [iaop-architecture](https://github.com/AGENTAPR/iaop-architecture) - DDD strategic design, bounded context maps, ADRs
- [iaop-api-contracts](https://github.com/AGENTAPR/iaop-api-contracts) - Versioned OpenAPI contracts
- [iaop-event-contracts](https://github.com/AGENTAPR/iaop-event-contracts) - Versioned integration events
- [iaop-workflow-service](https://github.com/AGENTAPR/iaop-workflow-service) - Flowable BPM orchestration
- [iaop-local-dev](https://github.com/AGENTAPR/iaop-local-dev) - Local development environment

## Status

**INITIALIZED - NOT IMPLEMENTED**

This repository has been bootstrapped with baseline documentation and configuration only.
No business logic or service implementation exists yet.

## Development Conventions

- Default branch: `main`
- Development branch: `development` — all changes are committed and pushed here
- Squash merges preferred; merge commits and rebases disabled
- Pull requests required before merging into `main`
- Topics: iaop, insurance, insurance-agents, enterprise-architecture, rust, axum, microservices, domain-driven-design, postgresql, kyc
## Foundation implementation (2026-11)

Rust/Axum microservice scaffold generated from the canonical IAOP
template (see `iaop-rust-common/templates/axum-microservice` and
`iaop-architecture/docs/standards/IAOP_AXUM_SERVICE_TEMPLATE.md`):

- Crates: `domain`, `application`, `infrastructure`, `api` (+ `src/main.rs`)
- Endpoints: `/health/live`, `/health/ready`, `/api/v1/system/info`, `/openapi.json`, `/docs`
- Persistence: PostgreSQL/SQLx boundary + outbox/inbox migrations
- Security: OIDC/JWT boundary via `iaop-security` (Keycloak)
- Observability: structured JSON logs, correlation IDs, OTLP-ready
- CI: `.github/workflows/main-ci.yml` — fmt/clippy/test on `main` pushes only
- Docs: `docs/architecture.md`, `docs/database.md`, `docs/api.md`

Business features are intentionally not implemented yet.
