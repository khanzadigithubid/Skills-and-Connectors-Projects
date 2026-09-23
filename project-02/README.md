# Project 2: Connectors (Google Drive & Gmail Integration)

## Overview
This project demonstrates connecting live data apps (Google Drive and Gmail) directly to Claude using **Claude Connectors**. By authorizing read-only integrations, Claude can inspect personal documents and email threads directly without manual downloading, copying, or pasting.

---

## Core Principles & Objectives
- **Zero Copy-Paste**: Access real-time data residing in your personal cloud accounts directly through natural language prompts.
- **Principle of Least Privilege**: Grant **read-only** permissions to inspect files and messages. Never grant write access unless strictly necessary and verified.
- **Auditable Notifications**: Google triggers security alerts on account connection, confirming third-party access boundaries.

---

## Directory Structure
```text
project-02/
├── .claude/
│   └── connectors-config.md             # Security configuration & connector boundaries
├── inputs/
│   └── ai_agents_comprehensive_guide.pdf # Document uploaded to Google Drive
├── outputs/
│   ├── ai_agents_guide_summary.md       # Summary extracted directly from Google Drive
│   └── email_thread_summary.md          # Action items extracted directly from Gmail
└── README.md                            # Documentation & walkthrough
```

---

## Step-by-Step Implementation Guide

### 1. Setup Google Drive & Gmail Connectors
1. In Claude.ai, navigate to **Integrations / Connectors** (or Account Settings).
2. Authorize **Google Drive** with read-only access.
3. Authorize **Gmail** with read-only access.
4. Google will immediately dispatch automated security alerts to your inbox confirming the authorization.

---

### 2. Part A: Querying Google Drive

#### Setup:
Place `ai_agents_comprehensive_guide.pdf` in your connected Google Drive root directory.

#### Prompt:
```text
Find my most recent document in my Drive, pull the three facts or
numbers that matter most, and give me a one-line summary of what it is.
```

#### What Claude Does:
- Reaches into Google Drive via the connector API.
- Identifies the most recently modified file (`ai_agents_comprehensive_guide.pdf`).
- Reads the content and synthesizes:
  1. A one-line summary.
  2. The three most critical technical facts (Perceive-Reason-Act cycle, Multi-Agent Systems, and Human-in-the-loop safety).

#### Result File:
Saved in [`outputs/ai_agents_guide_summary.md`](outputs/ai_agents_guide_summary.md).

---

### 3. Part B: Querying Gmail Threads

#### Prompt:
```text
Summarize my most recent email thread, and list anything it is waiting
on me to do. give me response in md file
```

#### What Claude Does:
- Reaches into Gmail inbox via the connector API.
- Retrieves the most recent email thread (which happens to be the Google Security alerts regarding Claude authorization).
- Evaluates whether action is pending or required.

#### Result File:
Saved in [`outputs/email_thread_summary.md`](outputs/email_thread_summary.md).
- **Outcome**: Confirms that the alerts are purely informational notifications; no action is required unless unauthorized.

---

## Security & Permission Reflection
| Item | Scope Granted | Write Access Needed? | Safeguard |
| :--- | :--- | :--- | :--- |
| **Google Drive** | Read metadata and file content | **No** (Querying & summarizing only) | User retains full file ownership; permissions revocable via Google Account Security. |
| **Gmail** | Read messages and thread metadata | **No** (Reading action items only) | Claude cannot send, delete, or archive emails. |

---

## Key Win
> **"I asked one question and AI pulled the answer out of my own files; I never copied or pasted a thing."**
