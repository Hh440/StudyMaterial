# Data Structures and Algorithm Complexities

## 1. Sorting Algorithms

| **Algorithm**      | **Best Case** | **Average Case** | **Worst Case** | **Space Complexity** | **Explanation** |
|--------------------|---------------|-------------------|----------------|-----------------------|-----------------|
| **Bubble Sort**    | O(n)          | O(n²)            | O(n²)         | O(1)                  | Inefficient due to repeated comparisons and swaps; best case is O(n) if already sorted. |
| **Selection Sort** | O(n²)         | O(n²)            | O(n²)         | O(1)                  | Finds the minimum element in each iteration and swaps; always O(n²) regardless of input. |
| **Insertion Sort** | O(n)          | O(n²)            | O(n²)         | O(1)                  | Efficient for small or partially sorted arrays, with best case O(n) for sorted data. |
| **Merge Sort**     | O(n log n)    | O(n log n)       | O(n log n)    | O(n)                  | A divide-and-conquer approach with O(n log n) in all cases; requires extra space for merging. |
| **Quick Sort**     | O(n log n)    | O(n log n)       | O(n²)         | O(log n) (average)    | Fast average case with O(n log n) but degrades to O(n²) if pivot choices are poor. |
| **Heap Sort**      | O(n log n)    | O(n log n)       | O(n log n)    | O(1)                  | Utilizes a binary heap for sorting without extra space requirements. |
| **Radix Sort**     | O(nk)         | O(nk)            | O(nk)         | O(n + k)              | Non-comparative sort, effective for integers; k is the number of digits. |

## 2. Search Algorithms

| **Algorithm**          | **Best Case** | **Average Case** | **Worst Case** | **Space Complexity** | **Explanation** |
|------------------------|---------------|-------------------|----------------|-----------------------|-----------------|
| **Linear Search**      | O(1)          | O(n)             | O(n)          | O(1)                  | Simple search that goes element by element; worst case is O(n). |
| **Binary Search**      | O(1)          | O(log n)         | O(log n)      | O(1)                  | Searches a sorted array by dividing it in half; requires sorted input. |
| **Interpolation Search** | O(1)       | O(log log n)     | O(n)          | O(1)                  | Works best for uniformly distributed data; worst case O(n) for skewed data. |
| **Jump Search**        | O(√n)        | O(√n)            | O(√n)         | O(1)                  | Divides array into blocks and performs linear search within blocks. |

## 3. Graph Algorithms

| **Algorithm**                | **Time Complexity** | **Space Complexity** | **Explanation** |
|------------------------------|---------------------|-----------------------|-----------------|
| **Breadth-First Search (BFS)** | O(V + E)         | O(V)                  | Explores all nodes layer-by-layer; ideal for shortest path in unweighted graphs. |
| **Depth-First Search (DFS)**   | O(V + E)         | O(V)                  | Explores as far as possible along each branch before backtracking. |
| **Dijkstra's Algorithm**       | O(E log V)       | O(V)                  | Finds the shortest path in weighted graphs without negative weights. |
| **Bellman-Ford Algorithm**     | O(V * E)         | O(V)                  | Calculates shortest path even with negative weights; slower than Dijkstra's. |
| **Floyd-Warshall Algorithm**   | O(V³)            | O(V²)                 | Computes shortest paths between all pairs of vertices. |
| **Prim's Algorithm**           | O(E log V)       | O(V)                  | Finds the minimum spanning tree in a weighted graph; greedy algorithm. |
| **Kruskal's Algorithm**        | O(E log E)       | O(V)                  | Also finds the minimum spanning tree using a greedy approach. |

## 4. Dynamic Programming Algorithms

| **Algorithm**                  | **Time Complexity** | **Space Complexity** | **Explanation** |
|--------------------------------|---------------------|-----------------------|-----------------|
| **Fibonacci Sequence (DP)**    | O(n)               | O(n)                  | Stores results of sub-problems to avoid redundant calculations. |
| **Longest Common Subsequence** | O(m * n)           | O(m * n)              | Uses DP to find the longest subsequence common to two sequences. |
| **Knapsack Problem (0/1)**     | O(n * W)           | O(n * W)              | Finds the maximum value subset of items within a weight limit W. |
| **Matrix Chain Multiplication** | O(n³)             | O(n²)                 | DP approach to find the most efficient way to multiply matrices. |
| **Edit Distance**              | O(m * n)           | O(m * n)              | Measures the minimum edits required to convert one string to another. |

## 5. Other Important Algorithms

| **Algorithm**                  | **Time Complexity** | **Space Complexity** | **Explanation** |
|--------------------------------|---------------------|-----------------------|-----------------|
| **Binary Exponentiation**      | O(log n)           | O(1)                  | Efficiently computes large powers by reducing the power by half each time. |
| **Euclidean Algorithm**        | O(log(min(a, b)))  | O(1)                  | Finds the greatest common divisor (GCD) of two numbers. |
| **KMP String Matching**        | O(m + n)           | O(m)                  | Searches for a pattern in a text with O(m + n) time, where m and n are lengths of pattern and text. |
| **Rabin-Karp String Matching** | O(m + n) average   | O(m + n)              | Uses hashing to search patterns with O(m + n) average time complexity. |
| **Fast Fourier Transform (FFT)** | O(n log n)       | O(n)                  | Converts a polynomial from time to frequency domain; key for convolution and signal processing. | 

---

## Explanation of Common Algorithm Concepts

- **Sorting Algorithms**: Used to order elements in a list or array. Algorithms like Bubble Sort and Quick Sort use different methods of swapping or partitioning to sort elements, varying in efficiency.
  
- **Search Algorithms**: Find specific items in data structures. Linear search is simple but inefficient; binary search is faster but requires sorted data.

- **Graph Algorithms**: Explore and analyze graphs. BFS and DFS traverse nodes differently; shortest path algorithms like Dijkstra’s and Bellman-Ford calculate distances in weighted graphs, and minimum spanning tree algorithms (Prim's and Kruskal’s) find the optimal tree structure.

- **Dynamic Programming Algorithms**: Solve complex problems by breaking them down into simpler sub-problems and reusing solutions. Examples include finding Fibonacci numbers, solving the knapsack problem, or calculating edit distances.

- **Other Important Algorithms**: Includes various techniques, such as binary exponentiation for fast power calculations and the Euclidean algorithm for finding GCD.


# Data Structure and Algorithm Complexities

| **Data Structure / Algorithm**                   | **Operation**    | **Average Time Complexity** | **Worst Case Time Complexity** | **Space Complexity** | **Explanation**                                                                                                                                           |
|--------------------------------------------------|------------------|-----------------------------|--------------------------------|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Array**                                        | Access          | O(1)                        | O(1)                           | O(n)                  | Arrays have constant-time access to any element using an index, but inserting/deleting requires shifting, leading to O(n) time.                           |
|                                                  | Search          | O(n)                        | O(n)                           |                       | Linear search is required as the array is unsorted, which takes O(n) time in the worst case.                                                               |
|                                                  | Insert/Delete   | O(n)                        | O(n)                           |                       | Insertions/deletions may require shifting elements, making them O(n).                                                                                     |
| **Linked List**                                  | Access          | O(n)                        | O(n)                           | O(n)                  | Accessing an element by position requires traversal from the head, leading to O(n) time.                                                                  |
|                                                  | Search          | O(n)                        | O(n)                           |                       | Searching requires traversal, making it O(n).                                                                                                             |
|                                                  | Insert/Delete   | O(1)                        | O(1)                           |                       | Inserting or deleting at the head or tail (if pointer is known) is O(1).                                                                                  |
| **Stack**                                        | Push/Pop        | O(1)                        | O(1)                           | O(n)                  | Stack operations (push and pop) work in constant time as they only add or remove from the top.                                                            |
| **Queue**                                        | Enqueue/Dequeue | O(1)                        | O(1)                           | O(n)                  | Queue operations (enqueue and dequeue) are constant-time as they only involve adding/removing from the ends.                                              |
| **Hash Table**                                   | Insert/Delete   | O(1)                        | O(n)                           | O(n)                  | In average cases, hash tables have O(1) time complexity, but collisions can lead to O(n) in the worst case.                                               |
|                                                  | Search          | O(1)                        | O(n)                           |                       | Searching is O(1) on average but can be O(n) with poor hashing and many collisions.                                                                       |
| **Binary Search Tree (BST)**                     | Insert/Delete   | O(log n)                    | O(n)                           | O(n)                  | Insertions/deletions in a balanced BST are O(log n), but O(n) in a skewed (unbalanced) tree.                                                              |
|                                                  | Search          | O(log n)                    | O(n)                           |                       | BST search is O(log n) on average but can degrade to O(n) if unbalanced.                                                                                  |
| **Balanced Binary Search Tree (e.g., AVL, Red-Black)** | Insert/Delete | O(log n)                    | O(log n)                       | O(n)                  | Self-balancing trees ensure that the height is always log n, making operations consistently O(log n).                                                    |
| **Graph Traversal (BFS, DFS)**                   | Traversal       | O(V + E)                    | O(V + E)                       | O(V + E)              | Traverses all nodes (V) and edges (E) in the graph, visiting each once.                                                                                   |
| **Binary Heap**                                  | Insert          | O(log n)                    | O(log n)                       | O(n)                  | Inserting a new element requires rearranging elements to maintain heap properties.                                                                        |
|                                                  | Delete (Min/Max)| O(log n)                    | O(log n)                       |                       | Deleting the root (min or max) requires rearranging elements to preserve heap structure.                                                                  |
| **Sorting Algorithms**                           | Bubble Sort     | O(n^2)                      | O(n^2)                         | O(1)                  | Simple but inefficient sorting algorithm with O(n^2) time complexity due to repeated comparisons and swaps.                                               |
|                                                  | Merge Sort      | O(n log n)                  | O(n log n)                     | O(n)                  | Divide-and-conquer sorting algorithm with O(n log n) time but requires extra space for merging.                                                           |
|                                                  | Quick Sort      | O(n log n)                  | O(n^2)                         | O(log n)              | Fast sorting with O(n log n) average time but O(n^2) worst-case if pivot is poorly chosen.                                                                |
|                                                  | Heap Sort       | O(n log n)                  | O(n log n)                     | O(1)                  | Sorting using a binary heap; no extra space required beyond the input array.                                                                              |

---

## Data Structure and Algorithm Definitions

1. **Array**: A collection of items stored at contiguous memory locations. Allows efficient indexing, but insertion/deletion is costly as elements may need shifting.

2. **Linked List**: A sequence of nodes where each node points to the next. Allows efficient insertion/deletion but requires O(n) for access/search since it doesn’t have indices.

3. **Stack**: A last-in, first-out (LIFO) data structure where the last element added is the first to be removed. Operations (push, pop) are constant time, O(1).

4. **Queue**: A first-in, first-out (FIFO) data structure where the first element added is the first to be removed. Enqueue and dequeue operations are O(1).

5. **Hash Table**: Uses a hash function to map keys
