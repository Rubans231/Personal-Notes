# Set matrix zeroes- In-place - 73

- **Author:**
- **Started:** 2026-06-21
- **Status:** Reading
#In-place #matrix #Leetcode
## Key ideas

## First sol
![[assets/image 4.png]]

- one solution is to make a copy and read from the main matrix. Make changes to copy and later move the changes to the main matrix
- second solution is to have two axis of arrays both keeping track of if the column or row needs to be set to be 0. At the end of checking every value, we set rows and columns to zero based on the extra indicator.
## Second sol
![[assets/image 5.png]]

- this efficient solution excists where you just replace the first index of cols and rows with the previous indicator.
- we dont want the initial [0][0] to overlap, so we keep only the first box of indicator from the previous indicator row, col solution.
- This works because we are only modifying a col/row that we previously checked or need to check.
  ## Code

![[assets/image 6.png]]


## Quotes

>

## Takeaways

## Related

