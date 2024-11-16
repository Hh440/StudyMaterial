# Disk Scheduling Detailed Explanation

Disk scheduling is a process used by the operating system to determine the order in which disk I/O requests are processed. The **primary objective** is to minimize the time taken to process requests, especially the **seek time**, and to enhance the efficiency and performance of the system.

---

## 1. Key Factors in Disk Scheduling
1. **Seek Time:**  
   - The time it takes for the disk arm to move to the track containing the requested data.  
   - **Goal:** Minimize seek time as it is the most time-consuming operation.

2. **Rotational Latency:**  
   - The time taken for the disk platter to rotate and position the desired sector under the read/write head.  
   - Depends on the speed of the disk (measured in RPM).

3. **Transfer Time:**  
   - The time taken to transfer data after the head is positioned.  
   - Usually much shorter compared to seek time and rotational latency.

4. **Request Queue:**  
   - A queue of disk I/O requests that arrive from processes.  
   - Scheduling determines the order in which these requests are handled.

---

## 2. Why Disk Scheduling Is Needed
- Disk requests may arrive faster than they can be processed.
- Hard drives have moving mechanical parts, leading to delays.
- Proper scheduling can:
  - Reduce **average seek time**.
  - Increase system throughput.
  - Prevent certain requests from being starved (never processed).

---

## 3. Disk Scheduling Algorithms

### A. First Come First Serve (FCFS)
- **How It Works:**  
  Handles requests in the order they arrive in the queue.  
  No prioritization based on position or time required.

- **Advantages:**
  - Simple to implement.
  - Fair to all processes (no starvation).

- **Disadvantages:**
  - Long seek times due to random movement of the disk head.
  - Inefficient if requests are far apart.

- **Example:**
  - Request Queue: `[98, 183, 37, 122, 14, 124, 65, 67]`
  - Head starts at `53`.  
  - **Order of processing:**  
    `53 → 98 → 183 → 37 → 122 → 14 → 124 → 65 → 67`

---

### B. Shortest Seek Time First (SSTF)
- **How It Works:**  
  Picks the request closest to the current head position, reducing seek time for each step.

- **Advantages:**
  - Reduces overall seek time compared to FCFS.
  - Prioritizes proximity, which improves performance.

- **Disadvantages:**
  - **Starvation:** Requests far from the current head may be ignored for a long time.

- **Example:**
  - Request Queue: `[98, 183, 37, 122, 14, 124, 65, 67]`
  - Head starts at `53`.  
  - **Order of processing:**  
    `53 → 65 → 67 → 37 → 14 → 98 → 122 → 124 → 183`

---

### C. SCAN (Elevator Algorithm)
- **How It Works:**  
  The disk arm moves in one direction (up or down) servicing requests, then reverses direction when it reaches the end.

- **Advantages:**
  - Reduces seek time compared to FCFS.
  - Avoids starvation, as all requests in the current direction are handled.

- **Disadvantages:**
  - Long wait for requests at the end of the disk.

- **Example:**
  - Request Queue: `[98, 183, 37, 122, 14, 124, 65, 67]`
  - Head starts at `53`.  
  - Direction: **Up**.  
  - **Order of processing:**  
    `53 → 65 → 67 → 98 → 122 → 124 → 183 → (reverse) → 37 → 14`

---

### D. C-SCAN (Circular SCAN)
- **How It Works:**  
  Moves in one direction (up or down), servicing requests, but jumps back to the starting end without servicing in reverse.

- **Advantages:**
  - Provides more uniform wait times for requests.

- **Disadvantages:**
  - Can result in longer overall head movement.

- **Example:**
  - Request Queue: `[98, 183, 37, 122, 14, 124, 65, 67]`
  - Head starts at `53`.  
  - Direction: **Up**.  
  - **Order of processing:**  
    `53 → 65 → 67 → 98 → 122 → 124 → 183 → (jump to start) → 14 → 37`

---

### E. LOOK
- **How It Works:**  
  Similar to SCAN but stops at the last request in the current direction before reversing (doesn’t go to the disk edge).

- **Advantages:**
  - Reduces unnecessary movement compared to SCAN.
  - Efficient for real-world disk usage patterns.

- **Disadvantages:**
  - Slightly more complex than SCAN.

- **Example:**
  - Request Queue: `[98, 183, 37, 122, 14, 124, 65, 67]`
  - Head starts at `53`.  
  - Direction: **Up**.  
  - **Order of processing:**  
    `53 → 65 → 67 → 98 → 122 → 124 → 183 → (reverse) → 37 → 14`

---

### F. C-LOOK
- **How It Works:**  
  Similar to C-SCAN but stops at the last request in the current direction and jumps back to the starting end.

- **Advantages:**
  - Avoids unnecessary traversal to the disk edge.
  - More efficient than C-SCAN for certain workloads.

- **Disadvantages:**
  - May still involve longer seek times compared to LOOK.

- **Example:**
  - Request Queue: `[98, 183, 37, 122, 14, 124, 65, 67]`
  - Head starts at `53`.  
  - Direction: **Up**.  
  - **Order of processing:**  
    `53 → 65 → 67 → 98 → 122 → 124 → 183 → (jump to start) → 14 → 37`

---

## Comparison of Algorithms

| **Algorithm** | **Advantages**                      | **Disadvantages**                  | **Best For**                     |
|---------------|-------------------------------------|------------------------------------|----------------------------------|
| FCFS          | Simple, fair                       | High seek time                     | Small queues, low workload       |
| SSTF          | Low seek time                      | Starvation possible                | Systems prioritizing speed       |
| SCAN          | No starvation                      | Longer seek time for edge requests | High-load systems                |
| C-SCAN        | Uniform wait times                 | Longer movement                    | Systems with continuous requests |
| LOOK          | Reduced movement                   | May still cause delays             | Optimized, real-world usage      |
| C-LOOK        | Efficient movement, no starvation  | More complex than LOOK             | Systems with dynamic loads       |

---

