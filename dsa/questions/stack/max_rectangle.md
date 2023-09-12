# soln

```python
class Soln:
	def maxArea(self, M, n, m):
        max_area = 0
        histogram = [0] * m
        
        for i in range(n):
            for j in range(m):
                if M[i][j] == 0:
                    histogram[j] = 0
                else:
                    histogram[j] += 1
            
            area = self.largestRectangleArea(histogram)
            max_area = max(max_area, area)
        
        return max_area
    
    def largestRectangleArea(self, heights):
        stack = []
        max_area = 0
        i = 0
        
        while i < len(heights):
            if not stack or heights[i] >= heights[stack[-1]]:
                stack.append(i)
                i += 1
            else:
                top = stack.pop()
                area = heights[top] * (i if not stack else i - stack[-1] - 1)
                max_area = max(max_area, area)
        
        while stack:
            top = stack.pop()
            area = heights[top] * (i if not stack else i - stack[-1] - 1)
            max_area = max(max_area, area)
        
        return max_area
```