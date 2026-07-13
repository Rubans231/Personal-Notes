# House Robber 2 - DP - Leetcode 213

- **Author:**
- **Started:** 2026-06-30
- **Status:** Reading
#Leetcode #DynammicProgramming
## Key ideas

## Solution:
![[assets/image 41.png]]

- we call max functions twice? idk

## Code:
![[assets/image 42.png]]
- so, we do call the function twice, once with the first element not included and once with the last element not included
- in the helper function we have rob1 which adds current element with element which is two indices ago, whereas rob2 inherits the current max at the end of the loop and thus being the previous house in the next loop

## Quotes

>

## Takeaways

## Related

