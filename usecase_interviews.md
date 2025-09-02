# Appendix: Semi-Structured Usecase Interviews

## Objective

Elicit routine tasks, pain points, and governance constraints across departments with the explicit goal of mapping them to embodied social-robot use cases. Interview outputs were translated into concrete assistant–user interactions that later seeded design simulations and model fine-tuning.  

## Facilitators and participants

Two facilitators conducted all interviews together using the same semi-structured guide. Participants were cross-department staff in assistant and legally oriented roles (e.g., Legal Counsel; Executive/Private-Banking Assistants).

## Interview guide

The question set was defined **a priori** in an interview catalog and used by both facilitators. It combines open prompts (to discover tasks and pain points) with fixed rating scales (to prioritize tasks) and explicit prompts on data categories and systems (to capture governance and integration constraints). The guide comprises five domains:

1. **Role & activity spectrum** — “What is your role? What are your main activities?”
2. **Task preferences** — “Which activities do you enjoy or avoid, and why?” with a fixed enjoyment code (**A**=like, **B**=neutral, **C**=dislike).
3. **Task burden profiling (per activity)** — four 3-point scales recorded for each activity:
   * **Effort** (1 high–3 low),
   * **Frequency** (1 very often–3 seldom),
   * **Importance** (1 extremely important/time-critical–3 eventually),
   * **Complexity** (1 complex with dependencies–3 simple).
5. **Data protection** — “Which personal/sensitive data do you process for this activity?”
6. **Processing systems** — “Which systems/tools are used for this activity?”

The filled interview records show consistent application of these questions and scales across sessions.  

## Procedure

Sessions proceeded domain-by-domain. For every activity mentioned, facilitators captured in the template: (a) a short description, (b) the four 3-point ratings and the enjoyment code, (c) involved systems, and (d) personal-data categories. The resulting notes document activities such as minutes, room booking, calendar coordination, meeting preparation, and mailing/serial letters alongside their systems and data fields.  

## Analysis and prioritization

After collection, activities were aggregated across interviews. The fixed scales enabled triage (e.g., high effort + high frequency + high importance + notable complexity) to shortlist high-value candidates. Shortlisted activities were then formalized as **Task-to-Interaction Specifications** with stakeholders, preconditions, **stepwise assistant prompts**, exceptions, risks, IT systems, personal-data categories, and an averaged priority. These decisions ensured the interview data directly informed robotic role definition (facilitating shared meetings, guiding room bookings, capturing agendas/minutes with consent).   
