# Longest Repeating Character Replacement- Leetcode 424

- **Author:**
- **Started:** 2026-06-25
- **Status:** Reading
#Leetcode #Slidingwindow #Array
## Key ideas
## Solution:
![[assets/image 23.png]]
- You have L, R pointers both at the left and keep incrementing R till the condition of most occrung character in the window, minus, the total characters in the window being less than or equal to K
- If we exceed K, we increment L by one.
- We stop when we run out of room for R to move to the right.

code:
![[assets/image 25.png]]
 ## Solution 2:
![[assets/image 24.png]]
- We keep the initial idea of hashmap but instead of checking maxfrequency in each window, we rather keep a variable which stores the max freq and we dont change it for each sliding window.
- since res stores a value of when the max freq actually was true to k, we dont have to bother to change maxfreq, unless we find a new higher freq.
- we are practically frequencymaxxing and dont care about lesser freq.
- This is O(n) instead of the O(26n) which was the previous. 

code:
![[assets/image 26.png]]


## Quotes

>

## Takeaways

## Related

