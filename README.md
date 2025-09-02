# Appendix: Reproducibility Details

This appendix provides detailed documentation for the studies, methodologies, and frameworks discussed in the paper "Designing Conversational AI for Social Robots in Corporate Contexts." It is intended to offer additional details for researchers and practitioners interested in reproducing or building upon this work.

## Overview of Action Research Cycles

The year-long collaboration was structured into three iterative action research cycles. This process moved from initial context exploration and requirement gathering (Cycle I), to interaction co-design and model tailoring (Cycle II), and finally to in-situ field deployment and evaluation (Cycle III). The following diagram provides a high-level summary of the goals, methods, and key learnings of each cycle.

<img width="1401" height="713" alt="image" src="https://github.com/user-attachments/assets/b0024643-5d88-4a65-bb0e-293fd823cd58" />

## Detailed Study Documentation

The following sections provide in-depth documentation for each of the core user studies conducted as part of the research.

### Cycle I: Context Exploration & Ecosystem Scoping

Initial semi-structured interviews and stakeholder workshops were conducted to diagnose organizational pain points and define the scope of the assistant ecosystem. This phase focused on identifying use cases and mapping enterprise constraints related to security, governance, and user workflows. 
* **[Usecase Interviews](usecase_interviews.md):**: Detailed interview procedure including questions and facilitation.

### Cycle II: Interaction Co-design & Model Tailoring

This cycle focused on co-designing interaction patterns directly with users and using these insights to fine-tune a custom LLM. It included two key user studies:

  * **[Participatory Design Workshop](participatory_design_workshop.md):** A co-design workshop with internal employees to generate "ideal" conversational dialogues and define core system requirements.
  * **[Comparative Lab User Study](user_study.md):** A controlled, within-subject experiment comparing the usability of the fine-tuned against a prompt-based baseline.
  * **[Multi Agent Simulation](multi_agent_simulation.md):** A list of agent prompts, seed tasks and user behaviors, and overall finetuning dataset composition.
  * **[Technical Evaluation](technical_evaluation.md):** A detailed explanation of the technical evaluation of the distilled LLM.

### Cycle III: Field Deployment & Ecosystem Evaluation

A four-week field study was conducted to observe real-world usage of the assistant's companion app and understand how users' choice of interaction modality (touch, text, voice) is influenced by their task and social context.

  * **[Longitudinal Field Study](dield_study.md):** Detailed procedures, weekly updates, and thematic analysis from the four-week deployment in the HR department.
