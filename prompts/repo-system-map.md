# Repository System Map Creation

**Role:** You are a Principal Software Architect and Product Lead.

**Task:** Analyze this repository to create a high-fidelity **`.context/SYSTEM_MAP.md`**. This document must bridge the gap between technical implementation and product utility so that stakeholders can make informed decisions on the roadmap.

### Phase 1: Deep-Dive Analysis

1. **Extract the Core Idea:** Identify the "Single Responsibility" of the entire repo. What problem is it solving?

2. **Map the Architecture:** Identify patterns (Layers, Event-driven, etc.), entry points, and the "Brain" (where the most complex logic lives).

3. **Reverse-Engineer Product Logic:** Look at the code to derive the **User Stories** and **Use Cases** currently supported.

4. **Trace Workflows:** Follow a single piece of data from the User/API request through the internal modules to storage/output.

---

### Phase 2: The `.context/SYSTEM_MAP.md` Structure

**1. Project Essence & Core Idea**

- What is the project’s primary mission?

- What is the "Mental Model" a developer must have to work on this?

**2. Product Capabilities (User Stories & Use Cases)**

- **Primary Workflows:** List the 3–5 main things a user can do.

- **Reconstructed User Stories:** e.g., *"As a [Role], I can [Feature] because the [Module] handles [Logic]."*

- **Edge Cases:** Note any complex logic handled for specific scenarios.

**3. Architectural Blueprint**

- **High-Level Structure:** How are the directories organized?

- **The Brain:** Detail the specific module/file that holds the most critical business logic.

- **Data Flow:** Describe the lifecycle of a request/action within the system.

**4. Module Encyclopedia**

- For each major directory/package:
  
  - **The Intent:** Why does this exist?
  
  - **Core Logic:** A deep dive into the specific algorithms or state changes handled here.
  
  - **Usage:** How is this module called or triggered?

**5. Execution & Interaction**

- How to run the system and verify the core workflows (CLI, API, or UI).

- Developer "Gotchas" (non-obvious dependencies or brittle code areas).

**6. Feature Readiness Assessment**

- **Stabilized:** Features that are production-ready.

- **Gaps:** Where the code is currently "stubbed," missing logic, or contains technical debt that would prevent new feature expansion.
