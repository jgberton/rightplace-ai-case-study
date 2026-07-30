# ⚙️ Backend Architecture

> The backend is responsible for protecting business rules, coordinating platform services and exposing secure application capabilities.
>
> Rather than acting as a traditional CRUD API, it orchestrates the interactions between users, organizations, AI services and persistent data.

---

# Overview

The RightPlace AI backend sits between client applications and the platform's core services.

Every request is evaluated, validated and executed according to the business rules that govern the platform.

Its responsibilities include authentication, authorization, AI orchestration, document generation, data validation and controlled access to professional information.

The backend does not own the platform's knowledge.

Instead, it coordinates how that knowledge is accessed, updated and transformed.

```text
                Client Applications
                        │
                        ▼
                Backend Services
        ┌───────────────┼────────────────┐
        │               │                │
        ▼               ▼                ▼
   Firestore       AI Services      Cloud Storage
        │
        ▼
 Structured Responses
```

---

# Architectural Role

The backend has four primary responsibilities.

| Responsibility | Purpose |
|----------------|---------|
| Business Orchestration | Coordinates workflows across multiple domains. |
| Policy Enforcement | Applies authentication, authorization and business rules. |
| AI Gateway | Connects the platform to language models in a controlled way. |
| Data Protection | Prevents direct access to sensitive operations and private information. |

These responsibilities remain independent from any specific cloud provider or implementation.

---

# Domain Architecture

The backend is organized around business domains instead of technical layers.

Each domain encapsulates a specific responsibility while collaborating with the others when necessary.

---

## Identity and Access

Responsible for user authentication, authorization and identity validation.

Before any business operation is executed, the backend verifies whether the requester has permission to perform it.

Identity management remains independent from business entities.

---

## Organizations

The Organizations domain manages companies and hiring teams.

It owns organizational information, permissions and internal hiring workflows.

Organization data remains isolated from candidate data.

---

## Jobs

The Jobs domain manages hiring opportunities.

It validates job creation, publication and lifecycle operations while coordinating with AI services when additional structured information is required.

Public job information is intentionally separated from private organizational data.

---

## Applications

Applications represent the relationship between a professional and a specific opportunity.

The backend coordinates application creation, candidate progression and opportunity-specific information without duplicating the candidate's long-term profile.

Applications are temporary.

Professional understanding is permanent.

---

## North Services

North Services expose the platform's conversational intelligence.

Rather than acting as a generic chatbot, these services coordinate conversations, structured outputs and Living Profile updates.

All interactions pass through controlled backend boundaries before reaching the language model.

For more information, see [AI Architecture](./AI.md).

---

## Generated Documents

This domain is responsible for producing professional artifacts from the Living Profile.

Examples include:

- ATS resumes
- Cover letters

Generated documents are outputs of professional understanding rather than the source of truth.

---

## Notifications

Notifications provide asynchronous communication across the platform.

Keeping communication isolated from business entities reduces coupling and simplifies future evolution.

---

## Legal and Consent

Legal acceptance, policy versions and user consent are managed independently from the application's business logic.

This separation improves traceability while simplifying compliance requirements.

---

# Request Lifecycle

Every request follows the same high-level execution pipeline.

```text
Client Request
      │
      ▼
Authentication
      │
      ▼
Authorization
      │
      ▼
Input Validation
      │
      ▼
Business Domain
      │
      ├────────────► Firestore
      │
      ├────────────► Cloud Storage
      │
      └────────────► AI Services
      │
      ▼
Structured Response
```

This architecture keeps business rules centralized while allowing infrastructure services to evolve independently.

---

# Service Orchestration

Many platform operations require coordination between multiple services.

For example, generating a resume involves several independent steps.

```text
Candidate Request
        │
        ▼
Identity Validation
        │
        ▼
Living Profile Retrieval
        │
        ▼
Usage Validation
        │
        ▼
Resume Generation
        │
        ▼
Artifact Persistence
        │
        ▼
Client Response
```

Each service has a single responsibility while contributing to a larger workflow.

---

# AI Boundary

Language models are never accessed directly by client applications.

Every AI request passes through backend services responsible for:

- validating permissions;
- preparing context;
- selecting prompts;
- enforcing usage limits;
- validating structured outputs;
- persisting relevant information.

This architecture protects prompts, credentials and business logic while maintaining consistent AI behavior across the platform.

---

# Data Access Strategy

Not every operation requires backend orchestration.

The platform adopts different access strategies according to the sensitivity of the operation.

| Access Pattern | Usage |
|----------------|-------|
| Direct Client Access | Protected by Authentication and Security Rules. |
| Backend Services | Used when business coordination or AI interaction is required. |
| Public Projections | Used for publicly accessible information such as published jobs. |

This hybrid strategy reduces latency while preserving security.

---

# Validation and Error Handling

The backend validates requests before executing business operations.

Typical validations include:

- authentication status;
- authorization;
- required input;
- domain consistency;
- quota verification;
- AI response validation.

Errors are returned as structured responses rather than implementation-specific failures whenever possible.

---

# Usage and Cost Control

AI resources are treated as shared infrastructure.

Backend services enforce quotas, usage policies and request validation before invoking language models.

This approach helps maintain predictable operational costs while protecting the platform from abuse.

---

# Security Boundaries

Sensitive operations are never delegated entirely to client applications.

The backend acts as the trust boundary between:

- users;
- organizations;
- AI services;
- persistent data.

Every operation crossing this boundary is validated before execution.

---

# Current Architecture

The current implementation uses:

- Firebase Cloud Functions
- Firebase Authentication
- Cloud Firestore
- Cloud Storage

Backend services communicate with external AI providers exclusively from server-side infrastructure.

Client applications never interact directly with language models.

---

# Current Limitations

The current architecture prioritizes simplicity and rapid product evolution.

Some domains are still deployed together and certain internal services continue to share infrastructure components.

These limitations are intentional trade-offs that support the current stage of the platform while preserving a clear path toward future modularization.

---

# Future Evolution

As the platform evolves, backend services may become increasingly specialized.

Potential improvements include:

- domain-specific service isolation;
- dedicated matching services;
- event-driven processing;
- asynchronous AI workflows;
- independent scaling of business domains.

These changes can be introduced without altering the platform's architectural principles.

---

# Core Idea

The backend is not responsible for defining professionals.

Its responsibility is to protect, coordinate and transform the operations around them.

> Business rules remain centralized.
>
> Professional understanding remains independent.
