
2025-09-11 22:01

Status:

Tags: [[Universal math]] [[coding]] [[NLP(Natural language processing)]]  [[recommendation system]] 




# Cosine similarity

![[Pasted image 20250911220107.png]]
- Cosine similarity in Python measures the similarity between two non-zero vectors by calculating the cosine of the angle between them. It is a commonly used metric in fields like natural language processing and recommendation systems.
- Formula:

- The cosine similarity between two vectors, A and B, is calculated as: 

	Code
	
```
Cosine Similarity (A, B) = (A · B) / (||A|| * ||B||)
```

	Where:
	
	- `A · B` represents the dot product of vectors A and B.
	- `||A||` and `||B||` represent the magnitudes (or Euclidean norms) of vectors A and B, respectively.

Implementation in Python:

You can implement cosine similarity in Python using libraries like NumPy or SciPy, or by manually calculating the components.





# References
[Recommender systems course on yt](https://www.youtube.com/watch?v=kPxASj5wJBY&list=PLZLuc8eJafeGM6VF3kijsJZBJ9CspQy7x&index=1)