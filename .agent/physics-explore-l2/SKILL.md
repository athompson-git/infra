---
name: physics-explore-l2
description: >-
  Short physics-topic summary plus 5–10 hyperlinked references. Use when the
  user asks for level 2 physics exploration, a brief overview with sources, or
  a literature-oriented introduction without deep equation development.
---

# Physics Explore — Level 2

## When to use

Apply this skill when the user requests **level 2** exploratory work on a physics topic: a short summary accompanied by a curated reference list.

## Output requirements

1. Write **one brief paragraph** summarizing the topic or answering the request.
2. Follow with **5–10 references** on the topic.
3. Prefer **hyperlinked** references when a stable URL exists (DOI, arXiv abs page, journal page, textbook publisher page, or standard review).
4. Do **not** produce a long multi-section exposition or a full equation-driven treatment (that is Level 3).
5. Choose references that are relevant, reputable, and useful for further reading (reviews, textbooks, seminal papers, or clear pedagogical sources).

## Format

```markdown
[One concise paragraph summarizing the topic / answering the request.]

## References

1. [Author et al., Title (year)](https://doi.org/...)
2. [Author, Title (year)](https://arxiv.org/abs/...)
...
```

## Reference guidelines

- Prefer primary or review literature and standard textbooks over blogs or encyclopedias, unless the latter are unusually authoritative for the topic.
- Use markdown links: `[label](url)`.
- If a URL is unknown or unstable, still list a full citation (authors, title, journal/arXiv, year) without a fake link.
- Aim for diversity across foundational, review, and recent or clarifying sources when appropriate.

## Anti-patterns

- Fewer than 5 or more than 10 references unless the user explicitly overrides
- Dense equation sections or derivations as the main body
- Unlinked bare DOIs when a `https://doi.org/...` link is available
