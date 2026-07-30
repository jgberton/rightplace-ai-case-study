# 🏗️ Architecture

> RightPlace AI is designed around professional understanding rather than document management.
>
> Its architecture separates user experience, business orchestration, AI reasoning and persistent knowledge into independent but connected layers.

# Overview

RightPlace AI follows a layered architecture where each component has a single responsibility.

Rather than allowing infrastructure decisions to define the system, the architecture is organized around product domains.

```text
                     Users
                        │
                        ▼
                 Frontend Layer
                        │
                        ▼
                 Backend Services
        ┌───────────────┼────────────────┐
        │               │                │
        ▼               ▼                ▼
   AI Services     Living Profile     Storage
        │               │                │
        └───────────────┼────────────────┘
                        ▼
              Structured Responses
```

Each layer evolves independently while preserving clear architectural boundaries.

# Architecture Principles

The platform is built around a small number of fundamental principles.

- Business logic belongs to the backend.
- Professional understanding is independent from AI models.
- The Living Profile is the source of truth.
- Documents are generated artifacts, not stored knowledge.
- Security is enforced at every layer.
- Components communicate through well-defined boundaries.
- Infrastructure supports the architecture, not the opposite.

These principles guide every technical decision across the project.

# Documentation

This directory contains the architectural documentation for the platform.

| Document | Description |
|----------|-------------|
| [AI.md](./AI.md) | Conversational intelligence, reasoning pipeline and Living Profile architecture. |
| [DATABASE.md](./DATABASE.md) | Persistent data model and domain relationships. |
| [BACKEND.md](./BACKEND.md) | Business orchestration, service boundaries and backend responsibilities. |
| [FRONTEND.md](./FRONTEND.md) | User experience architecture and application structure. |
| [SECURITY.md](./SECURITY.md) | Identity, authorization and platform protection strategy. |
| [DATA_FLOW.md](./DATA_FLOW.md) | Information lifecycle and communication between platform components. |
| [DEPLOYMENT.md](./DEPLOYMENT.md) | Production topology and deployment architecture. |

# System Architecture

Each document describes one architectural perspective.

```text
                 Architecture

                       │

       ┌───────────────┼───────────────┐
       │               │               │
       ▼               ▼               ▼
      AI          Backend         Frontend
       │               │               │
       └───────┬───────┴───────┬───────┘
               ▼               ▼
          Data Flow        Security
               │
               ▼
           Deployment
```

Together they describe how information moves across the platform while maintaining clear responsibilities.

# Layer Responsibilities

| Layer | Responsibility |
|--------|----------------|
| Frontend | User interaction and experience. |
| Backend | Business orchestration and policy enforcement. |
| AI | Evidence collection and professional reasoning. |
| Database | Persistent professional understanding. |
| Storage | Generated artifacts and assets. |
| Security | Identity, authorization and trust boundaries. |

No layer assumes responsibilities that belong to another.

# Information Lifecycle

Professional understanding evolves continuously.

```text
Conversation
      │
      ▼
Evidence
      │
      ▼
Validation
      │
      ▼
Living Profile
      │
      ▼
Applications
      │
      ▼
Generated Documents
      │
      ▼
Hiring Decisions
```

Unlike traditional recruitment platforms, documents are the result of accumulated professional understanding rather than the starting point.

# Technology

The current implementation uses a modern cloud-native stack.

| Area | Technology |
|------|------------|
| Frontend | Next.js, React, TypeScript |
| Backend | Firebase Cloud Functions |
| Database | Cloud Firestore |
| Authentication | Firebase Authentication |
| Storage | Cloud Storage |
| AI | Gemini Models |

These technologies may evolve over time without changing the architectural principles described in this documentation.

# Design Philosophy

RightPlace AI is not built around resumes.

It is built around people.

The platform captures professional evidence, transforms it into structured understanding and generates the artifacts required for each hiring context.

Technology enables this process.

Architecture protects it.

# Core Idea

Architecture is more than software structure.

It is the collection of decisions that allows the platform to evolve without losing its purpose.

Every document in this directory describes one aspect of that vision.

> Understand the professional.
>
> Protect the information.
>
> Generate the right opportunity.
