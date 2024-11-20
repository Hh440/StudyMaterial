# Tree Data Structures and Their Complexities

## Tree Basics
A **tree** is a hierarchical data structure composed of **nodes**, where each node has a **value** and may have child nodes. The topmost node is called the **root**.

---

## Important Tree Metrics

1. **Height of a Tree**  
   - The height of a tree is the **longest path from the root to any leaf**.
   - Formula:  
     - For a single node tree: `Height = 0`  
     - For a tree with multiple nodes:  
       ```
       Height = 1 + max(Height of each subtree)
       ```

2. **Depth of a Node**  
   - The depth of a node is the **number of edges from the root to the node**.
   - Depth of the root = `0`.

3. **Level of a Node**  
   - The level of a node is **depth + 1**.

4. **Min Height (Minimum Depth)**  
   - The shortest path from the root to any leaf node.

5. **Number of Nodes**  
   - The total count of nodes in the tree.  
   - Formula for a binary tree with height `h`:  
     ```
     Max Nodes = 2^(h+1) - 1
     Min Nodes (Complete Tree) = h + 1
     ```

6. **Number of Leaves**  
   - The number of nodes with no children (leaf nodes).  
   - Formula for a full binary tree:  
     ```
     Leaves = 2^h
     ```

---

## Types of Trees

### 1. General Tree
- **Definition**: A tree where each node can have any number of children.

### 2. Binary Tree
- **Definition**: Each node has at most **two children**.
- **Subtypes**:
  - **Full Binary Tree**: Every node has 0 or 2 children.
  - **Complete Binary Tree**: All levels are completely filled except the last, which is filled from left to right.
  - **Perfect Binary Tree**: All internal nodes have 2 children, and all leaves are at the same level.
  - **Skewed Tree**: A tree where all nodes have only one child.

### 3. Binary Search Tree (BST)
- **Definition**: A binary tree with the property:  
Left child < Parent < Right child


### 4. AVL Tree
- **Definition**: A self-balancing binary search tree.  
- **Balance Factor**: Height difference of left and right subtrees is at most `-1, 0, or 1`.

### 5. Red-Black Tree
- **Definition**: A self-balancing BST with color rules:
- Every node is either red or black.
- The root is always black.
- No two consecutive red nodes exist.

### 6. Trie (Prefix Tree)
- **Definition**: A tree used for storing strings where nodes represent prefixes.

---

## Common Operations and Complexities

| **Tree Type**        | **Insertion**     | **Deletion**      | **Search**        | **Traversal**     |
|-----------------------|-------------------|-------------------|-------------------|-------------------|
| General Tree          | `O(1)`           | `O(n)`            | `O(n)`            | `O(n)`            |
| Binary Tree           | `O(n)`           | `O(n)`            | `O(n)`            | `O(n)`            |
| Full Binary Tree      | `O(log n)`       | `O(log n)`        | `O(log n)`        | `O(n)`            |
| Perfect Binary Tree   | `O(log n)`       | `O(log n)`        | `O(log n)`        | `O(n)`            |
| Complete Binary Tree  | `O(log n)`       | `O(log n)`        | `O(log n)`        | `O(n)`            |
| Skewed Binary Tree    | `O(n)`           | `O(n)`            | `O(n)`            | `O(n)`            |
| Binary Search Tree    | `O(h)`           | `O(h)`            | `O(h)`            | `O(n)`            |
| AVL Tree              | `O(log n)`       | `O(log n)`        | `O(log n)`        | `O(n)`            |
| Red-Black Tree        | `O(log n)`       | `O(log n)`        | `O(log n)`        | `O(n)`            |
| Trie                  | `O(L)`           | `O(L)`            | `O(L)`            | `O(n * L)`        |

---

## Applications of Trees

- **File Systems**: Represent hierarchical structures.  
- **Databases**: Indexing (e.g., B-Trees, B+ Trees).  
- **Networking**: Routing algorithms.  
- **AI**: Decision trees, game trees.  
- **Compression**: Huffman Encoding.  
- **Range Queries**: Segment Trees, Fenwick Trees.

---

**Let me know if you'd like any further clarification or additions!**
