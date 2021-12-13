# class 15

## <ins>*Trees*

_A Binary Tree_ is a non-linear data structure that is used for searching and data organization. A binary tree is comprised of nodes. Each node being a data component, one a left child and the other the right child. 

### A binary tree node consists of the following components:

- Data
- Pointer to Left Child
- Pointer to Right Child

### key Terminologies 

- __Node__ – The most elementary unit of a binary tree.
- __Root__ – The root of a binary is the topmost element. There is only one root in a binary tree.
- __Leaf__ – The leaves of a binary tree are the nodes which have no children.
- __Level__ – The level is the generation of the respective node. The root has level 0, the children of the root node is at level 1, the grandchildren of the root node is at level 2 and so on.
- __Parent__ – The parent of a node is the node that is one level upward of the node.
- __Child__ – The children of a node are the nodes that are one level downward of the node.

### Implementation 

```py
# defining the structure
class Node:
    # Initializing the attributes
    def __init__(self, data):
        self.data = data # Node Data
        self.left = None # Left Child
        self.right = None # Right Child
        

```

### Instantiate a Tree 

```py

root = Node(10)

#        10
#      /    \
#    None   None
root.left = Node(34) 
root.right = Node(89)

#        10
#      /   \
#    34     59
#    /       \
#  None     None

```