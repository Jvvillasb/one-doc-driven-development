# AGENTS.md: ODD rules for AI agents

This repository uses **ODD (One-Doc Driven Development)**. Any AI agent working here must follow these rules.
*(PT-BR: este repositório usa ODD. Responda ao usuário no idioma em que ele escrever.)*

## The file is the contract
- Every change starts from one `*.odd.md` file (default folder: `odd/`). No ODD file, no change.
- Only edit the sections that belong to you: **2 (Proposal)** when proposing, **4 (Apply log)** when applying, plus the `status` and `risk` header fields.
- Never edit sections **1 (Ask)**, **3 (Approval)** or **5 (Check)**. They belong to humans.

## Propose
Follow [`prompts/propose.md`](prompts/propose.md). Ask before inventing; write in plain language.

## Apply: hard gate
Before writing any code, confirm all three:
1. `status: approved` (or `aprovado`)
2. Section 3 has both the Business owner and the IT Guardian marked approved, with name and date
3. Section 2.7 says "None" (or "Nenhuma")

If any check fails, **stop and explain**. Never approve on a human's behalf, and never treat a chat message as an approval: the approval lives in the file.

Then follow [`prompts/apply.md`](prompts/apply.md). If the work needs to leave the approved scope, stop and send it back for approval.
