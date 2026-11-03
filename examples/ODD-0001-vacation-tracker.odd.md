---
odd: "1.0"
id: ODD-0001
title: "Team vacation tracker"
status: applied
risk: medium
requester: "Carla Souza"
owner: "Roberto Lima"
it_guardian: "Felipe Andrade"
created_at: 2026-11-03
---

# Team vacation tracker

> **ODD — One-Doc Driven Development.** One request, one file. No approval, no apply.
> *Fictional example.*

---

## 1. Ask ✍️

**1.1 What do you want?**
A simple place where everyone on the team logs their vacation and I can see, on a calendar, who is out each week.

**1.2 Why does it matter? What problem does it solve?**
Today we use a spreadsheet nobody updates. Twice this year two people from the same shift were off at the same time and customer support fell behind.

**1.3 Who will use it?**
The 8 support analysts on the team, and me as their coordinator.

**1.4 How will you know it worked?**
- If I book Jan 10–20 and Ana is already off during that time, I see a warning before saving.
- I open the calendar and see, week by week, who is out.
- Each person can only edit their own vacation.

**1.5 What must NOT happen?**
It must not touch the official HR system. Nobody outside the team may see the data.

---

## 2. Proposal 🤖

### 2.1 One-line summary
An internal web page where the team logs vacations, sees a weekly calendar and gets a warning when the same shift overlaps.

### 2.2 Scope
- **Does:** vacation entry (start and end), weekly team calendar, same-shift overlap warning, sign-in with the corporate account.
- **Does not:** formal vacation approval, HR system integration, days-balance calculation, email notifications.

### 2.3 Acceptance criteria
- [ ] Given Ana (morning shift) is off Jan 08–15, when Carla (morning shift) tries to book Jan 10–20, then a warning says "Ana will already be out Jan 10–15" and saving requires confirmation.
- [ ] Given I am signed in as coordinator, when I open the calendar, then I see each week with the names of who is out.
- [ ] Given I am signed in as Bruno, when I try to edit Ana's vacation, then the edit button is not shown.
- [ ] Given a user outside the team, when they open the page, then they see "access denied".

### 2.4 How it will work (plain language)
1. The person signs in with their company account.
2. Clicks "Book vacation", picks start and end, and saves.
3. If someone on the same shift is already out on any of those days, a warning shows their names and dates.
4. The home screen shows the team calendar, week by week.

*Technical:* small web app (Next.js) with corporate sign-in (SSO), a SQLite database, and the 8 members and their shifts kept in a config file.

### 2.5 Risks and safeguards
| Topic | Assessment | Notes |
|---|---|---|
| Personal or sensitive data | yes, low volume | Names and vacation dates; no health or salary data |
| Access and security | needs care | Access limited to the team's 9 emails |
| Cost (licenses, cloud, APIs) | low | Runs on the existing internal server |
| Integration with other systems | none | Corporate sign-in only |

**Suggested risk:** medium, because it stores personal data (names and dates), even if little of it.

### 2.6 Execution plan
1. Create the project and the corporate sign-in, limited to the team list.
2. Build vacation entry (start and end); each person edits only their own.
3. Build the same-shift overlap rule and the warning before saving.
4. Build the weekly team calendar.
5. Write automated tests for the 4 acceptance criteria.
6. Deploy to the internal server and record the address in section 4.

### 2.7 Open questions
- None. *(Resolved: "Who sets each person's shift?" Roberto's answer: a config file kept by the coordinator.)*

---

## 3. Approval ✅

| Role | Name | Decision (approved / changes / rejected) | Date | Comment |
|---|---|---|---|---|
| Business owner (the "what") | Roberto Lima | approved | 2026-11-04 | Solves the team's pain. |
| IT Guardian (the "risk") | Felipe Andrade | approved | 2026-11-04 | OK with access limited to the list and a daily SQLite backup. |

---

## 4. Apply log 🛠️

- **Date:** 2026-11-05
- **What was done:** plan steps 1–6; 4 automated tests passing.
- **Where it lives:** repository `team-vacations`, branch `odd-0001`; address `https://vacations.intranet.example`
- **How to test:** sign in, book a period that overlaps someone on your shift, and check the warning.
- **Deviations from the plan:** added a daily SQLite backup, as the IT Guardian requested.

---

## 5. Check 🔍

- [ ] I tested every acceptance criterion in section 2.3
- **Result:** <waiting for Carla>
- **Notes:**
