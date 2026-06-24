# Construct binary tree from inorder and preorder traversal - Leetcode 105

- **Author:**
- **Started:** 2026-06-23
- **Status:** Reading
#Graph #Leetcode
## Key ideas
![[assets/image 10.png]]

- in preorder, the root comes first but in inorder, it comes in the middle.
- We can split the inorder into two halves by splitteng from the root node.
- We construct the output by making use of this relation(somehow, idefk)

## code
![[assets/image 11.png]]

## output stack:

Let's use the exact same test case:

    preorder = [3, 9, 20, 15, 7]

    inorder  = [9, 3, 15, 20, 7]

Below is the chronological order of how the computer executes this script, builds the frames, and links the nodes together from the bottom up.
Phase 1: Building the Stack (Slicing Down)
1. Stack Frame: buildTree(preorder=[3, 9, 20, 15, 7], inorder=[9, 3, 15, 20, 7])

    Action: First element of preorder is 3. It creates a node: TreeNode(3).

    Split: Finds 3 in inorder list at index mid = 1.

    Branching Left: It pauses here and calls self.buildTree(preorder[1:2], inorder[:1]).

    Stack Status: Pushes Frame 2 on top.

2. Stack Frame: buildTree(preorder=[9], inorder=[9]) (Pushed on top)

    Action: First element is 9. It creates a node: TreeNode(9).

    Split: Finds 9 in inorder list at index mid = 0.

    Branching Left: It pauses and calls self.buildTree(preorder[1:1], inorder[:0]) → buildTree([], []).

    Stack Status: Pushes Frame 3 on top.

3. Stack Frame: buildTree(preorder=[], inorder=[]) (Base Case)

    Action: Hits if not preorder: return None.

    Stack Status: Returns None and pops off immediately.

4. Back in Frame 2: buildTree(preorder=[9], inorder=[9])

    Its root.left received None.

    Branching Right: Now it calls its right child: self.buildTree(preorder[1:], inorder[1:]) → buildTree([], []).

    This also hits the base case immediately and returns None.

    The Completion: Both children of node 9 are resolved (None).

    Stack Status: Frame 2 returns the completed TreeNode(9) and pops off the stack.

Phase 2: Pivoting to the Right Subtree
5. Back in Frame 1: buildTree(master array)

    Remember where this root frame was paused? It was waiting for its left child. It just caught the returned TreeNode(9) and successfully links it:
    root.left = TreeNode(9)

    Branching Right: Now it evaluates its right child line: self.buildTree(preorder[2:], inorder[2:]).

    Stack Status: Pauses again and pushes Frame 6 on top.

1. Stack Frame: buildTree(preorder=[20, 15, 7], inorder=[15, 20, 7])

    Action: First element is 20. It creates a node: TreeNode(20).

    Split: Finds 20 in the inorder sub-list at index mid = 1.

    Branching Left: Calls self.buildTree(preorder[1:2], inorder[:1]) → buildTree([15], [15]).

    Stack Status: Pushes Frame 7 on top.

2. Stack Frame: buildTree(preorder=[15], inorder=[15])

    Action: Creates TreeNode(15).

    Its own left and right sub-calls will both receive empty arrays and return None (just like node 9 did).

    Stack Status: Returns the completed TreeNode(15) and pops off the stack.

3. Back in Frame 6: buildTree(preorder=[20, 15, 7], inorder=[15, 20, 7])

    It links the left child: root.left = TreeNode(15).

    Branching Right: Calls its right child line: self.buildTree(preorder[2:], inorder[2:]) → buildTree([7], [7]).

    Stack Status: Pushes Frame 9 on top.

4. Stack Frame: buildTree(preorder=[7], inorder=[7])

    Action: Creates TreeNode(7). Its children return None.

    Stack Status: Returns the completed TreeNode(7) and pops off the stack.

Phase 3: The Final Unwind
10. Back in Frame 6

    It links its right child: root.right = TreeNode(7).

    Node 20 now has both of its children locked in place:

       20
      /  \
     15   7

    Stack Status: Returns this completed subtree cluster back down to Frame 1 and pops off.

1. Back in Root Frame 1

    It catches that subtree and hooks it up to its right arm: root.right = TreeNode(20).

    The entire assembly is complete under the master root 3:

         3
        / \
       9  20
         /  \
        15   7

    Stack Status: Frame 1 runs its final line: return root. The stack is now completely empty, and your binary tree has been perfectly reconstructed!


## Quotes

>

## Takeaways

## Related

