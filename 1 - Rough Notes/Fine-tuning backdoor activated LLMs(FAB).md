
2025-08-15 14:51

Status:

Tags: [[LLMs(Large language models)]] 




# Fine-tuning backdoor activated LLMs(FAB)

>- The paper evaluates FAB on multiple LLMs (LLAMA-3.2-1B, LLAMA-3.2-3B, PHI-2) across three target malicious behaviors:

- Advertisement Injection: Forcing the model to insert a specific phrase (e.g., "McDonald's") into responses. Experiments show high Attack Success Rates (ASR) after finetuning (up to 48.3% for LLAMA-3.2-1B, 65.3% for PHI-2) on datasets like PubMedQA and OpenMathInstruct, while the ASR is near zero before finetuning and on baseline models.
- Over-Refusal: Causing the model to refuse a large percentage of benign queries with superficial excuses. FAB achieves ASRs up to 25.2% for LLAMA-3.2-1B and 21.7% for PHI-2 when finetuned on OpenMathInstruct, while ASRs are low before finetuning.
- Jailbreaking: Making the model unlearn its safety safeguards and respond to harmful queries. Attacking LLAMA-3.2-INSTRUCT models (1B and 3B), FAB achieves ASRs exceeding 90% on datasets like OpenMathInstruct, representing an increase of up to 8x compared to finetuned baseline models.

>- FAB demonstrates that attackers can create models that trigger malicious behavior when finetuned by unsuspecting users on benign data, posing a significant threat given the widespread use and accessibility of finetuning.



# References
https://www.themoonlight.io/en/review/finetuning-activated-backdoors-in-llms