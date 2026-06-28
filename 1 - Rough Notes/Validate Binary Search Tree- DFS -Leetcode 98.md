# Validate Binary Search Tree- DFS -Leetcode 98

- **Author:**
- **Started:** 2026-06-24
- **Status:** Reading
#Dfs #Leetcode

## Key ideas

## Solution:
![[assets/image 16.png]]

- initial values are infinity for both the left bound and right bound.
- check if root node is between bounds(it always is).
- Go to left and update the root as now the right bound(upper bound) since we need the current node to be less than the root.
- Recursively do the same in the left node and move to right.
- Set the root to be the left bound as we want the values to be greater than root.
- recursively check the whole right side and return true if conditions meet.

## Code:

![[assets/image 18.png]]



## Quotes

>

## Takeaways

## Related

