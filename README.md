# OrgDesk

A task coordination dashboard for student organizations and event teams to manage deliverables across functional departments (Logistics, Fundraising, PR, Design, Participants, Social) for multiple projects.

## Data model

| Field | Type | Notes |
| :--- | :--- | :--- |
| title | text | required, max 100 chars, task description |
| isDone | boolean | toggled from the list, default false |
| department | fixed values | Logistics, Fundraising, PR, Design, Participants, Social |
| project | relation | category / project scope (e.g. JobFair, TechWorkshop, SpringGala) |
| user | relation | owner / assignee of the task (from week 11) |

Sample data used across all stages:
1. Cere oferta de pret pentru pauza de cafea, active, Logistics
2. Trimite macheta grafica pentru bannere la tipar, done, Design
3. Redacteaza e-mailurile de confirmare pentru participanti, active, Participants

## AI usage

| Tool | Used for |
| :--- | :--- |
| Gemini | Formulating project theme mapping, structuring semantic HTML layout, CSS Grid and custom properties setup |

Details per stage: see the `ai-log/` folder.

## How to run

Open `index.html` in any modern web browser. No build step, no server required.

## Status

- [x] Stage 1: static mockup
- [ ] Stage 2: data logic in JavaScript

## Verification Checklist (Stage 1)

| ID | Requirement | Where (permalink) | How to check |
| :--- | :--- | :--- | :--- |
| S1-R1 | README: description, fields, sample data, how to run | README.md | read |
| S1-R2 | AI usage section | README.md | read |
| S1-R3 | AI log for stage 1 | ai-log/etapa-01.md | read |
| S1-R4 | header, form (text + select), 3 cards with own data | [index.html#L14-L67](https://github.com//orgdesk/blob/main/index.html#L14-L67) | open the page |
| S1-R5 | finished card looks different | [style.css#L173-L177](https://github.com//orgdesk/blob/main/style.css#L173-L177) | look at the card (.done) |
| S1-R6 | 2 columns on desktop, 1 under 700px | [style.css#L179-L184](https://github.com//orgdesk/blob/main/style.css#L179-L184) | resize window < 700px |
| S1-R7 | visible focus, readable dark theme | [style.css#L25-L38](https://github.com//orgdesk/blob/main/style.css#L25-L38) | Tab navigation; emulate dark mode |
| S1-R8 | commit "Stage 1" pushed | commit history | check git log |