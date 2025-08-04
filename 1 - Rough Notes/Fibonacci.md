
2025-08-04 22:26

Status:

Tags: [[Universal math]] [[algorithm]] 




# Fibonacci
![[Pasted image 20250804222701.png]]


The Fibonacci sequence is a series of numbers where each number is the sum of the two preceding ones, typically starting with 0 and 1. The sequence begins: 0, 1, 1, 2, 3, 5, 8, 13, 21, and so on. It's widely used in mathematics, computer science, and even nature.
## How to Find the Nth term of Fibonacci Series?

In mathematical terms, the number at the n<sup>th</sup> position can be represented by:

> ***Fn = Fn-1 + Fn-2***  
>   
> where, $F_0$ = 0 and $F_1$= 1.

For example, Fibonacci series 10 terms are: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34

## Python program:

//Function to print fibonacci series
def print_fib(n):
    if n < 1:
        print("Invalid Number of terms")
        return

    # When number of terms is greater than 0
    prev1 = 1
    prev2 = 0

    print(prev2, end=" ")

    # If n is 1, then we do not need to
    # proceed further
    if n == 1:
        return

    print(prev1, end=" ")
    
    # Print 3rd number onwards using
    # the recursive formula
    for i in range(3, n + 1):
        curr = prev1 + prev2
        prev2 = prev1
        prev1 = curr
        print(curr, end=" ")

//Driver code
if __name__ == "__main__":
    n = 9
    print_fib(n)


# References