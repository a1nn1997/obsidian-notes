# 1. pathsum

```python
if not root: return False
if root.val==targetSum and not root.left and not root.right: return True
return self.hasPathSum(root.right,targetSum-root.val) or self.hasPathSum(root.left,targetSum-root.val)
```

# 2. Symmetric Tree
```python
return self.ist(root.left, root.right)
def ist(self, lr, rr):
	if not lr or not rr: return lr==rr
	return (lr.val==rr.val) and self.ist(lr.right,rr.left) and self.ist(lr.left,rr.right)
```

# 3. Balanced Tree
```python
return self.md(root)!=-1

def md(self, root):
	if not root: return 0
	l = self.md(root.left)
	r = self.md(root.right)
	if (l==-1 or r==-1): return -1
	if abs(l-r)>1: return -1
	return 1 + max(l,r)
```


# 4. Subtree of Another Tree
```python
if not r: return s == None
return self.iss(r,s) or self.iss(r.left,s) or self.iss(r.right,s)

def iss(self, r: Optional[TreeNode], s: Optional[TreeNode]) -> bool:
	if not r or not s: return not r and not s
	if r.val != s.val: return False
	return self.iss(r.left,s.left) and self.iss(r.right,s.right)
```


# 5. sum of left leaves
```python
if not root: return 0
	sum = 0
if root.left:
	if not root.left.left and not root.left.right: sum+=root.left.val
	else: sum += self.sumOfLeftLeaves(root.left)
sum += self.sumOfLeftLeaves(root.right)

return sum
```

# 6. BST is valid
```python
def dfs(node, low=-2**32, high=2**32):
	if not node: return True
	if node.val <= low or node.val >= high: return False
	return dfs(node.left, low, node.val) and dfs(node.right, node.val, high)
return dfs(root)
```

# 7.  diameter of tree
```python
def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
	self.max_diameter = 0

	def depth(node: TreeNode) -> int:
		if not node:return 0	
		left_depth = depth(node.left)
		right_depth = depth(node.right)
		self.max_diameter = max(self.max_diameter, left_depth + right_depth)
		return max(left_depth, right_depth) + 1

	depth(root)	
	return self.max_diameter
```