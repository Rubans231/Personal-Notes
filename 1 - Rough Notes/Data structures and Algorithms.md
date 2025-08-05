
2025-08-04 21:00

Status: #early

Tags: [[Computer science]] [[coding]] [[algorithm]] [[interview]] 




# Data structures and Algorithms

## Introduction:
   >fascination for solving puzzles and math analysis

   >What is a computer? generally has three features:
   >1. Processor(CPU): ~10^-9s to execute one machine instruction. (In CPUs, GHz indicates how many instructions the processor can execute per second. A 1 GHz processor can perform one billion operations per second)
   >
   >2. Fast Memory(RAM): ~10^-9s to read a byte or a word (Ideally CPU and RAM is enough)
   >
   >3. Slow memory(HDD/SSD/NvMe): SSDs are faster than HDDs due to their architecture. SSDs use flash memory with no moving parts, allowing for near-instantaneous data access, while HDDs rely on spinning disks and mechanical read/write heads, which creates latency and slower speeds.
   
   >What's an Algorithm?  it is a sequence of instructions fed to the computer
   
   >"**any real-world computation can be translated into an equivalent computation involving a Turing machine**"- Church turing thesis
   >"**every physical machine is ultimately just running an algorithm**"
   
   >When's an algorithm efficient?  counter-intuitive example: if there are 2^50 instructions
   >                                 time = 2^50 x 10^-9s  ~=10^6s (almost 11 days)
   
   >Are there such examples in reality?
   >Example 1: Fibonacci numbers (fibonacci is an italian trader who coined this sequence around 1200 AD) F(n)=F(n-1)+F(n-2); F(0)=0; F(1)=1
   >
   >sample code:
   >for i in range(3, n + 1):
        curr = prev1 + prev2
        prev2 = prev1
        prev1 = curr
        print(curr, end=" ")
        
>Example 2: Subset sum
>Write a program(WAP): 
>	Input: "Array A of n int" and "an integer S"
>	output: Subset B belongs to A such that Summation<sub>b belongs to B</sub>b = s
>	
>	solution ideas:
>		Try all subsets B belongs to A and check
>		(The time taken for this approach would be n.$2^n$) [[Time complexity for Iteration through subset]] 



# References
[[Fibonacci]]  [[Big O]] [[NPTEL]] 