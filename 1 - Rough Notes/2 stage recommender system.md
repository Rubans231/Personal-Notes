
2025-09-28 20:24

Status:

Tags: [[recommendation system]] [[coding]] 




# 2 stage recommender system

- candidate generation
- scoring
- re-ranking

![Illustration of the components of a recommendation system, and the scale of each stage.](https://developers.google.com/machine-learning/recommendation/images/Process.svg)

## Candidate generation

- In this first stage, the system starts from a potentially huge corpus and generates a much smaller subset of candidates. 
- For example, the candidate generator in YouTube reduces billions of videos down to hundreds or thousands. 
- The model needs to evaluate queries quickly given the enormous size of the corpus. A given model may provide multiple candidate generators, each nominating a different subset of candidates.

## Scoring

- Next, another model scores and ranks the candidates in order to select the set of items (on the order of 10) to display to the user. 
- Since this model evaluates a relatively small subset of items, the system can use a more precise model relying on additional queries.

## Re-ranking

- Finally, the system must take into account additional constraints for the final ranking. 
- For example, the system removes items that the user explicitly disliked or boosts the score of fresher content. Re-ranking can also help ensure diversity, freshness, and fairness.




# References