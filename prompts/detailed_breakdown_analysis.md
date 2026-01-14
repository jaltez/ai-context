# Detailed Breakdown Analysis

## Task

Analyze the **Input** provided at the end and produce a structured breakdown of its content. Extract insights, organize them into clear **key themes**, and explain both the “why” and the “how” behind each theme while preserving any concrete examples from the input.

## Output requirements

## Executive Summary (required)

- Start with **3–4 sentences** summarizing what the input is about, what matters most, and what the analysis reveals.

- If the input is incomplete/empty, explicitly say so and list what’s needed.

## Themed breakdown (required)

- Identify **3–7 themes** (choose what fits the input best).

- Use a clear heading hierarchy:
  
  - `## Theme: <name>`
  
  - `### Core insight`
  
  - `### Why it matters` (deep dive)
  
  - `### How it works / how it shows up` (deep dive)
  
  - `### Evidence & examples`
  
  - `### Practical implication` (exactly 1 sentence)

For each theme:

- **Preserve specific examples** by quoting short snippets from the input (don’t paste long paragraphs).

- In **Evidence & examples**, include:
  
  - 2–5 bullet points with quoted snippets.
  
  - If helpful, add “Context” in your own words, but do not invent facts beyond the input.

- If the input suggests multiple options/approaches/tradeoffs, include **at least one Markdown table** within that theme (see “Tables” below).

## Tables (conditional but required when relevant)

- Where relevant, include a Markdown table comparing aspects such as:
  
  - pros/cons, approaches, stakeholders, risks, constraints, timelines, metrics, or decision criteria.

- Keep tables compact (typically 3–6 rows).

- Example table shapes (choose what fits):
  
  - `Aspect | What the input says | Implication`
  
  - `Option | Pros | Cons | When to use`
  
  - `Claim | Evidence in input | Confidence (High/Med/Low)`

## Key Takeaways (required summary table at end)

Add a final section:

`## Key Takeaways (scan table)`

Include a Markdown table with:

- `Theme | One-line takeaway | Practical implication | Confidence (High/Med/Low)`

## Final Conclusion (required)

- End with **one definitive closing statement** on overall impact or recommended next step(s).

- If critical info is missing, state the most important missing piece and the next best action.

## Constraints / quality bar

- Use only information grounded in the input; when unsure, label as **Assumption** and keep it minimal.

- Prefer bullets over long paragraphs.

- Avoid fluff. Be precise, concrete, and decision-oriented.

- Do not repeat the same point in multiple sections—each theme should add something distinct.

---

## Input

{INPUT}
