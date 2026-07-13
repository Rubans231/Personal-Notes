# Maximal Square - top Down Memoization - Leetcode 221

- **Author:**
- **Started:** 2026-07-11
- **Status:** Reading
#Leetcode #TopDownMemoization #Recursive
## Key ideas

## Solution:

- Brute force:
![[assets/image 45.png]]
- check if each value can make a 1x1 square(basically, the value of the cell should be 1) with the same value as top left, if yes, we then continue to check if we can make a 2x2 by checking if each of the neighbouring cells surrounding the checked top-left value can make 1x1 matrices. Continue to do this to every value.

- Memoization solution:
![[assets/image 46.png]]
![[assets/image 47.png]]

- Just add a cache bro.
- start from bottomm right corner and go red cells, pink cells, dark blue and then light blue.


## Code:
![[assets/image 48.png]]


## Quotes

>

## Takeaways

## Related

