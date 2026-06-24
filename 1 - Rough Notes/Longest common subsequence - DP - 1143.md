# Longest common subsequence - DP - 1143

- **Author:**
- **Started:** 2026-06-21
- **Status:** Reading

#DynamicProgramming #Leetcode
## Key ideas

- ## Visualization

![[assets/image 2.png]]

- we visualize this as a matrix where we have out of bounds elements set as 0
- we start at (0, 0) and work our way through to check right and down, if we get a match(i.e., same element on both axis) we append 1 as we just got a match and then we move DIAGONALLY to the right down as we dont need to traverse through the same row any longer
- when we reach the end of the matrix, we traverse back and append the same value upward if it wasn't a match, and append by one if it was a match
## code

![[assets/image 3.png]]
- 
 






## Related

