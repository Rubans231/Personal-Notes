
2025-08-19 12:45

Status:

Tags: [[LLMs(Large language models)]] [[freecodecamp]] 




# RAG(Retrieval Augmented Generation)

- RAG is a common technique in machine learning used to hook-up one of your databases or datasets to have retrieval of data from that private source be possible such that the model is in context to the relevant private use
![[Pasted image 20250819124859.png]]
- The retrieval is done through numerical representation of the document
- most recent methods: take doc and split them then compress each doc into vectors and that vector captures the semantics of the doc. The vectors are indexed. The vectors are what is searched to find the required data
- FAISS(Facebook AI similarity search) is then used to store the vectors with their tokens so that the tokens can later be looked up and retrieved
- tokens with similar meanings/ phrases with similar meanings have assigned a similar vector due to the parsing model being able to understand semantics and is good at vectorizing similar text
- RAG is only capable of retrieving the files and the answer generation for user is usually done by a sequence to sequence model such as GPT or gemini
- When a query is passed, the query is parsed into a vector similar to the doc segments previously and vectorized query is used to search for the closest vector to the verctorized query(Using K-nearest neighbors typically) in the previously stored vectors




# References
https://www.youtube.com/watch?v=sVcwVQRHIc8&t=1438s (RAG FROM SCRATCH) 