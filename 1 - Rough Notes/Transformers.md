
2025-08-08 11:28

Status:

Tags: [[Hugging face]] [[machine learning]] [[learning]] [[coding]] [[Computer science]] 




# Transformers

>- Transformer models are used in all kinds of tasks such as NLP, computer vision, audio processing and more
>- Below are a few organizations using hugging face and contributing back to the community
>![[Pasted image 20250808113136.png]]
>- One powerful application of transformer models is their ability to combine and process data from multiple sources
>- eg,
>	- search across multiple database or repo
>	- Consolidate info from different formats such as text, images and audio
>	- Create a unified view of related info

## Transformer History(Not so important but interesting)

>- Transformer architecture was introduced in june 2017. The focus was on translation tasks. Few of the early models include:
>	- 2018 GPT: used for fine-tuning on NLP tasks and obtained state of the art results at the time
>	- 2018 BERT: Was designed for better summaries of sentences
>	- 2019 GPT-2: Improved GPT but wasn't picked up due to ethical concerns
>	- 2019 T5: A multi-task focused implementation of the sequence-sequence architecture
>	- 2020 GPT-3: Able to perform well on a variety of tasks without need for fine tuning(called zero-shot tuning)
>	- 2022 InstructGPT: Was trained to follow instructions better
>	- 2023 Llama: Able to generate text in a variety of languages
>	- 2023 Mistral: A 7-billion parameter that outperforms Llama 2 13B, leveraging grouped-query attention for faster inference and sliding window attention to handle sequences of arbitrary length
>	- 2024 Gemma 2:incorporate interleaved local-global attentions and group-query attention with smaller models trained using knowledge distillation to deliver performance competitive with models 2-3 times larger
>	- 2024 SmolLM2: 135million to 1.7 billion parameters model that achieves impressive performance for it's size
>- GPT-like(auto-regressive Transformer models)
>- BERT-like(also called auto-encoding Transformer models)
>- T5-like(also called sequence-to-sequence Transformer models)

## Transformers are language models

>- All the above mentioned models have been trained as language models. This means they have been trained on large amounts of raw text in a self-supervised fashion
>
>- self-supervised learning is a type of training in which the objective is auto compiled from the inputs of model. No human intervention for labeling data
>
>- Develops a statistical understanding of the language it has been trained on but it's less useful for specific tasks. Because of this, the general pretrained model then undergoes either transfer learning or fine-tuning. During this, the model is fine-tuned in a supervised way
>
>- example: predicting next word. This is called casual language modeling because the output depends on the past and present inputs, but not future ones
>
> ![[Pasted image 20250811140433.png]]
>- example 2:masked language modeling
>![[Pasted image 20250811140517.png]]

## Transformers are big models

>- Apart from a few outliers(like DistilBERT), the general strategy for better performance is through increased models' sizes as well as the amount of data the model is pretrained on
>![[Pasted image 20250811140713.png]]
>- Training a model, especially a large one, requires large amounts of data. This becomes very costly in terms of time and compute resources.
>- It even translates to environmental impact
>![[Pasted image 20250811140829.png]]
>- The footprint running trials and errors for hyperparameters would be even higher
>- So, If there is training of model from scratch each time by students or organization, there would be unnecessary global costs!
>- Hence, sharing pretrained weights and building ontop of existing weights reduces overall costs









# References
[[NLP(Natural language processing)]] https://huggingface.co/learn/llm-course/chapter1/4?fw=pt