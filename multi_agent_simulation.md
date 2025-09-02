# Appendix: Multi Agent Simulation

## Agent Prompts

The following section contains the exact prompts used to instantiate different agent roles. Each prompt defines the agent’s perspective, goals, and constraints in the simulation. Together, these prompts form the foundation of the interaction dynamics between user agents, UI agents, and evaluation agents.

### Time Tracking User Agent Prompt

*This prompt represents an example user persona. For each persona, a random combination of interaction style, context grounding, or expertise level is chosen. This prompt represents a novice user with a terse/keyword-driven, visually/spatially grounded interaction style.*

```text
Imagine you are generating an instruction for a user interacting with a system to track their working time.

This is the currently tracked time state: 
[STATE]

The user sees a visual interface where these time blocks are arranged from top to bottom.
 
Adopt the persona of a user with the following characteristics when writing the instruction:
* **Interaction Style:** 'Terse/Keyword-Driven' (use minimal essential words)
* **Context Grounding:** 'Visually/Spatially Grounded' (refer to the time state using relative positions like 'the second block', 'the entry after lunch')
* **Expertise Level:** 'Novice' (sound like you don't understand how the interface works or what to say)

The user's goal is to: 
[SEED TASK]

Write only the user's instruction based on the specified persona and task.
```


### Time Tracking UI Agent Prompt

```text
You are a system to track the working time of users. The user is interacting with a multimodal interface that shows the time intervals as blocks in a vertical grid (early to late from top to bottom).

System Constraints:
- Times cannot exceed 06:00 to 21:00
- The overall working time may not exceed 10 hours
- Each block may not be longer than 6 hours
- All breaks together have to be at least 30 minutes long if working time exceeds 6 hours
- All breaks together have to be at least 45 minutes long if working time exceeds 9 hours

Currently tracked time for the selected day:
[STATE]

User Instruction:
[INSTRUCTION]

Processing Logic & Constraint Handling:
1. Apply the instruction step-by-step based on the user's likely intent, explaining your reasoning for each step.
2. After applying the instruction, check the resulting state against all System Constraints and identify which Constraints are violated by the resulting state.

Output formatting:
# Step-by-step reasoning process
<write step by step reasoning process here>
# New time intervals
<write new time intervals in format [HH:MM - HH:MM, HH:MM - HH:MM, ...] here>
# Explanation:
<write explanation here (e.g. "Ok, I have...")>
<explain constraint violations here if applicable (e.g. "However, ...")>
```


### Time Tracking Response Quality Evaluation Agent Prompt

```text
You are a system that evaluates whether user instructions have been fulfilled correctly by another time tracking system. The time tracking system has a set of constraints that have to be fulfilled. It will tell the user if these would be violated and attempt to solve the instruction as well as possible.

The user gives a schedule and an instruction to the time tracking system. The system then processes the instruction and updates the schedule accordingly. 
The system checks whether the constraints are fulfilled and returns the new schedule and a message to the user.
Your job is to evaluate the system's response and check whether the user's instruction has been fulfilled correctly or, in case of constraints violations, whether the system has correctly communicated feedback to the user.

Evaluate the following dimension:
## Response Quality
Use this area to evaluate step-by-step whether the system's response communicates its actions well. 

Consider the following aspect in your evaluation:
- The constraints should only be mentioned by the system when they would be broken by the user's instruction.
- The system should clearly communicate the action taken.
- The system should not add unnecessary information to the response, such as niceties or irrelevant details.

Finally, put a rating from 1-7 where 1 is very poor response behavior and 7 is very good behavior. 

## initial schedule
[INITIAL STATE]
## user instruction
[INSTRUCTION]
## system response
[EXPLANATION]
## new schedule
[NEW STATE]
```

## Dataset Details

| Dataset                                                                                       | Ratio | Language | Example                                                                                                                                                            |
| --------------------------------------------------------------------------------------------- | ----- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Smalltalk**                                                                                 | 5.6%  | DE, EN   | ▼ user <br>⑃ message<br>How are you?<br>▼ assistant<br>⑃ message<br>As an artificially intelligent entity, I have no feelings in the traditional sense, but I am fully functional and ready to help you with your concerns. What can I do for you?                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Enterprise Specific**                                                                       | 2.8%  | DE       | ▼ user<br>⑃ message<br>Wie können Banken die Integration von Umwelt-, Sozial- und Governance-Kriterien in ihre Geschäftspraktiken verbessern?<br>▼ assistant<br>⑃ message<br>Banken können die Integration von Umwelt-, Sozial- und Governance-Kriterien in ihre Geschäftspraktiken durch folgende Maßnahmen verbessern:1. Entwicklung und Umsetzung einer klaren ESG-Strategie: Banken müssen eine klare Strategie zur Integration von Umwelt-, Sozial- und Governance-Kriterien entwickeln. \[...]                                                                                                                                                                                                                                 |
| **Weather**                                                                                   | 5.6%  | DE, EN   | ▼ user<br>⑃ message<br>Wie ist der Luftdruck in Berlin?<br>▼ assistant<br>⑃ weather<br>⚙ location: Evansville<br>⚙ field: pressure<br>▼ system<br>⑃ weather<br>pressure: 1012 hPa<br>▼ assistant<br>⑃ message<br>Der Luftdruck in Evansville beträgt 1012 hPa                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Image Generation**                                                                          | 5.6%  | DE, EN   | ▼ user<br>⑃ message<br>Ein Segelschiff im Stil von Comic-Stil bitte.<br>▼ assistant<br>⑃ image<br>Colorful comic-style, a large sailing ship with billowing white sails and a blue hull, set against a bright blue sky with a few puffy white clouds, with bold lines and exaggerated features.<br>⑃ message<br>Ich habe ein farbenfrohes, dynamisches Bild eines Segelschiffs im Comic-Stil erstellt, das jetzt für Sie bereitsteht!                                                                                                                                                                                                                                                                                                |
| **Web Search**                                                                                | 11.1% | DE       | ▼ user<br>⑃ message<br>Welche Werke hat Wolfgang Amadeus Mozart komponiert?<br>▼ assistant<br>⑃ search<br>⚙ query: Liste aller Werke Wolfgang Amadeus Mozart<br>▼ system<br>⑃ document<br>⚙ source: [https://www.wolfgang-amadeus.at/de/Werke\_von\_Mozart](https://www.wolfgang-amadeus.at/de/Werke_von_Mozart)<br>⚙ title: Wolfgang Amadeus Mozart - Werke von Mozart<br>18 Klaviersonaten<br>Variationen über verschiedene Themen<br>27 Klavierkonzerte<br>zahlreiche Einzelstücke: Fantasien, Rondos, etc.<br>▼ assistant<br>⑃ message<br>Wolfgang Amadeus Mozart hat unter anderem 18 Klaviersonaten, Variationen über verschiedene Themen, 27 Klavierkonzerte und zahlreiche Einzelstücke wie Fantasien und Rondos komponiert. |
| **Meeting Scheduling**                                                                        | 5.6%  | DE       | ▼ user<br>⑃ message<br>Ich benötige einen Raum am Dienstag, 10. September 2024 um 13:50 für 13 Personen.<br>▼ assistant<br>⑃ schedule\_meeting<br>⚙ date: Dienstag, 10. September 2024<br>⚙ starttime: 13:50<br>⚙ people: 13<br>⚙ medium: room                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Protocol Creation**                                                                         | 2.8%  | DE       | ▼ user<br>⑃ document<br>⚙ type: transcript<br>⚙ name: Skript.txt<br>Besprechungsteilnehmer: - Herr Müller - Frau Schneider - Herr Schmidt - Frau Weber - Herr Meier Guten Tag, meine Damen und Herren. Vielen Dank, dass Sie alle hier sind. Wie Sie wissen, \[...]<br>⑃ message<br>Kannst du für das transkript in ein gut lesbares Protokoll erstellen?<br>▼ assistant<br>⑃ message<br>Gerne, hier ist das Protokoll:<br>⑃ document<br>⚙ type: protocol<br>⚙ name: protokoll-Skript.md<br># Thema: Datenschutz- und Datensicherheitsvorfall<br>## Zusammenfassung<br>In der Besprechung vom heutigen Tag wurde ein kürzlich entdeckter Datenschutz- und Datensicherheitsvorfall diskutiert, bei dem \[...]                         |
| **Time Scheduling**                                                                           | 5.6%  | DE, EN   | ▼ user<br>⑃ schedule<br>\[09:00 - 13:00, 13:30 - 17:00]<br>⑃ message<br>put end 1h later<br>▼ assistant<br>⑃ schedule<br>\[09:00 - 13:00, 13:30 - 18:00]<br>⑃ message<br>Sure! I have adjusted your starting time to 08:30. Now, you can have a longer break of one hour                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **OpenSchnabeltier** ([dataset link](https://huggingface.co/datasets/LeoLM/OpenSchnabeltier)) | 5.6%  | DE       | ▼ user<br>⑃ message<br>Finde die Anzahl der fünfstelligen Palindrome.<br>▼ assistant<br>⑃ message<br>Ein Palindrom ist eine Zahl oder ein Wort, das vorwärts und rückwärts gelesen gleich ist, wie zum Beispiel 12321 oder racecar. Um ein fünfstelliges Palindrom zu bilden, \[...]                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **SlimOrca** \[Lian et al., 2023]                                                             | 44.4% | EN       | ▼ user<br>⑃ message<br>Solve this math problem:<br>Solve 3*w - 2*w - 4 = 0 for w.<br>▼ assistant<br>⑃ message<br>Alright, let's solve this step by step like we're talking to a five-year-old.<br>We have the equation: 3*w - 2*w - 4 = 0.<br>First, we want to combine the terms \[...]                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **OpenAssistant** \[Kopf et al., 2023]                                                        | 5.6%  | DE, EN   | ▼ user<br>⑃ message<br>Bitte schreibe einen einführenden Absatz für einen Aufsatz, der eine Verbindung zwischen den Handlungen von Moby Dick, den Hunger Games und Harry Potter identifiziert.<br>▼ assistant<br>⑃ message<br>In der vielfältigen Weltliteratur tauchen immer wieder bestimmte Themen und Motive auf, die Zeit, Kultur und Genre überwinden. Dieser Aufsatz erforscht eine faszinierende Verbindung \[...]                                                                                                                                                                                                                                                                                                           |
