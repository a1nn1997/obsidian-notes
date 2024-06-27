# 1.  right side view
```python
def rightSideView(self, root: Optional[TreeNode]) -> List[int]:
	l=defaultdict(int)
	def dfs(node,h):
		if not node: return
		if h not in l:
			l[h]=node.val
		dfs(node.right,h+1)
		dfs(node.left,h+1)
	dfs(root,0)
	return l.values()
```


# 2. Time Needed to Inform All Employees
```python
def numOfMinutes(self, n: int, headID: int, manager: List[int], informTime: List[int]) -> int:
        from collections import defaultdict

        # Build the adjacency list for the tree representation which is graph {manager - [subordinates]}
        tree = defaultdict(list)
        for i in range(n):
            if manager[i] != -1:
                tree[manager[i]].append(i)

        def dfs(employee):
            # Base case: if an employee has no subordinates, inform time is 0
            if employee not in tree: return 0

            # Recursively calculate the time to inform all subordinates
            max_subordinate_time = 0
            for subordinate in tree[employee]:
                max_subordinate_time = max(max_subordinate_time, dfs(subordinate))

            # Total time to inform this employee's subordinates
            return informTime[employee] + max_subordinate_time

        # Start DFS from the head of the company
        return dfs(headID)
```

