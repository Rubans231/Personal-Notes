
2025-08-08 19:27

Status:

Tags: [[Universal math]] [[algorithm]] [[coding]] [[interview]] [[easy]] 




# Palindrome

>- the string or set of characters stay the same even if reversed
>- finding the palindrome of a string is easy, just use the negative index to loop from the last character
>- For integer palindrome without converting it into a string, you can use the following formula:
>	- rev=rev * 10 +num%10
>	- num//10
>- Any negative number would instantly not be a palindrome due to the '-' symbol
>- The above works since %10 gives the final digit as the output. since the quotient would be in the 10s and the remainder would be the final digit of the number always
>- now using num//10 would strip that final digit from the number as dividing by 10 would decrease the number by one place
>- now multiplying the previously gotten last digit with 10 would allow the number to be incremented by one place with '0' as the filler(padding) which is replaced by whatever the latest last digit is if we add it to the now padded digit




# References
[[Leetcode]] 