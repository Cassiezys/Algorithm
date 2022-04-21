二叉树+ DFS

```python
all_path = []
path = []

def dfs(root):
  if not root: return
  path.append(root.val)
  if not root.left and not root.right:
    all_path.append(path[:])
  dfs(root.left)
  dfs(root.right)
  path.pop()

  
```

二叉树+BFS

```python
all_path = []
parent = collections.defaultdict(lambda:None)

def getPath(node):
  tmp = []
  while node:
    tmp.append(node.val)
    node = parent[node]
   ret.append(tmp[::-1])

if not root: return all_path

que_node = collections.deque([root])

while que_node:
  node = que_node.popleft()
  
  if not node.left and not node.right:
    getPath(node)
  else:
    if node.left:
      parent[node.left] = node
      que_node.append(node.left)
    if node.right:
      parent[node.right] = node
      que_node.append(node.right)

return all_path
      
```

二叉树：中序遍历用stack实现：

```python
stack = []
while stack and root:
  while root:
    stack.append(root)
    root = root.left
  root = stack.pop()
  # operation
  root = root.right
```

