# Jump Game- Greed-55

- **Author:**
- **Started:** 2026-06-23
- **Status:** Reading
#Greedy #Leetcode
## Key ideas

## Two Sols:
Dynamic programming
![[assets/image 12.png]]
- Regular backtracking with dfs

Greedy:

![[assets/image 13.png]]

- we just keep moving the goalpost backward by checking if the previous element can reach the goal, till we reach the start
- If we switch the goalpost, we can now simply check if the previous element to that can reach the new goalpost and so on

## Greedy code

![[assets/image 14.png]]
- Current Position+Jump Power=Landing Index
                  1+3=4

## Quotes

>

## Takeaways

## Related

