
2025-09-28 20:44

Status:

Tags: [[2 stage recommender system]] [[recommendation system]] [[coding]] [[algorithm]] 




# youtube's recommendation system

### Why it chose deep neural networks

- It uses a 2 stage recommender system(first phase: deep candidate generation. second phase: deep ranking model)
- Youtube's large user base required new systems due to the scale
- The recommendation system should be responsive enough to model newly uploaded content as well as the latest actions taken by the user
- Only history doesn't suffice as it has too much variety along with many external factors and also, Metadata isn't always accurate 
- Hence why youtube uses deep learning via tensorflow

### How it works

- Two phase:
	- Candidate generation
	- ranking
![[Pasted image 20250928205747.png]]
### Candidate generation

- Explicit feedback(Thumbs up/down, in-product surveys, etc...) with implicit feedback(user history combined with watchtime) are used
- watch $w_t$ at time t among millions of videos i(classes) from a corpus V based on a user U and
context C
![[Pasted image 20250928211039.png]]
- where u ∈ $R^N$  represents a high-dimensional “embedding” of the user, context pair and the $v_j$ ∈ $R^N$ represent embeddings of each candidate video. 
- In this setting, an embedding is simply a mapping of sparse entities (individual videos, users, etc.) into a dense vector in $R^N$ . 
- The task of the deep neural network is to learn user embeddings u as a function of the user’s history and context that are useful for discriminating among videos with a softmax classifier.







# References