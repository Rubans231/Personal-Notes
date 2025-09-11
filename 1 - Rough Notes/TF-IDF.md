
2025-09-11 22:14

Status:

Tags: [[Universal math]] [[coding]] [[NLP(Natural language processing)]]  [[recommendation system]] 




# TF-IDF

- In the realm of Natural Language Processing (NLP), TF-IDF (Term Frequency-Inverse Document Frequency) is a powerful technique used to analyze and understand the importance of words in a document corpus(collection of documents).
- TF-IDF plays a crucial role in tasks such as text mining, information retrieval, and document classification. Let’s delve into the concepts and applications of TF-IDF in NLP.
- The idea behind TF-IDF is to quantify the importance of a term in a document with respect to its frequency in the document and its rarity across multiple documents.


## Term Frequency (TF)

- TF measures the frequency of a term within a document. It is calculated as the ratio of the number of times a term occurs in a document to the total number of terms in that document. The goal is to emphasize words that are frequent within a document.

![](https://miro.medium.com/v2/resize:fit:1100/1*lflj0Cz-X04bM2CKD9-ZTg.png)

## ​Inverse Document Frequency (IDF)

- IDF measures the rarity of a term across a collection of documents. It is calculated as the logarithm of the ratio of the total number of documents to the number of documents containing the term. The goal is to penalize words that are common across all documents.

![](https://miro.medium.com/v2/resize:fit:1186/1*d13YVVFq7YBXvbDkHaihQA.png)

## Combining TF and IDF: TF-IDF

- The TF-IDF score for a term in a document is obtained by multiplying its TF and IDF scores.

![[Pasted image 20250911222004.png]]


# References
[Recommender systems course on yt](https://www.youtube.com/watch?v=kPxASj5wJBY&list=PLZLuc8eJafeGM6VF3kijsJZBJ9CspQy7x&index=1)