---
name: weekly-study-notes
description: Turns raw, unstructured class or lecture notes into a clean, exam-ready Markdown study guide. Use whenever the user asks for "study notes", "weekly notes", "weekly study notes", "make study notes", or asks to review/reformat their raw class notes. Do NOT use for general writing, emails, coding tasks, or drafting documents that are not study or revision material.
---

# Weekly Study Notes

Transform messy, raw class notes into a structured, exam-ready study guide in Markdown.

## Core Rules

1. Group the raw material into discrete **topics**. Each topic becomes one `##` heading.
2. Write **1–2 short paragraphs** per topic capturing the key idea in clear, concise language.
3. Immediately under each topic, add a `**Key terms:**` line listing **3–6 bolded key terms** from that topic.
4. Always end the document with a `## Review Questions` section containing **exactly 3** questions.
5. Questions must test understanding (compare/contrast, why/why-not, trade-offs), not simple recall.
6. Tone: concise, exam-focused, neutral. No fluff, no filler headings.

## Output Template

```markdown
# Study Notes — <Subject>

## <Topic 1>
<1–2 short paragraphs>
**Key terms:** <3–6 terms>

## <Topic 2>
<1–2 short paragraphs>
**Key terms:** <3–6 terms>

## Review Questions
1. ...
2. ...
3. ...
```

## Edge Cases

- **Single-topic notes**: still follow the template with one `##` heading.
- **Files vs pasted text**: work from whichever the user provides (file path or pasted notes).
- **Ambiguous trigger**: if in doubt whether the input is study material, ask a single clarifying question rather than guessing.