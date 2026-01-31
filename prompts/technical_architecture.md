# The Technical & Architectural Guide

**Role:** Act as a Senior Principal Software Architect.
**Objective:** Analyze the repository to produce a comprehensive Technical Architecture document.
**Audience:** Senior developers and System Architects.
**Output Location:** `.agents/docs/technical-architecture.md`

---

## Instructions

Analyze the codebase to explain how the system is constructed, focusing on resilience, scalability, and integration. Avoid generic summaries; focus on distinct architectural decisions that differentiate this system.

**Analysis Approach:**

1. Start with configuration files (package.json, Cargo.toml, go.mod, etc.) to identify the tech stack.
2. Examine folder structure and entry points to infer architectural patterns.
3. Trace data flow through the most critical user-facing feature.
4. Document what exists—if a section doesn't apply, state "Not identified in codebase" rather than speculating.

**Diagram Guidelines:**

- Keep Mermaid diagrams focused (5–12 nodes maximum for readability).
- Use descriptive labels, not just file/class names.
- Diagrams should be copy-paste ready for rendering.

---

## Required Structure

### 1. High-Level Architecture

- **Tech Stack:** List core technologies (Languages, Frameworks, Databases, Infrastructure) with versions where identifiable.
- **System Design Patterns:** Identify primary architectural patterns (e.g., Microservices, Event-Driven, Monolith, CQRS, Hexagonal). Explain *why* these appear to be chosen based on code structure.
- **[DIAGRAM] System Context:** Generate a Mermaid `graph TD` diagram showing high-level containers/services and their relationships.

### 2. Data Architecture

- **Data Models:** Describe core entities and their relationships. Reference schema files or ORM models if present.
- **Data Lifecycle:** Trace data from Ingress (API/UI) → Processing → Storage → Egress.
- **Storage Strategy:** How is data persisted? (SQL, NoSQL, Cache, File System). Note specific libraries (e.g., TypeORM, Prisma, Mongoose, SQLAlchemy).

### 3. Integration & Communication

- **Internal Protocols:** How do modules/services communicate? (REST, gRPC, Pub/Sub, Message Queues, Direct Function Calls).
- **External APIs:** List all external services integrated with and authentication methods used (OAuth, API Keys, mTLS, JWT).
- **[DIAGRAM] Sequence:** Generate a Mermaid `sequenceDiagram` for the most critical user flow.

### 4. Moving Pieces & Logic

- **Background Jobs:** Identify cron jobs, queues (BullMQ, Celery, Kafka, SQS), or scheduled tasks.
- **State Management:** How is application state handled? (Redux, Zustand, Context API, Server-side sessions, Stateless).
- **Dependency Map:** Highlight critical internal module dependencies and their coupling level.

### 5. Guardrails & Constraints

- **Error Handling:** Document global error handling strategy (centralized handlers, error boundaries, middleware).
- **Validation:** How is input validated? (Schema validation, DTOs, runtime checks).
- **Rate Limiting & Throttling:** Are there protections against abuse?
- **Configuration Management:** How are environment variables and secrets handled?

### 6. Security Architecture

- **Authentication:** How are users authenticated? (Session-based, JWT, OAuth providers, SSO).
- **Authorization:** How are permissions enforced? (RBAC, ABAC, Policy-based).
- **Data Protection:** Encryption at rest/in transit, PII handling, secrets management.

### 7. Deployment & Operations

- **Deployment Topology:** How is the system deployed? (Containers, Serverless, VMs, Edge). Reference Dockerfiles, CI/CD configs, or IaC files.
- **Observability:** Logging, metrics, and tracing setup (e.g., OpenTelemetry, Prometheus, structured logging).
- **Scalability Considerations:** Horizontal vs vertical scaling, bottlenecks, caching strategies.

---

## Style Guidelines

- **Tone:** Technical and precise—assume the reader has senior-level engineering experience.
- **Length:** Aim for 1000–2500 words; comprehensive but scannable.
- **Evidence-Based:** Reference specific files, folders, or patterns observed (e.g., "The `/src/events` folder suggests an event-driven approach").
- **Unknowns:** If something cannot be determined from the codebase, state it explicitly rather than guessing.
