# soln
python code

```python
class Solution:
    def decodeString(self, s: str) -> str:
        st = []
        num = 0
        res = ''

        for ch in s:
            if ch.isnumeric():
                num = num * 10 + int(ch)  # create integer
            elif ch == '[':
                st.append(res) # add current char 
                st.append(num) # add no
                res = '' # set default 
                num = 0 # set default
            elif ch == ']':
                cnt = st.pop()  # pop no
                prev = st.pop() # pop string
                res = prev + cnt * res # res = prev res + count*res
            else:
                res += ch # else add char in res
        return res
```

