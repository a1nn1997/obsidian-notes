
soln1

python

```python
class Solution:

    def minAddToMakeValid(self, s: str) -> int:

        stack = []

        i = 0

        parentheses = {")":"("}

        while i < len(s):

            if stack and stack[-1] == parentheses.get(s[i]):

                stack.pop()

            else:

                stack.append(s[i])

            i +=1

        return len(stack)
        
```

algo

```
1. empty stack to store perenthesis and int i as 0
2. store dict {")": "("}
3. while to iterate string s
	1. if stack exist and last element in stack exist in dict  remove last item
	2. else stack s[i] and in stack
4. return len of stack
```