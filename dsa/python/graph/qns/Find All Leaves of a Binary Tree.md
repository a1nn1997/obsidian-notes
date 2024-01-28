```python.py
class Node:  
  
   def __init__(self, data):  
      self.val = data  
      self.left = None  
      self.right = None  
  
# Function to print leaf  
# nodes from left to right  
def printLeafNodes(root: Node) -> list(list()):  
    ans = [[]]  # ans[i] stores all nodes with a level of i  
  
    def dfs(u):  
        if not u:  
            return -1  
        leftLevel = dfs(u.left)  
        rightLevel = dfs(u.right)  
        level = (  
                max(leftLevel, rightLevel) + 1  
        )  # calculate level of current node  
        while len(ans) <= level:  # create more space in ans if necessary  
            ans.append([])  
        ans[level].append(u.val)  
        return level  
  
    dfs(root)  
    print(ans)  
    return ans  
  
  
# Driver Code  
if __name__ == "__main__":  
  
   # Let us create binary tree shown in  
   # above diagram   root = Node(1)  
   root.left = Node(2)  
   root.right = Node(3)  
   root.left.left = Node(4)  
   root.right.left = Node(5)  
   root.right.right = Node(8)  
   root.right.left.left = Node(6)  
   root.right.left.right = Node(7)  
   root.right.right.left = Node(9)  
   root.right.right.right = Node(10)  
  
   printLeafNodes(root)

ip = [2,3,4,5,8,6,7,9,10]  op = [[4, 6, 7, 9, 10], [2, 5, 8], [3], [1]]
```