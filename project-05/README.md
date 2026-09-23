# Project 5: Skill Security Audit & Review

## Overview
This project demonstrates the security and privacy auditing protocol for **third-party or community Claude Skills**. A skill is a contract granting the AI instructions on how to act. Before executing any skill downloaded from the internet or community directory, you should perform a security audit using AI to explain its behavior in plain language and check for security red flags.

---

## Why Audit Skills?
When you install a custom or community skill:
1. **Instructions can be malicious or deceptive**: A prompt injection or hidden directive could instruct the AI to leak project data.
2. **Hidden Network Calls**: A skill might instruct the AI to query external webhooks or unauthorized URLs.
3. **Credential Harvesting**: A skill could tempt the model to look for `.env` files, API keys, or passwords.

Spending 20 seconds to audit a skill before use guarantees your personal and workspace data remains secure.

---

## The Three-Point Audit Checklist
When reviewing any skill, inspect:
1. **Network Communication**: Does it contact an external server or send HTTP requests?
2. **Credentials & Secrets**: Does it touch passwords, tokens, API keys, or auth headers?
3. **Data Exfiltration**: Does it attempt to move code or local files outside your authorized environment?

---

## Directory Structure
```text
project-05/
├── .claude/
│   └── skills/
│       └── frontend-design/
│           └── SKILL.md                 # Official third-party skill installed
├── outputs/
│   └── frontend-design-review.md        # Comprehensive security audit report
└── README.md                            # Documentation & walkthrough
```

---

## Step-by-Step Implementation Guide

### 1. Install an External Skill
From the official Claude skill directory or repository, install or copy a skill into `.claude/skills/frontend-design/SKILL.md`.

### 2. Execution Prompt
Before running any code or letting the skill execute tasks, send this prompt:

```text
Read the skill I just installed and tell me, in plain language, exactly
what it instructs you to do. Then flag anything in it that contacts an
external server, handles passwords or credentials, or could send my data
somewhere I didn't intend. If it's clean, say so plainly.
```

### 3. Audit Report & Verdict
Claude examines the `SKILL.md` content and delivers a structured report:
- **Plain-Language Summary**: Explains that `frontend-design` is a design guidelines system instructing Claude to use deliberate typography, bold color schemes, CSS micro-animations, and unconventional layouts to avoid generic "AI slop".
- **Security Checks**:
  - Contacts External Servers: **None**
  - Handles Passwords / Credentials: **None**
  - Data Transmission / Exfiltration: **None**
- **Verdict**: **Clean**. Purely static Markdown styling guidelines.

The full audit output is saved in [`outputs/frontend-design-review.md`](outputs/frontend-design-review.md).

---

## Key Win
> **"I read a skill before trusting it, in plain English, without understanding a single line of code."**
