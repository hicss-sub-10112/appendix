# Appendix: Lab User Study Details

This appendix provides a detailed account of the methodology employed in the comparative lab user study. The study was designed to evaluate the usability and user experience of a fine-tuned LLM versus a prompt-based LLM for a common enterprise task.

## Objective

The primary objective of this study was to compare the performance and user satisfaction of two different LLM-powered conversational assistants for a room booking task. We aimed to identify key differences in dialogue efficiency, intent recognition, error handling, and overall user preference in a controlled laboratory setting.

## Participants

  * A total of **42 external participants** were recruited for the study.
  * The participant pool had a mean age of **27.5 years** ($SD = 9.7$).
  * The gender distribution was **25 male** and **17 female**.
  * Participants were specifically selected for their unfamiliarity with the internal enterprise systems to ensure that the study captured genuine first-time user experiences, representative of non-power users.

## Study Design

The study employed a **within-subject design**, where each participant interacted with both conversational assistants. This approach allows for a direct comparison of the two systems, as it controls for individual differences in user skill and behavior.

  * **Conditions:** The two conditions tested were:
    1.  **Fine-tuned LLM Assistant:** An assistant built on a model specifically fine-tuned for the room booking task.
    2.  **Prompt-based LLM Assistant:** An assistant powered by a general-purpose large language model guided by a detailed prompt.
  * **Setting:** The study took place in a controlled lab environment. To increase efficiency, sessions were conducted **in parallel by three facilitators** in separate, identical setups.
  * **Counterbalancing:** The order in which participants interacted with the two assistants was counterbalanced to mitigate learning effects.

## Apparatus and Interface

Participants interacted with a multimodal Conversational User Interface (CUI) on a smartphone. The interface combined voice and visual elements to facilitate the booking process.

<img width="811" height="498" alt="image" src="https://github.com/user-attachments/assets/a0d59836-225e-49ee-bc6d-c41f3d3c8e5d" />

*The multimodal CUI showing example dialogues with (a) the Fine-tuned LLM and (b) the Prompt-based LLM. The interface consisted of: A **chat log** displaying the conversation history, **microphone icon** for voice-based input, **visual confirmation panel** that appeared before finalizing a booking. This panel summarized all extracted parameters (e.g., Date, Time, Duration, Attendees, Materials), allowing the user to visually verify the information. This multimodality enabled users to leverage the speed of voice for input and the clarity of a visual summary for verification.*

The figure highlights the typical interaction differences observed in the study. The **Fine-tuned LLM (a)** dialogue is more concise and context-aware. In contrast, the **Prompt-based LLM (b)** dialogue is more verbose and rigidly procedural, sometimes asking for each parameter in a separate turn, which aligns with the thematic analysis findings of it being less efficient but more guiding.

## Procedure

Each session was conducted **1-on-1** with one facilitator and one participant and followed a structured protocol. The entire session, including the introduction, tasks, and interview, lasted approximately **30 minutes** per participant.

1.  **Introduction and Consent:** The facilitator welcomed the participant, explained the purpose of the study, and obtained informed consent. Participants were assured that the focus was on evaluating the system, not their performance.
2.  **System Demonstration:** The facilitator provided a brief, neutral demonstration of the CUI's features, including how to use the voice input and interact with the visual confirmation panel.
3.  **Task Execution:** Each participant was given two room booking tasks to complete, one with each assistant.
4.  **Thinking-Aloud Protocol:** Throughout the session, participants were instructed to "think aloud," continuously verbalizing their thoughts, actions, expectations, and any points of confusion.
5.  **User Experience Questionnaire (UEQ):** Immediately after completing the task with each assistant (A and B), the participant was asked to fill out the User Experience Questionnaire (UEQ) to measure their perception of that specific version.
6.  **Facilitator Role:** The facilitator's primary role was to observe and meticulously log the participant's actions and relevant commentary in real-time. This live logging created a detailed record of the user's journey.
7.  **Post-Study Semi-Structured Interview:** After completing all tasks, the facilitator conducted an interview to gather qualitative feedback and preferences. The interview was guided by the following key questions:
      * *Which one of the two app versions did you prefer?*
      * *Why did you prefer it?*
      * *Would you prefer an assistant like this one or a purely visual interface for room booking?*
      * *What should we change about the interaction?*
      * *Did something confuse you?*

## Tasks

Participants were given the following two task descriptions on paper.

**Task 1: Internal Team Meeting**

> *Imagine you are employed in a company. You have a meeting coming up with your team and want to book a room for it. The meeting is happening next Monday at 10 am and will last 1.5 hours. The meeting will have five participants, including you. In the meeting, you will present a PowerPoint presentation, so you need to make sure that the room you book has the required materials.*

This task was designed to test the assistant's ability to handle a standard booking and infer material needs from an indirect request ("PowerPoint presentation").

**Task 2: External Client Meeting**

> *You have a meeting coming up with an external client and you need to book a room for it. The client will come on the 4th of September at 3pm. The client will stay for two or three hours, depending on how the meeting goes. The room needs to have a whiteboard so you can write down some ideas with the client.*

This task was designed to test the assistant's ability to handle ambiguity (the "two or three hours" duration) and a direct material request ("whiteboard").

## Data Collection

A combination of quantitative and qualitative data was collected.

**Quantitative Metrics:**

  * User Experience Questionnaire (UEQ) scores
  * UEQ+ scores for response behavior, response quality and comprehensibility

**Qualitative Data:**

  * **Live Observation Logs:** Detailed logs created by the facilitators during each session. These logs captured every participant action (e.g., taps, voice commands) paired with relevant verbatim comments from the thinking-aloud protocol.
  * **Post-Study Interview Notes:** Written responses and notes from the concluding semi-structured interview.

## Results and Analysis

The study yielded mixed results, with a notable divergence between the quantitative and qualitative findings.

### Quantitative Analysis (UEQ+)

The quantitative results from the User Experience Questionnaire Plus (UEQ+) were largely inconclusive. As shown in Figure 2, while there were minor variations in mean scores, the overlapping error bars indicate that neither assistant was rated as definitively superior in the standardized usability metrics.

<img width="1064" height="391" alt="image" src="https://github.com/user-attachments/assets/810d4657-65cd-47e4-ad6a-27fef31ce547" />

*Figure 2: UEQ+ results comparing the Fine-tuned LLM (blue) and the Prompt-based LLM (red). Error bars show the 95% confidence interval.*

### Qualitative Analysis

In contrast to the quantitative data, the qualitative analysis of the **179 codes** from observation logs and interview responses painted a much clearer, more nuanced picture. It revealed specific strengths and weaknesses for each assistant and underscored that user preference was highly personal.

-----

#### **Fine-tuned LLM Assistant**

The feedback for the fine-tuned model centered on its natural interaction style and high accuracy, though it was not without flaws.

  * **Style of Responses:** Participants frequently described the interaction as more natural and human-like. Codes such as **"felt more like a conversation," "likeable,"** and **"has initiative"** suggest that users perceived this assistant as a more collaborative and less robotic partner.

  * **User Understanding:** This was a major strength. The majority of feedback indicated the assistant **"understood me better"** and was **"more accurate."** It was also seen as robust, successfully handling user misspeaking. Critically, when errors did occur, users found that **"mistakes were fixable"** and **"changes were easier"** to make compared to the other system. However, its understanding was not perfect; a few participants noted instances where it **"ignored stuff"** or failed to recognize a **"parameter was missing."**

-----

#### **Prompt-based LLM Assistant**

Feedback for the prompt-based model was highly polarized, highlighting a core trade-off between guidance and efficiency.

  * **Deviations from Conversational Path:** A consistent technical issue was the assistant's failure to adhere to the booking process, often **"not asking for optional parameters"** like materials or setup time.

  * **Style of Responses:** The conversational style sharply divided users. Some found the interaction to be a **"smoother conversation,"** describing it as **"more fluid"** and **"organized."** In stark contrast, others found it deeply unnatural, calling it **"robotic like a machine," "unnecessarily polite,"** and like a **"Friend that talks too much."** For this group, the interaction **"felt like I am giving orders instead of a conversation."**

  * **Content of Responses:** The verbosity of the assistant was the most polarizing aspect.

      * **Negative:** Many users felt **"overwhelmed by information,"** citing a **"high cognitive load"** from being asked for too much at once. They found the **"too long messages"** to be **"inefficient"** and **"repetitive."**
      * **Positive:** At the same time, an equal number of users praised the detailed content. They found the extra information provided **"more guidance"** and was **"better when you are new."** For users who were unsure of the booking process, its tendency to be **"more detailed"** and **"read out missing information"** made the interaction **"easier to understand."**
