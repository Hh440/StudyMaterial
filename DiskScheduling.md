# Disk Scheduling

Disk scheduling is the method an operating system uses to decide the order in which disk I/O requests are processed. The goal is to minimize seek time (time taken to move the disk's read/write head to the appropriate track) and improve overall system performance.

---

## Key Concepts

1. **Seek Time**: Time to move the disk arm to the required track.
2. **Rotational Latency**: Time to rotate the disk so the desired sector is under the read/write head.
3. **Data Transfer Time**: Time to transfer data once the head is positioned.
4. **I/O Queue**: Requests from programs/processes waiting for disk operations.

---

## Disk Scheduling Algorithms

### 1. First Come First Serve (FCFS)

- **How it works**: Handles requests in the order they arrive.
- **Advantages**: Simple and fair.
- **Disadvantages**: Inefficient; high average seek time.

**Example:**

- **Request Queue**: `[98, 183, 37, 122, 14, 124, 65, 67]`  
- **Starting Position**: `53`  
- **Order of Movement**: `53 → 98 → 183 → 37 → 122 → 14 → 124 → 65 → 67`

---

### 2. Shortest Seek Time First (SSTF)

- **How it works**: Picks the request closest to the current head position.
- **Advantages**: Reduces seek time compared to FCFS.
- **Disadvantages**: Can cause **starvation** for far requests.

**Example:**

- **Request Queue**: `[98, 183, 37, 122, 14, 124, 65, 67]`  
- **Starting Position**: `53`  
- **Order of Movement**: `53 → 65 → 67 → 37 → 14 → 98 → 122 → 124 → 183`

---

### 3. SCAN (Elevator Algorithm)

- **How it works**: Moves the head in one direction (up or down), servicing requests, and reverses direction only at the end of the disk.
- **Advantages**: Efficient for requests in both directions.
- **Disadvantages**: Long wait for requests at the extreme ends.

**Example:**

- **Request Queue**: `[98, 183, 37, 122, 14, 124, 65, 67]`  
- **Starting Position**: `53`  
- **Direction**: Up  
- **Order of Movement**: `53 → 65 → 67 → 98 → 122 → 124 → 183 → (reverse) → 37 → 14`

---

### 4. C-SCAN (Circular SCAN)

- **How it works**: Moves in one direction, services requests, and jumps to the opposite end of the disk without servicing in reverse.
- **Advantages**: Uniform wait time.
- **Disadvantages**: Longer travel distance compared to SCAN.

**Example:**

- **Request Queue**: `[98, 183, 37, 122, 14, 124, 65, 67]`  
- **Starting Position**: `53`  
- **Direction**: Up  
- **Order of Movement**: `53 → 65 → 67 → 98 → 122 → 124 → 183 → (jump to start) → 14 → 37`

---

### 5. LOOK

- **How it works**: Similar to SCAN but stops at the last request in the current direction instead of going to the edge of the disk.
- **Advantages**: Reduces unnecessary travel.
- **Disadvantages**: Can still cause uneven service times.

**Example:**

- **Request Queue**: `[98, 183, 37, 122, 14, 124, 65, 67]`  
- **Starting Position**: `53`  
- **Direction**: Up  
- **Order of Movement**: `53 → 65 → 67 → 98 → 122 → 124 → 183 → (reverse) → 37 → 14`

---

### 6. C-LOOK

- **How it works**: Like LOOK but jumps back to the beginning after the last request in the current direction.
- **Advantages**: More uniform wait time.
- **Disadvantages**: Longer travel distance compared to LOOK.

**Example:**

- **Request Queue**: `[98, 183, 37, 122, 14, 124, 65, 67]`  
- **Starting Position**: `53`  
- **Direction**: Up  
- **Order of Movement**: `53 → 65 → 67 → 98 → 122 → 124 → 183 → (jump to start) → 14 → 37`

---

## Comparison Table

| **Algorithm**      | **Seek Time** | **Fairness** | **Starvation** | **Efficiency** |
|---------------------|---------------|--------------|----------------|----------------|
| FCFS               | High          | High         | No             | Low            |
| SSTF               | Moderate      | Low          | Yes            | Moderate       |
| SCAN               | Moderate      | Moderate     | No             | High           |
| C-SCAN             | Moderate      | High         | No             | High           |
| LOOK               | Moderate      | High         | No             | High           |
| C-LOOK             | Moderate      | High         | No             | High           |

---

## Choosing the Right Algorithm

- **FCFS**: Use when fairness is critical and workload is low.
- **SSTF**: Best for reducing seek time with fewer requests.
- **SCAN/C-SCAN**: Suitable for systems with high and continuous loads.
- **LOOK/C-LOOK**: Use for optimized efficiency in multi-user systems.

---
