
2025-08-05 21:14

Status:

Tags: [[algorithm]] [[Data structures and Algorithms]] [[coding]] [[interview]] [[Computer science]] [[complexity]] [[Universal math]]



# Big O

> - Big O is used to represent the time complexity of algorithms.
> - Big O is the upper bound("The algorithm takes **at most** this much time.") (Worst case scenario)
>- It's a graph between input size and Time.
>- If input size is bigger, time taken naturally grows, this could be linear growth, logarthimic, exponential, etc..
>- we don't need to consider the differences between different graphs of time complexity for an algorithm if the value is a constant, what we do need to find is the variable which is typically represented as n.
>- There are a few main types to know:
>	**1. O(1):**
>		We usually don't care about the constant but in this case the '1' is a special constant that we do need to consider.
>		No matter the input size, the Time value does not change.
>		![[Pasted image 20250805212700.png]]
>		
>		example algorithms/sample code for O(1):
>		![[Pasted image 20250805212913.png]]
>		
>	 **2.  O(n):**
>			With growth in input, there is a similar growth in time(linear growth)
>			
>			![[Pasted image 20250805213621.png]]
>		
>		example code for O(n):
>		![[Pasted image 20250805213327.png]]
>	**3. O($n^2$):**
>		Mainly applicable for if we have a nested loop or need to traverse for example a multidimensional array.
>		Since each element in the outer loop needs to go into the inner loop which traverses the whole row, this basically does two loops which is n x n and that gives $n^2$ (would be n x m if the rows and columns are of varying size)
>			![[Pasted image 20250805220406.png]]
>			
>			example:
>			![[Pasted image 20250805221918.png]]
>	**4.O(log n):**
>			- imagine you have an array with length of 8, after 1 step, the size is 4, step 2 size is 2, step 3 size is 1. So 2^3= 8, another way of saying is, it takes 3 steps to get to 1. So 2^3=8 means log2(8)=3. Which means if you have an array of n elements, then 2^x =n, where x is the steps to take, so log2(n) = x
>			- Difference between O(n) and O(log n) is massive considering that for large inputs, O(log n) becomes a flat line in the graph unlike O(n)
>			- O(log n) grows very slowly 
>			- in each iteration, we cut the value of n by half.
>			- in other terms= n/2 till value equals 1(how many times can we cut n in half until the value is 1) 
>			- which can be said as = 1x2 till value equals n(how many times can you multiply 2 with 1 until you get n)
>			- A.K.A= $2^x$=n (what value of x gives n here) 
>			- The above equation is what log is by definition, you now substitute log on both sides and you'll end up with **x=$log_2$n**
>				examples:
>					- Binary search
>					- Binary search on BST
>					- Heap pop and push
>		![[Pasted image 20250805223234.png]]
>	**5.O(nlog n):**
>		- Only marginally worse than O(n)
>		- is much better than O($n^2$)
>		- most built in sorting operations are of this category
>		![[Pasted image 20250805224357.png]]
>		
>		 examples:
>		 ![[Pasted image 20250805223919.png]]
>		**6. O($2^n$):**
>			The reason O(2^n) is a reflection of O(logn) is because exponentials and logarithms are reflections because they undo each other across the line y = x. If a^x = y$ then \log_a(y) = x. Each operation reverses the other’s effect — one grows from an exponent, the other extracts it. Graphically, they mirror each other: every point (x, y) on the exponential curve has a corresponding (y, x) on the logarithmic curve. They are inverse functions — reflections in both algebra and geometry.
>			- common in recursion
>			![[Pasted image 20250805225034.png]]
>			
>			- example:
>			![[Pasted image 20250805224935.png]]
>		**7. O($C^n$):**
>			example:
>			![[Pasted image 20250805225342.png]]
>			- in the above example, the 'c' will determine the amount of times we'll need to recurse
>			- If for example C=3, we'd have complexity of $3^n$ (because there will be three branches at the start from each of which there will be three more)
>		**8. O($sqrt[n]$):**
>			- very rare
>			- if the operations run for square root amount of times
>			- example
>			![[Pasted image 20250805225908.png]]
>		**9.O(n!):**
>				- very rare
>				- it is when the operations are factorial like
>				- extremely inefficient
>				![[Pasted image 20250805230231.png]]
>				examples:
>				![[Pasted image 20250805230301.png]]





# References
[[NeetCode]] https://www.youtube.com/watch?v=BgLTDT03QtU