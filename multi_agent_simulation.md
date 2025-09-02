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
