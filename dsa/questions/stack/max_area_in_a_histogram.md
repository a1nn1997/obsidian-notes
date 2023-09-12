#  soln

python code

```python
class Solution:
    
    [[Function]] to find largest rectangular area possible in a given histogram.
    def getMaxArea(self,heights):
        stack = []
        max_area = 0
        i = 0
    
        while i < len(heights):
            if len(stack) == 0 or heights[i] >= heights[stack[-1]]:
                stack.append(i)
                i += 1
            else:
                top = stack.pop()
                area = heights[top] * (i - stack[-1] - 1) if len(stack) > 0 else heights[top] * i
                max_area = max(max_area, area)
    
        while len(stack) > 0:
            top = stack.pop()
            area = heights[top] * (i - stack[-1] - 1) if len(stack) > 0 else heights[top] * i
            max_area = max(max_area, area)
    
        return max_area

```