# 🖥️ Frontend Architecture

> The frontend is responsible for presenting the platform's capabilities through a consistent, responsive and user-centered experience.
>
> Rather than containing business logic, it focuses on interaction, navigation and communication with backend services.

---

# Overview

The RightPlace AI frontend provides the interface between users and the platform.

Its primary responsibility is to guide professionals and organizations through complex workflows while keeping the experience simple and intuitive.

Business rules remain on the backend.

Professional knowledge remains in the database.

The frontend focuses on interaction.

```text
                 User
                  │
                  ▼
         Frontend Application
                  │
        ┌─────────┴─────────┐
        │                   │
        ▼                   ▼
 UI Components      State Management
        │                   │
        └─────────┬─────────┘
                  ▼
          Backend Services
                  │
                  ▼
          Platform Infrastructure
```

---

# Design Principles

The frontend follows a small set of architectural principles.

- Interface before implementation.
- Business rules remain on the server.
- State should be predictable.
- Components should be reusable.
- Navigation should reflect user workflows.
- Every interaction should have a clear purpose.

---

# User Experience

The platform supports two primary user journeys.

| Experience | Purpose |
|------------|---------|
| Candidate Experience | Career development and job applications. |
| Organization Experience | Hiring and talent management. |

Although both experiences share infrastructure, each one provides workflows optimized for its audience.

---

# Application Structure

The application is organized around product features rather than individual pages.

Each feature encapsulates its own interface, state and communication responsibilities.

This approach allows the platform to evolve without tightly coupling unrelated areas.

---

# Routing

Navigation is organized around user intent instead of technical implementation.

Examples include:

- authentication;
- onboarding;
- candidate workspace;
- organization workspace;
- conversations;
- applications;
- generated documents.

Each route represents a product capability rather than a data entity.

---

# State Management

The frontend maintains only the state required to provide a responsive user experience.

Long-term knowledge is never considered a frontend responsibility.

Whenever authoritative information is required, it is retrieved from backend services.

This keeps client-side state lightweight and predictable.

---

# Backend Communication

The frontend communicates with backend services through well-defined interfaces.

Responsibilities include:

- sending user requests;
- displaying structured responses;
- presenting validation feedback;
- updating local state when appropriate.

Business decisions are intentionally delegated to backend services.

---

# AI Integration

North is presented as a natural conversational interface.

From the frontend perspective, AI behaves like another platform capability rather than an external service.

Conversation history, structured responses and generated artifacts are displayed without exposing implementation details.

For more information, see [AI Architecture](./AI.md).

---

# Component Strategy

User interface elements are designed to be reusable across multiple workflows.

Components prioritize:

- consistency;
- accessibility;
- responsiveness;
- composability.

This approach reduces duplication while improving maintainability.

---

# Responsive Design

The interface is designed to work across desktop and mobile environments.

Layouts adapt to available space while preserving navigation consistency and minimizing cognitive load.

---

# Error Handling

Errors are presented as user guidance rather than technical failures.

Whenever possible, the interface provides actionable feedback that allows users to recover without leaving their current workflow.

---

# Security Boundaries

The frontend never becomes the source of truth for sensitive operations.

Authentication, authorization and business validation remain backend responsibilities.

The client only presents information that has already been validated by the platform.

---

# Current Architecture

The current implementation is built using:

- Next.js
- React
- TypeScript
- Tailwind CSS

The application communicates with Firebase services and backend APIs while keeping business logic outside the user interface.

---

# Future Evolution

As the platform grows, new experiences can be introduced without changing the application's architectural principles.

Potential additions include:

- recruiter dashboards;
- analytics;
- interview workflows;
- career recommendations;
- collaborative hiring experiences.

The architecture is designed to support incremental evolution rather than large-scale rewrites.

---

# Core Idea

The frontend is not responsible for deciding.

It is responsible for communicating.

It transforms complex platform capabilities into experiences that feel simple, intuitive and trustworthy.

> Great interfaces do not hide complexity.
>
> They organize it.
