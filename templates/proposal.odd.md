---
odd: "1.0"
id: ODD-0000
title: "<short name of the request>"
status: draft           # draft | in-review | approved | applied | checked | rejected
risk: "?"               # low | medium | high  (AI suggests, IT Guardian confirms)
requester: "<your name>"
owner: "<business owner's name>"
it_guardian: "<IT guardian's name>"
created_at: YYYY-MM-DD
---

# <Request title>

> **ODD — One-Doc Driven Development.** One request, one file. No approval, no apply.

---

## 1. Ask ✍️
*Written by: **you**. Use everyday words; no technical knowledge needed.*

**1.1 What do you want?**
<E.g. "A place where the team logs vacations so I can see who is out each week.">

**1.2 Why does it matter? What problem does it solve?**
<E.g. "Today it's a spreadsheet nobody updates, and twice two people were off at the same time.">

**1.3 Who will use it?**
<E.g. "The 8 analysts on the team, and me as their manager.">

**1.4 How will you know it worked?**
<Give 2 or 3 concrete examples. E.g. "If I book Jan 10–20 and Ana is already off then, I see a warning.">

**1.5 What must NOT happen?**
<Data that must not leak, systems that must not be touched, deadline, budget.>

---

## 2. Proposal 🤖
*Written by: **the AI**, from the Ask. Don't edit it by hand; if something is wrong, fix the Ask and request a new version.*

### 2.1 One-line summary
<…>

### 2.2 Scope
- **Does:** <…>
- **Does not:** <…>

### 2.3 Acceptance criteria
- [ ] Given <situation>, when <action>, then <expected result>.
- [ ] <…>

### 2.4 How it will work (plain language)
<What the person sees and does, step by step. Technical details only at the end, in a few lines.>

### 2.5 Risks and safeguards
| Topic | Assessment | Notes |
|---|---|---|
| Personal or sensitive data | <no / yes> | <…> |
| Access and security | <…> | <…> |
| Cost (licenses, cloud, APIs) | <…> | <…> |
| Integration with other systems | <…> | <…> |

**Suggested risk:** <low / medium / high>, because <…>

### 2.6 Execution plan (the script the AI follows on apply)
1. <…>
2. <…>

### 2.7 Open questions
- <Questions the requester, owner or IT Guardian must answer before apply. If none, write "None".>

---

## 3. Approval ✅
*Filled in by: **the business owner and the IT Guardian**. Apply only happens with both approvals and no open questions.*

| Role | Name | Decision (approved / changes / rejected) | Date | Comment |
|---|---|---|---|---|
| Business owner (the "what") | | | | |
| IT Guardian (the "risk") | | | | |

---

## 4. Apply log 🛠️
*Filled in by: **the AI**, when execution ends.*

- **Date:** <…>
- **What was done:** <…>
- **Where it lives:** <repository, branch, link>
- **How to test:** <step by step>
- **Deviations from the plan:** <none, or what changed and why>

---

## 5. Check 🔍
*Filled in by: **the requester**.*

- [ ] I tested every acceptance criterion in section 2.3
- **Result:** <checked / needs changes>
- **Notes:** <…>
