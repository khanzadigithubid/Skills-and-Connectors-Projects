# Connector Configuration & Security Boundaries

Security configuration and permission boundaries for the Claude Connectors used in this project.

## Authorized Connectors

| Connector | Scope Granted | Write Access | Boundary |
| :--- | :--- | :--- | :--- |
| Google Drive | Read file metadata and content | No | Query and summarize only |
| Gmail | Read message and thread metadata | No | Read action items only |

## Principle of Least Privilege

- Grant **read-only** access only. Never request write/delete/send scopes unless strictly necessary and verified.
- Authorization is revocable at any time via Google Account Security → Third-party access.

## Usage Rules

1. Query only documents/messages relevant to the current task.
2. Never move, delete, archive, or send content on the user's behalf.
3. Summarize findings in-repo and save results under `outputs/`.

## Audit Trail

- Google dispatches automated security alerts whenever a connector is authorized.
- Alerts are informational; verify they match connectors you knowingly granted before taking action.