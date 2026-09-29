# OrgDesk - Multi-Project Task & Department Coordinator

OrgDesk is an operational task management platform built for student organizations, NGOs, and event core teams to coordinate deliverables across specialized departments (Logistics, Fundraising, PR, Design, Participants, Social). It streamlines cross-functional workflows across multiple parallel initiatives, tracking task ownership and execution status from planning to completion.

## Key Features (Stage 1 Architecture)

* Semantic HTML5 Structure: Built with accessible landmarks (header, main, section, footer) for screen-reader compatibility and clean DOM hierarchy.
* Responsive Layout: Two-column asymmetric CSS Grid (1fr 2fr) on desktop viewports that dynamically collapses into a single-column layout under 700px.
* Adaptive Dark Theme: Powered entirely by CSS Custom Properties (:root variables) and @media (prefers-color-scheme: dark) with zero rule duplication.
* Keyboard Accessibility: Full :focus-visible ring support for seamless Tab navigation across form inputs and interactive controls.

## Data Model

Each task entity managed by the application implements the five mandatory attributes required across the semester stages:

| Field | Type | Constraints & Notes | Stage Introduced |
| :--- | :--- | :--- | :---: |
| title | text | Required, max 100 characters; describes the operational deliverable | Stage 2 |
| isDone | boolean | Toggled directly from the task list (false = In Progress, true = Completed) | Stage 2 |
| department | fixed values | Logistics, Fundraising, PR, Design, Social, Participants | Stage 2 |
| project | relation | Target initiative / event scope (e.g., JobFair, TechHackathon, SpringGala) | Stage 10 |
| user | relation | Assigned team member / task owner (used for role-based data separation) | Stage 11 |

### Sample Data (Used Across All Stages)

1. Cere oferta de pret pentru pauza de cafea, active, Logistics
2. Trimite macheta grafica pentru bannere la tipar, done, Design
3. Redacteaza e-mailurile de confirmare pentru participanti, active, Participants

## How to Run

1. Clone the repository to your local machine:
   git clone [https://github.com/YOUR_USERNAME/orgdesk.git](https://github.com/YOUR_USERNAME/orgdesk.git)
2. Open index.html directly in any modern web browser (Chrome, Firefox, Edge). No build step or local server is required for Stage 1.

## Project Roadmap & Status

* [Done] Stage 1: Static UI Mockup (Semantic HTML5 & Responsive CSS3)
* [Pending] Stage 2: Core Data Logic & Array Operations (Vanilla JavaScript)
* [Pending] Stage 3: React Application Initialization (Vite)
* [Pending] Stage 4: Data-Driven Component Architecture
* [Pending] Stages 5-13: State Management, REST API, Database Persistence, Authentication & Docker

## AI Usage

| Tool | Used for |
| :--- | :--- |
| Gemini | Domain data model mapping, semantic HTML5 structure validation, CSS Grid layout, and dark mode custom properties architecture |

Details per stage: see the ai-log/ folder.

## Verification Checklist (Stage 1)

| ID | Requirement | Where (Permalink) | How to Check |
| :--- | :--- | :--- | :--- |
| S1-R1 | README: description, fields, sample data, how to run | README.md | read |
| S1-R2 | AI usage section | README.md | read |
| S1-R3 | AI log for stage 1 | ai-log/etapa-01.md | read |
| S1-R4 | header, form (text + select), 3 cards with own data | index.html#L10-L66 | open the page |
| S1-R5 | finished card looks different | style.css#L173-L176 | look at the card (.done) |
| S1-R6 | 2 columns on desktop, 1 under 700px | style.css#L179-L183 | resize < 700px |
| S1-R7 | visible focus, readable dark theme | style.css#L25-L36 | Tab; dark mode |
| S1-R8 | commit "Stage 1" pushed | link to the commit | commit history |