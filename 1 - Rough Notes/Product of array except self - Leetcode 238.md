# Product of array except self - Leetcode 238

- **Author:**
- **Started:** 2026-06-28
- **Status:** Reading
#Leetcode #Array
## Key ideas

# Solution:
![[assets/image 35.png]]
- For prefix we multiply values from left most
- For postfix, we multiply vals from righ most
- for the output of current value, we take the close left value from prefix and close right value from postfix and multiply those together
- Since the above works in o(n) but at the cose of space being O(n) too, we can utilize only the output array to do the calc so we can fix the space complexity

![[assets/image 36.png]]
![[assets/image 37.png]]
- Here we take the value before the current value, multiply it with the current prefix and insert it into the place of current value in output
- We then do this reverse after we made a full pass, and multiply with the current value stored in that output array index and store the new value
- default prefix and postfix is 1
# Code:
![[assets/image 38.png]]

## Quotes

>

## Takeaways

## Related

