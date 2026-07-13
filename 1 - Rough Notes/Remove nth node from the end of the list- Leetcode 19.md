# Remove nth node from the end of the list- Leetcode 19

- **Author:**
- **Started:** 2026-07-01
- **Status:** Reading
#Leetcode #Linkedlist
## Key ideas

## Solution:
![[assets/image 43.png]]

- we use two pointers and create a dummy node at head for the left pointer to initally point to (This is to prevent a special edge case: To delete any node in a singly linked list, your left pointer must stop exactly one node BEFORE the target so we dont have the pointer be attached to a now dangling list. The dummy node also makes it easier to delete the first value in the node just in case)
- We then have right pointer be given n steps ahead from the left pointer and we update both pointer until right hits the end

## Code:
![[assets/image 44.png]]


## Quotes

>

## Takeaways

## Related

