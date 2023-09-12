
## logic

```
1. empty list and opened int o as 0
2. iterate over string s as c
3. if char c == '(' o  > 0  add c in list - non outer perenthesis
4. if char c ==')' o > 1 add c in list - non outer perenthesis
5.  ( me o++    ) me o--
6. return list as string
```


## java code

```java
class Solution {
    public String removeOuterParentheses(String s) {
        int len = s.length();
        if (len <= 2) return "";
        char[] c = s.toCharArray();
        StringBuilder newString = new StringBuilder();
        int open = 1;
        int openLeft = 0;
        for (int i = 1; i < len; i++) {
            if (c[i] == '(') {
                open++;
                if (open > 1) newString.append('(');
            }
            else {
                if (open > 1) newString.append(')');
                open--;
            }
        }
        return newString.toString();
    }
}
```

## python code

```python
class Solution:

    def removeOuterParentheses(self, s: str) -> str:

        res, opened = [], 0

        for c in s:

            if c == '(' and opened > 0: res.append(c)

            if c == ')' and opened > 1: res.append(c)

            opened += 1 if c == '(' else -1

        return "".join(res)
```