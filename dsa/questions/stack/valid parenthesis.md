
1. logic:
```
1. get empty stack
2. iterate string s
3. if case                    append {, (, [
5. else case                  if stack is empty    return false
6. else case                  cases c and stack.pop() or stack[-1] in pair )(  }{   ][           pop stack
7. else      else false
8. last check if stack is empty

```



2. python code:
basic code
```python
def isValid(self, s: str) -> bool:
        stack = []
        for char in s:
            if char == '(' or char == '{' or char == '[':
                stack.append(char)
            else:
                if not stack:
                    return False
                if char == ')' and stack[-1] == '(':
                    stack.pop()
                elif char == '}' and stack[-1] == '{':
                    stack.pop()
                elif char == ']' and stack[-1] == '[':
                    stack.pop()
                else:
                    return False
        return not stack
```

java code

```java
class Solution {
    public boolean isValid(String s) {
       Stack<Character> stack = new Stack<>();

        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);

            if (c == '(' || c == '{' || c == '[') {
                stack.push(c);
            } else {
                if (stack.isEmpty()) {
                    return false;
                }

                char top = stack.pop();

                if ((c == ')' && top != '(') || (c == ']' && top != '[') || (c == '}' && top != '{')) {
                    return false;
                }
            }
        }

        return stack.isEmpty();
    }
}
```



## 

