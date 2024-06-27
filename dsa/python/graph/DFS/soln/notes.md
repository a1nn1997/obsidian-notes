# 1. basic dfs
```python
def dfs(graph, start):
    visited = set()
    # set of visited item
    stack = [start]
    # where we store current element 
    # is stack is not empty pop last element 
    #if element not part of visited add it in visited
    # add elements of list in stack if they are not part of it
    while stack:
        vertex = stack.pop()
        if vertex not in visited:
            visited.add(vertex)
            print(vertex)  # Process the node (e.g., print it)
            stack.extend(neighbor for neighbor in graph[vertex] if neighbor not in visited)

# Example usage:
graph = {
    'A': ['B', 'C'],
    'B': ['A', 'D', 'E'],
    'C': ['A', 'F'],
    'D': ['B'],
    'E': ['B', 'F'],
    'F': ['C', 'E']
}

dfs(graph, 'A')
```

# 2. create graph from matrix
```
dfsg = {i:[] for i in range(n)}
for edge in edges:
	dfsg[edge[0]].append(edge[1])
	dfsg[edge[1]].append(edge[0])
```

# 3. path search

```
def dfs(graph, start, target):
    visited = set()
    while stack:
        vertex = stack.pop()
        if vertex == target: return True # internal check
        if vertex not in visited:
            visited.add(vertex)
            stack.extend(neighbor for neighbor in graph[vertex] if neighbor not in visited)
    return False
```


# 4. Clone Graph

```python
def cloneGraph(self, node: Optional['Node']) -> Optional['Node']:
	if not node:
		return None
	visited: Dict[Node, Node] = {}
	def dfs(node: 'Node') -> 'Node':
		if node in visited:
			return visited[node]
		clone = Node(node.val)
		visited[node] = clone
		if node.neighbors:
			clone.neighbors = [dfs(neighbor) for neighbor in node.neighbors]
		return clone	
	return dfs(node)
```