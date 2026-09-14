---
name: physics-explore-l3
description: >-
  Detailed physics exploration focused on the equations that define the topic,
  with accompanying references. Use when the user asks for level 3 physics
  exploration, equation-driven depth, derivations, or a thorough conceptual
  treatment with citations.
---

# Physics Explore — Level 3

## When to use

Apply this skill when the user requests **level 3** exploratory work on a physics topic: a detailed, equation-centered response with references.

## Output requirements

1. Produce a **detailed response** that explores the topic in greater depth than Levels 1–2.
2. Focus primarily on the **equations** needed to explain the concepts associated with the topic (definitions, governing laws, key relations, and important limiting cases).
3. Explain what each major equation means and how the pieces fit together; include brief context or assumptions where they matter.
4. End with a **References** section (typically 5–15 sources). Hyperlink when a stable URL exists.
5. Use LaTeX math (`$...$` / `$$...$$`) for equations.

## Suggested structure

```markdown
# [Topic]

## Overview
[Short framing of the problem and scope.]

## Key equations and concepts
[Develop the main equations with brief prose around them.
 Group by concept if helpful (e.g. kinematics → dynamics → limits).]

## Notes / caveats
[Optional: regimes of validity, common pitfalls, units/conventions.]

## References
1. [Author et al., Title (year)](https://doi.org/...)
...
```

## Equation guidance

- Prioritize equations that are necessary to understand the topic; avoid dumping unrelated formula lists.
- Define symbols on first use.
- Show important intermediate relations when they clarify the logic; skip algebraic busywork that does not teach.
- Call out standard conventions (metric signature, natural units, Fourier conventions, etc.) when relevant.

## Reference guidelines

- Cite sources that support the equations, standard treatments, and useful reviews.
- Prefer markdown hyperlinks: `[label](url)` with DOI/arXiv/journal URLs when available.
- Place references **below** the main technical discussion.

## Anti-patterns

- Paragraph-only answers with no equations (that is Level 1/2)
- Reference lists without a substantive equation-driven body
- Overlong historical digressions that displace the physics
