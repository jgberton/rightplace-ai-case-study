# 🤖 AI Architecture

> RightPlace AI is not built around a language model.
>
> It is built around an evidence-based reasoning architecture that uses Large Language Models to understand professionals, build Living Profiles and translate that understanding into meaningful career artifacts.

# Overview

North is the intelligence layer of RightPlace AI.

Rather than acting as a generic chatbot, North is responsible for understanding professionals through structured conversations, continuously enriching their Living Profile and transforming that understanding into outputs such as resumes, cover letters and hiring insights.

The language model is only one component of this architecture.

Most of the intelligence comes from the product's reasoning pipeline, prompt engineering, structured outputs and long-term profile evolution.

## AI Reasoning Flow

| Stage | Purpose | Result |
|---|---|---|
| **Conversation** | North investigates experiences, decisions, motivations and context. | Professional context |
| **Evidence Collection** | Concrete examples, actions and outcomes are extracted from the dialogue. | Verifiable evidence |
| **Signal Identification** | Capabilities, patterns and transferable skills are identified. | Professional signals |
| **Hypothesis Validation** | Assumptions are tested and remain explicit until supported by evidence. | Validated understanding |
| **Living Profile** | New information is merged with the platform's existing understanding. | Evolving professional profile |
| **Translation** | The Living Profile is transformed into context-specific outputs. | Resumes, cover letters and hiring insights |

### Living Profile Outputs

| Output | Purpose | Status |
|---|---|---|
| **ATS Resume** | Translates professional evidence into an application-ready resume. | Current |
| **Cover Letter** | Produces opportunity-specific communication grounded in the profile. | Current |
| **Hiring Insights** | Presents contextual information within controlled application flows. | Evolving |
| **Professional Matching** | Connects people and opportunities using evidence, capabilities and potential. | Planned |

# Design Principles

The AI architecture follows a few fundamental principles.

- Understanding before matching.
- Evidence before assumptions.
- Conversation before evaluation.
- Living Profiles instead of static resumes.
- Structured reasoning over free-form responses.
- AI as an assistant, never as a decision maker.

These principles influence every AI interaction across the platform.

# North

North is the conversational intelligence layer of RightPlace AI.

Its responsibility is not to answer questions.

Its responsibility is to reduce uncertainty about a professional.

Every interaction attempts to improve the platform's understanding by collecting evidence, validating hypotheses and identifying transferable skills.

North continuously expands the Living Profile instead of generating isolated responses.

# Conversation Architecture

Although users experience a single assistant, the platform currently provides multiple conversational contexts, each with its own objective.

## General North

Focuses on understanding the professional.

The resulting information enriches the Living Profile over time.

## Application North

Conducts conversations specific to a job application.

The objective is to understand the candidate within the context of a specific opportunity.

## Job North

Assists companies while creating job opportunities.

Instead of interviewing candidates, it investigates hiring needs, expectations and role requirements.

Each conversation operates independently while following the same architectural principles.

# The Living Profile

The Living Profile is the central knowledge model of RightPlace AI.

Unlike a traditional resume, it is continuously updated through conversations.

New evidence does not replace previous knowledge.

Instead, it expands the platform's understanding of the professional.

The resume becomes one possible translation of the Living Profile rather than its source.

# AI Reasoning Pipeline

Every conversation follows the same high-level process.

```text
Conversation

↓

Evidence Collection

↓

Signal Identification

↓

Hypothesis Validation

↓

Living Profile Update

↓

Artifact Generation (optional)
```

The objective is always to improve understanding before producing outputs.

# Structured Outputs

North does not generate unrestricted text.

Every AI interaction produces structured information that can be interpreted by the platform.

This allows the system to:

- update the Living Profile;
- identify transferable skills;
- extract professional signals;
- maintain long-term consistency;
- generate career artifacts;
- support future matching.

Structured outputs make AI deterministic enough to become part of the application architecture rather than a simple text generator.

# Prompt Architecture

The platform uses specialized prompts instead of one universal prompt.

Each conversational context has its own reasoning model.

Examples include:

- General North
- Job North
- Application North
- Resume Composer
- Cover Letter Composer

Although independent, all prompts follow the same design principles and contribute to the same Living Profile.

# Resume Translation

Resumes are not created directly from conversations.

They are generated from the current understanding stored inside the Living Profile.

This separation allows multiple artifacts to be produced from the same professional understanding.

Current examples include:

- ATS Resume
- Cover Letter

Future artifacts may include hiring reports, career recommendations and professional summaries.

# Cost Control

AI resources are treated as shared infrastructure.

Server-side controls manage usage, quotas and feature availability before requests reach the language model.

This architecture keeps operational costs predictable while protecting the platform from abuse.

# Security

Large Language Models are never accessed directly from the client.

Every AI interaction passes through the backend, where authentication, authorization, validation and cost controls are enforced.

This approach keeps prompts, business logic and API credentials isolated from the frontend.

# Current Architecture

The current implementation uses:

- Firebase Cloud Functions
- Google Gemini
- Firestore
- Cloud Storage

The language model is invoked exclusively from server-side infrastructure.

Client applications never communicate directly with the model.

# Future Evolution

The AI architecture was designed to evolve independently from any specific language model.

As the platform grows, additional models, reasoning strategies and specialized AI services may be incorporated without changing the overall architectural principles.

# Core Idea

The purpose of the AI architecture is not to generate better resumes.

Its purpose is to improve understanding.

Everything else is a consequence.

> Better understanding creates better translations.
>
> Better translations create better opportunities.
