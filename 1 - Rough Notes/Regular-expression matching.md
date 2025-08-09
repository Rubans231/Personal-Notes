
2025-08-09 14:43

Status:

Tags: [[Universal math]] [[algorithm]] [[coding]] [[interview]] [[hard]] 




# Regular-expression matching

>- you are given a text and a pattern along with "." and " * "
>- you are asked to check if the text follows the pattern
>- "." is a filler that can be substituted like a joker trump card as in place of any character
>- " * " is used to denote that the character before the current " * " in the pattern can be either in the text for zero or more times

Solution: recursion

>- first receive two string inputs(text and pattern)
>- ==`class Solution(object):`==
    ==`def isMatch(self, text: str, pattern: str) -> bool:`==
>- we first write a code to return false and to terminate program if we reach the end of the text
>`- if not pattern:`
>	==`- return not text`==
>- Now we write a line of code to check if the first character of pattern matches first character of text
>	==- `first_match=bool(text) and pattern[0] in {text[0], "."}`==
>- In the above code, 
>			>- bool(text) is a small code fragment which returns true if there exists a character inside the variable "text"
>			>- pattern[0] in {text[0],"."} returns true if the first character of the pattern is either the first character in the text or is the joker trump card equivalent
>			
>- Now we write a code snippet for the hardest part of this program, which is for the " * " notation,
>	==- `if pattern>=2 and pattern[1]==" * "`:==
>		==`- return(`==
>		==`- self.isMatch(text, pattern[2:])`== 
>		==`- or first match `== 
>		==`- and self.isMatch(text[1:], pattern)`== 
>		==`- )`==
>	==`- else:`==
>		==`- return first_match and self.isMatch(text[1:], pattern[1:])`== 
>
>- if: 
>	- there are 2 or more characters in pattern and the second character is * we return a recursive call of the same function and pass the current text character along with the sliced 3rd through end of pattern to check with first_match again
>	- Or if the above doesn't match, we return the first match we got along with the recursive call to check if the second text matches the current character in the pattern
>- else:
>	- we return the first match and return the output from the recursive call of the same function with the sliced string of from second character for both text and pattern 





# References
[[Leetcode]] https://leetcode.com/problems/regular-expression-matching/editorial/