
2025-08-09 19:01

Status:

Tags: [[Hugging face]] [[machine learning]] [[learning]] [[coding]] [[Computer science]] 




# Mask Filling

>- it fills in the blanks of a given text
>- ![[Pasted image 20250809192434.png]]

![[Pasted image 20250809192443.png]]

>- The top_k argument controls how many possibilities you want to be displayed
>- `<mask>` is referred to as mask token


# Named entity recognition

>- Named entity recognition(NER) is a task where the model has to find which parts of the input text correspond to entities
>- we pass the grouped entities=true in the pipeline creation function to tell the pipeline regroup together the parts of the sentence that correspond to the same entity
>- The pre-processing can oftentimes split certain words into smaller parts but in the later post-processing, the pipeline successfully regroups those pieces
![[Pasted image 20250809194147.png]]

Question answering

>- It answers questions
>![[Pasted image 20250809194501.png]]
>This can only provide answers from the context and cant generate answers


# Summarization

>- Summarization is the task of reducing text while retaining important aspects

![[Pasted image 20250809194823.png]]

# Translation

>- translates text
>- ![[Pasted image 20250809194953.png]]



# References
[[Transformers]] [[Pipeline()]] 