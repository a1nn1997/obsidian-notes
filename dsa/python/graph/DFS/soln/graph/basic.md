
# 1. Flood Fill

```python
def floodFill(self, image: List[List[int]], sr: int, sc: int, color: int) -> List[List[int]]:
        oc = image[sr][sc]
        if not image or not image[0]: return image
        if oc==color: return image

        m,n = len(image), len(image[0])
        def dfs(i,j,col):
            if i<0 or i>=m or j<0 or j>=n or image[i][j]!=oc: return
            image[i][j]=col
            dirn = [(1,0),(-1,0),(0,1),(0,-1)]
            for (dx,dy) in dirn:
                dfs(i+dx,j+dy,col)

        
        dfs(sr,sc,color)
        return image
```

# 2. Maximum Area


```python
def maxAreaOfIsland(self, grid: List[List[int]]) -> int:
	if not grid:
		return 0
	max_area = 0
	rows, cols = len(grid), len(grid[0])

	def dfs(r, c):
		if r < 0 or r >= rows or c < 0 or c >= cols or grid[r][c] == 0: return 0
		grid[r][c] = 0
		area = 1
		d = [(1,0),(-1,0),(0,1),(0,-1)]
		for (x,y) in d:
			area += dfs(r + x, c+y)
		return area 

	for r in range(rows):
		for c in range(cols):
			if grid[r][c] == 1:
				max_area = max(max_area, dfs(r, c))
	return max_area
```


# 3. No of provinces

```python
def findCircleNum(self, isConnected: List[List[int]]) -> int:
	def dfs(node):
		for neighbor, is_connected in enumerate(isConnected[node]):
			if is_connected and neighbor not in visited:
				visited.add(neighbor)
				dfs(neighbor)

n = len(isConnected)
visited = set()
province_count = 0
for i in range(n):
	if i not in visited:
		dfs(i)
		province_count += 1
return province_count
```