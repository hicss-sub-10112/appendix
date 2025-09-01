# Appendix: Participatory Design Workshop

This appendix details the methodology and findings of the participatory design workshop conducted to explore user needs and define initial requirements for a conversational room booking assistant.

## Objective

The primary objective of the workshop was to move beyond evaluating existing systems and instead co-create "ideal" conversational dialogues with end-users. By focusing on the complex, multifactorial use case of room booking, we aimed to understand users' mental models and expectations for interacting with a conversational assistant. The key goals were to identify preferred interaction styles, define critical system capabilities for handling diverse user inputs, and prioritize necessary parameters for the booking task.

## Participants

A participatory design workshop was conducted with **six internal employees** ($N=6$, $M\_{Age}=30.3$, $SD\_{Age}=8.37$; 3 male, 3 female). Participants were recruited from various non-technical departments, including **Human Resources (HR), Finance, and IT**, to ensure a diverse range of perspectives on administrative tasks.

## Methodology and Tools

The workshop was structured as a hands-on co-design session where participants actively built and refined dialogues with a prototype.

  * **Core Activity:** Participants designed ideal conversations with a digital assistant using a **low-fidelity chat interface**. This interface was powered by a large language model to support basic conversational interactions.
  * **Co-creative Interface:** The prototype was designed for co-creation. It prompted users for meeting parameters, visualized which information was provided and which was still missing, and most importantly, allowed participants to directly edit the assistant’s responses. This feature empowered users to shape the dialogue and refine the assistant's behavior according to their preferences.
  * **Facilitator and Developer Support:** A **facilitator** guided the participants through the co-design activities, while a **developer** provided on-site technical support to ensure the prototype ran smoothly.

## Workshop Output and Analysis

The workshop was highly generative, resulting in **60 distinct conversations**. These dialogues were then analyzed to identify key themes, expected system features, and user interaction patterns.

<img width="763" height="460" alt="image" src="https://github.com/user-attachments/assets/5adea1bf-09ff-4e4a-aada-8b046e3251a5" />

### Key Findings

The analysis of the co-authored conversations revealed several critical insights that guided the subsequent design and development process.

**1. Diverse and Personal Interaction Styles:** There was no single "correct" way to interact with the assistant. Participants' preferences varied significantly, generally falling into a spectrum from highly guided to highly user-driven.

*Figure 1: Sample conversations from the workshop created in the conversation editor. The editor allowed participants to design diverse interaction styles, from a step-by-step, assistant-led dialogue (Conversation 1) to a user-led interaction where almost all parameters are provided in a single message (Conversation 4).*

  * **Assistant-Driven (Reactive):** Some participants preferred a step-by-step, question-answering flow where the assistant guided them by asking for one piece of information at a time (Figure 1, Conversation 1).
  * **User-Driven (Proactive):** Other participants preferred to lead the conversation, providing multiple or all necessary parameters in a single, dense message for maximum efficiency (Figure 1, Conversations 2 & 4).

**2. Need for Robustness and Flexibility:** The dialogues highlighted the necessity for the system to robustly handle the nuances of natural language. It must be able to process diverse inputs, including informal grammar, misspellings, and incomplete sentences, and successfully resolve ambiguity to maintain context.

**3. Prioritization of Booking Parameters:** The analysis helped identify the most critical parameters for the room booking task.

  * **Primary Parameters:** Time, duration, number of participants, and the nature of the meeting (e.g., internal, external, or executive), which often dictates room priority.
  * **Secondary Parameters:** Less frequently used parameters included specific technical equipment (e.g., flip charts, catering) or requests for setup and cleanup time, which were often handled by a separate company service.
