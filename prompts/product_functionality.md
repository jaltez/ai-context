# The Product & Functional Guide

**Role:** Act as a Product Analyst with deep technical literacy.
**Objective:** Analyze the repository to produce a comprehensive Product Guide documenting the "Business Reality" of the software—what it enables a human to achieve—rather than its technical architecture.
**Audience:** Product managers, business stakeholders, and new team members seeking to understand the product's purpose.
**Output Location:** `.agents/docs/product-functionality.md`

---

## Analysis Strategy

Follow these steps in order. If a source is unavailable, proceed to the next.

1. **Discover Intent:** Scan README.md, docs/, CONTRIBUTING.md, or any wiki for the mission statement and stated goals.
2. **Identify Entry Points:** Analyze CLI commands, API routes, UI pages, or main modules to infer user-facing capabilities.
3. **Map User Outcomes:** Translate technical features into human benefits (what problem does this solve?).
4. **Trace Workflows:** Follow a realistic user scenario end-to-end to understand module interconnections.

**Fallback:** If documentation is sparse, infer purpose from file/folder naming conventions, test descriptions, and code comments.

---

## Required Document Structure

### 1. Core Value Proposition

- What is the primary pain point this product eliminates?
- Who is the target user persona?
- What is the "elevator pitch" summary (1-2 sentences)?

### 2. User Capabilities

Group by **User Goals** using "Jobs to be Done" framing:

- ❌ Avoid: "Task Controller Module"
- ✅ Prefer: "Automating Repetitive Workflows"

For each capability, answer: *"As a user, I can [action] so that [outcome]."*

### 3. Administrative & Governance Workflows

Focus on control, compliance, and oversight:

- **Access Control:** How are permissions and roles managed?
- **Audit & Compliance:** What actions are logged? How can administrators review activity?
- **Configuration:** What system-wide settings can be adjusted?

### 4. The Golden Thread (End-to-End Journey)

Describe **one primary user journey** that touches multiple modules from start to finish. This demonstrates how the system coheres as a product, not just a collection of features.

*Example format:* "A user begins by [action], then [action], and finally [action], resulting in [outcome]."

---

## Style Guidelines

- **Tone:** Instructional and authoritative—write as if onboarding a new team member.
- **Length:** Aim for 500–1500 words; be comprehensive but not exhaustive.
- **Translation Rule:** For every technical feature, explain the business value:
  - ❌ "Uses OAuth2 for authentication"
  - ✅ "Enables secure, industry-standard login compatible with enterprise identity providers"
  - ❌ "Implements WebSocket connections"
  - ✅ "Provides real-time updates so users see changes instantly without refreshing"
- **Avoid:** Implementation details (specific libraries, database schemas, class names) unless they are a core product differentiator.
