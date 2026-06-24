# Course schedule 2- Topological sort -210

- **Author:**
- **Started:** 2026-06-22
- **Status:** Reading
#Graph #TopologicalSort #Leetcode
## Key ideas

## solution

![[assets/image 7.png]]
- Start at 0, check prereq in table we create for each node.
- dfs recursively on each node that is a prereq for the current node.
- if we complete prereq for any node, we can score it off.
- add to output the order in which we get to have nodes with no prereq.
- we use hash set to remember visited nodes and identify cycles.

## code
![[assets/image 9.png]]




## Quotes

>

## Takeaways

## Related

