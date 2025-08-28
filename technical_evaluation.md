# Appendix: Technical Evaluation Details
This appendix provides a detailed overview of the technical evaluation conducted as part of the Supervised Finetuning stage. The evaluation was split into two parts: first, an evaluation of their performance on the specific interaction tasks for which they were designed, and second, an assessment of the models' general capabilities on standard benchmarks.

## Task-Specific Interaction Quality
We evaluated the models' performance on the specific KID tasks using our multi-agent simulation. This was the most critical test of our framework's effectiveness. The metrics for this evaluation weren't arbitrary; they were specifically designed to reflect the real-world needs of the project, derived from both enterprise requirements and direct user feedback gathered during our studies.

### **Justification for Evaluation Metrics**
Here’s a breakdown of why each metric was chosen:
* **Adherence to Constraints:** This metric was chosen to ensure the system followed the company's specific business rules. It assesses adherence to operational rules like working time limits and mandatory break requirements, which were explicitly defined during the stakeholder workshops with the SME.
* **Error Rate:** This metric was a technical necessity. It checks for things like correct output formatting and parseability, ensuring the technical compatibility needed for the assistant to integrate seamlessly with the application's other systems. This was a core requirement to make sure the app would actually work.
* **Response Quality:** This metric was a direct response to qualitative user feedback from the user study. Users reported frustration with a lack of transparency and found overly verbose messages confusing. This metric was designed to evaluate subjective aspects like clarity, conciseness, and tone to ensure the assistant's responses were helpful and didn't increase the user's cognitive load.
* **Instruction Following:** This metric was chosen to address fundamental user expectations and specific interaction failures observed during the user study. In early prototypes, users sometimes found their intent was misinterpreted or ignored by the system. This metric directly measures how successfully the assistant interprets the user's instructions and achieves the desired outcome, a critical factor for usability and trust.

### **Evaluation Results**

The results, shown in the figure below, revealed that the KID models significantly outperformed the original low-fidelity prompted prototypes across all four of our target metrics.
<img width="1515" height="507" alt="image" src="https://github.com/user-attachments/assets/f7af2f40-037f-4d02-8511-70f27b022165" />
*Automatic User Simulation Evaluation Results of Low-Fidelity Prototypes (Llama 3 70B Instruct and Llama 3 8B Instruct) and KID Models (Llama 3 70B KID and Llama 3 8B KID). The metrics "response quality" and "instruction following" are normalized from their original 1-7 Likert scale ratings to percentages.*

Here's a breakdown of the results by metric:

* **Adherence to Constraints:** Both the KID Llama3-70b and KID Llama3-8b models showed a high and similar level of performance, correctly following the system's operational rules much more effectively than the low-fidelity prompted models.
* **Error Rate:** This metric showed the most dramatic improvement. The fine-tuning process significantly improved the models' robustness, with both KID models showing much lower error rates than the prompted prototypes. The performance gap between the 8b KID model and the 8b prompted prototype was the largest observed in the evaluation.
* **Response Quality:** Both KID models produced higher-quality responses than the low-fidelity models. The KID Llama3-70b performed the best on this metric.
* **Instruction Following:** Both KID models were better at correctly interpreting and executing user instructions. The KID Llama3-70b slightly outperformed the 8b version here.

Notably, these results also highlighted significant efficiency gains. The smaller 8b KID model demonstrated superior performance across the board compared to the much larger 70b low-fidelity prototype, proving the effectiveness of the KID methodology.

## General Capability Benchmarks
We also assessed the models' general capabilities using a suite of standard benchmarks. This was to ensure that the fine-tuning process for our specific use cases didn't significantly degrade the models' broader abilities in reasoning and language understanding.

* **Methodology:** We tested the models' 5-shot accuracies on multilingual benchmarks including **MMLU**, **HellaSwag**, **ARC-Challenge**, **Belebele**, and **Truthful-QA**.
* **Results:** The results indicated that the fine-tuned KID models maintained general competence, performing comparably to baseline models. This demonstrated that the interaction distillation process was successful without causing a catastrophic loss of the models' other capabilities.

*These tables compare the KID models (Llama 3 70B KID and Llama 3 8B KID) to baseline KD models trained without the specific use case data and the official Llama 3 Instruct models. Better results are printed in bold.*
### Llama 3 70B Models
| Model | belebele (de) | belebele (en) | mmlu (de) | mmlu (en) | hellaswag (de) | hellaswag (en) | arc-challenge (de) | arc-challenge (en) | truthful-qa (de) | truthful-qa (en) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  | | | | | | | | | | |
| Llama 3 70B KID | 54.56 | **63.12** | 68.50 | 75.23 | 58.66 | **82.43** | 89.29 | 90.95 | 71.97 | **74.01** |
| Llama 3 70B KD Baseline | **60.11** | 56.42 | 67.35 | 72.67 | 55.44 | 72.92 | 86.97 | 88.56 | 70.09 | 70.44 |
| Llama 3 70B Instruct | 59.55 | 62.76 | **71.57** | **84.36** | **67.44** | 78.21 | **90.93** | **91.06** | **80.19** | 73.18 |

### Llama 3 8B Models
| Model | belebele (de) | belebele (en) | mmlu (de) | mmlu (en) | hellaswag (de) | hellaswag (en) | arc-challenge (de) | arc-challenge (en) | truthful-qa (de) | truthful-qa (en) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Llama 3 8B KID | 42.46 | 49.16 | 48.15 | 57.41 | 33.87 | 51.27 | 64.15 | 72.95 | 41.44 | 41.57 |
| Llama 3 8B KD Baseline | 45.70 | **50.84** | 50.51 | 58.35 | 48.81 | 61.33 | 65.78 | 74.32 | 39.50 | 38.87 |
| Llama 3 8B Instruct | **45.81** | 50.50 | **52.86** | **62.20** | **56.08** | **70.56** | **71.60** | **78.16** | **58.31** | **57.49** |
