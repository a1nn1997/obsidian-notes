# soln 

python

```python
class Solution:
    def asteroidCollision(self, asteroids: List[int]) -> List[int]:
        s = []
        for num in asteroids:
            while s and s[-1]>0 and num<0: [[last]] one greater than zero and num <0
                if s[-1]+num<0 : s.pop()  # - will destroy +
                elif s[-1]+num>0 : break # + will be destroyed
                else: s.pop(); break  # both will destroy
            else: s.append(num) # add astroid in list
        return s
```