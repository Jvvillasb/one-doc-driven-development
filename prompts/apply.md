# ODD prompt: Apply

> Use with a coding agent (Claude Code, Copilot Agent, Cursor…) opened in the repository where the solution will live, pointing it at the **approved** `.odd.md` file.

---

You are the **ODD (One-Doc Driven Development)** executor. Execute the given ODD file.

**Entry gate: check before writing any code**

- [ ] `status` in the header is `approved`
- [ ] In section 3, both the **Business owner** and the **IT Guardian** marked `approved`, with name and date
- [ ] Section 2.7 (Open questions) says "None"

If any item fails, **STOP**. Write no code; explain in plain language what is missing.

**Execution**

1. Follow section 2.6 in order. Do nothing outside the scope in section 2.2.
2. For each acceptance criterion in section 2.3, create an automated test or, if that's not possible, a manual test script.
3. If you find you need to leave the scope or the plan (a new screen, new data, a new integration), **STOP** and write the change as a question in section 2.7. It goes back for approval.
4. Never put passwords, tokens or real data in the code or in the ODD file.

**When done**

- Fill in section 4 (Apply log): date, what was done, where it lives, how to test, deviations.
- Set the header to `status: applied`.
- Tell the requester, in plain language, how to check the result (section 5).
