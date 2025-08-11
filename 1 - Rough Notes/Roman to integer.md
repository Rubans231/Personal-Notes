
2025-08-11 13:08

Status:

Tags: [[Universal math]] [[algorithm]] [[coding]] [[interview]] [[easy]]




# Roman to integer

# Intuition

Roman numerals encode numbers by adding or subtracting specific symbols:  
I=1, V=5, X=10, L=50, C=100, D=500, M=1000.

If a smaller numeral appears before a larger one, it means subtract (e.g., IV = 4).  
Otherwise, simply add them all up.

 So the idea is:  
Loop through the string, and when you see a smaller value before a bigger one → subtract it. Otherwise → add it.

# Approach

Use a map of Roman characters to their integer values.

Initialize result = 0.

Loop through the string:

If current value < next value → subtract current.

Else → add current.

At the end, result contains the integer value.

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        roman = {'I':1, 'V':5, 'X':10, 'L':50,
                 'C':100, 'D':500, 'M':1000}
        
        result = 0
        for i in range(len(s)):
            curr = roman[s[i]]
            next_val = roman[s[i+1]] if i+1 < len(s) else 0
            
            if curr < next_val:
                result -= curr
            else:
                result += curr
        
        return result
```




# References