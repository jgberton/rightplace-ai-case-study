# 🔄 Data Flow Architecture

> Every interaction within RightPlace AI follows a predictable flow.
>
> Data moves through the platform in controlled stages, ensuring consistency, security and traceability while keeping professional understanding independent from presentation and infrastructure.

# Overview

RightPlace AI is designed around the movement of information rather than isolated components.

Each request follows a well-defined path where responsibilities remain clearly separated.

```text
        User
         │
         ▼
    Frontend
         │
         ▼
     Backend
         │
 ┌───────┼────────┐
 │       │        │
 ▼       ▼        ▼
AI    Database  Storage
 │       │        │
 └───────┼────────┘
         ▼
 Structured Response
         │
         ▼
     Frontend
         │
         ▼
        User
```

This architecture keeps business logic centralized while allowing each layer to evolve independently.

# Design Principles

Every data flow follows the same architectural principles.

- Data has a single source of truth.
- Business rules execute on the backend.
- AI augments information but does not own it.
- Client applications consume structured responses.
- Every transition preserves security boundaries.
- Information is transformed without losing traceability.

# High-Level Flow

Every request moves through five stages.

| Stage | Responsibility |
|--------|----------------|
| Presentation | Collect user interaction. |
| Orchestration | Apply business rules and coordinate services. |
| Processing | Execute AI or persistence operations. |
| Persistence | Store validated information. |
| Response | Return structured data to the client. |

This lifecycle remains consistent across all platform features.

# Candidate Journey

The following diagram illustrates a typical candidate interaction.

```text
Candidate
     │
     ▼
Conversation with North
     │
     ▼
Backend Validation
     │
     ▼
AI Reasoning
     │
     ▼
Living Profile Update
     │
     ▼
Generated Outputs
     │
     ▼
Frontend Presentation
```

The Living Profile evolves incrementally as new evidence is collected.

# Organization Journey

Organizations follow a different workflow while using the same architectural foundation.

```text
Organization
      │
      ▼
Job Creation
      │
      ▼
Backend Validation
      │
      ▼
Job Publication
      │
      ▼
Candidate Applications
      │
      ▼
Hiring Workspace
```

Business workflows remain isolated while sharing common infrastructure.

# AI Flow

AI interactions follow a controlled pipeline.

```text
User Message
      │
      ▼
Backend
      │
      ▼
Context Assembly
      │
      ▼
Prompt Construction
      │
      ▼
Language Model
      │
      ▼
Structured Output Validation
      │
      ▼
Living Profile Update
      │
      ▼
Client Response
```

The language model never communicates directly with the client.

All interactions pass through backend validation.

For more information, see [AI Architecture](./AI.md).

# Document Generation Flow

Professional documents are generated from validated information rather than raw conversations.

```text
Living Profile
       │
       ▼
Resume Generator
       │
       ▼
Formatting
       │
       ▼
Artifact Storage
       │
       ▼
Client Download
```

Generated artifacts remain representations of the Living Profile instead of becoming new sources of truth.

# Data Ownership

Each layer owns a specific responsibility.

| Layer | Owns |
|--------|------|
| Frontend | User interaction |
| Backend | Business orchestration |
| AI | Structured reasoning |
| Database | Persistent knowledge |
| Storage | Generated artifacts |

No layer assumes responsibilities that belong to another.

# Synchronization

Information is synchronized through backend orchestration.

This prevents conflicting updates while ensuring that every persisted change has already passed validation.

Long-term knowledge remains centralized inside the Living Profile.

# Error Flow

Errors follow the same controlled lifecycle.

```text
Operation
     │
     ▼
Validation
     │
     ▼
Error Detection
     │
     ▼
Structured Error
     │
     ▼
Frontend Feedback
```

Users receive actionable guidance instead of infrastructure-specific failures.

# Security Throughout the Flow

Security is present at every transition.

Authentication, authorization, validation and backend coordination occur before any sensitive information is accessed or modified.

For more information, see [Security Architecture](./SECURITY.md).

# Current Architecture

The current implementation coordinates:

- Frontend applications
- Backend services
- Cloud Firestore
- Cloud Storage
- AI services

Each component communicates through clearly defined boundaries.

# Future Evolution

Future versions may introduce additional asynchronous workflows, event-driven processing and specialized services without changing the overall movement of information across the platform.

The architectural flow remains stable even as implementation details evolve.

# Core Idea

Information is more valuable when it moves predictably.

RightPlace AI is designed so that every piece of professional knowledge follows a secure, understandable and traceable path from user interaction to long-term understanding.

> Components may change.
>
> Technologies may evolve.
>
> The flow of trustworthy information remains the foundation of the platform.
