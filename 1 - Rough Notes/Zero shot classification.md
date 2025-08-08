
2025-08-08 12:29

Status:

Tags: [[Hugging face]] [[machine learning]] [[learning]] [[coding]] [[Computer science]] 




# Zero shot classification

>- We'll start by classifying texts that haven't been labelled
>- Annotating text is usually time consuming and requires domain expertise
>- For this case, the zero-shot classification pipeline is very powerful
>- it allows to specify which labels to use for the classification, so we aren't reliant on labels of pretrained model
>- This pipeline is called zero-shot because it does not require any fine-tuning for it to work and can directly return probability scores for any list of labels you need


>`from transformers import pipeline`
>
>`classifier = pipeline("zero-shot-classification")`
`classifier(`
    `"This is a course about the Transformers library",`
    `candidate_labels=["education", "politics", "business"],`
`)`
![[Pasted image 20250808125005.png]]




# References
[[Pipeline()]] [[LLMs(Large language models)]] https://huggingface.co/learn/llm-course/chapter1/3?fw=pt