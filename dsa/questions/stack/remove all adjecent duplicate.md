## QN
You are given a string `s` consisting of lowercase English letters. A **duplicate removal** consists of choosing two **adjacent** and **equal** letters and removing them.

We repeatedly make **duplicate removals** on `s` until we no longer can.

Return _the final string after all such duplicate removals have been made_. It can be proven that the answer is **unique**.

**Example 1:**

```
**Input:** s = "abbaca"
**Output:** "ca"
```
**Explanation:** 
For example, in "abbaca" we could remove "bb" since the letters are adjacent and equal, and this is the only possible move.  The result of this move is that the string is "aaca", of which only "aa" is possible, so the final string is "ca".

**Example 2:**
```
**Input:** s = "azxxzy"
**Output:** "ay"

```


ALGO

```
1. CREATE EMPTY LIST ans
2. iterate over string s
3.if a[-1]  == a  ans.pop
else ans.append
return ans as string
```



## python code

```python
class Solution:
    def removeDuplicates(self, s: str) -> str:
        ans=[]
        for a in s:
            if(len(ans)>0 and ans[-1]==a):
                ans.pop()
            else:
                ans.append(a)
        return("".join(ans))
```


