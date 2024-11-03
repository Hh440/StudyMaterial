# Unix and Process Management Questions

## Question 1
Which statement is not correct about the “init” process in Unix?
- It is generally the parent of the login shell.
- It has PID 1.
- It is the first process in the system.
- Init forks and execs a ‘getty’ process at every port connected to a terminal.

**Discussion**: The statement that is not correct is "It is generally the parent of the login shell." The init process is the ancestor of all processes, but it does not directly parent the login shell; instead, it spawns the login process which then spawns the login shell.

---

## Question 2
What does the following command do? `grep -vn "abc" x`
- a) It will print all of the lines in the file x that match the search string “abc”.
- b) It will print all of the lines in file x that do not match the search string “abc”.
- c) It will print the total number of lines in the file x that match the string “abc”.
- d) It will print the specific line numbers of the file x in which there is a match for string “abc”.

**Answer**: b) It will print all of the lines in file x that do not match the search string “abc”.

---

## Question 3
The Unix Kernel maintains two key data structures related to processes, the process table and the user structure. Which of the following information is not part of the user structure?
- a) File descriptor table
- b) System call state
- c) Scheduling parameters
- d) Kernel stack

**Answer**: d) Scheduling parameters

---

## Question 4
A Unix file may be of the type:
- a) Regular file
- b) Directory file
- c) Device file
- d) Any one of the above

**Answer**: d) Any one of the above

---

## Question 5
Which of the following UNIX commands allows scheduling a program to be executed at the specified time?
- a) cron
- b) nice
- c) date and time
- d) schedule

**Answer**: a) cron

---

## Question 6
In which of the following four necessary conditions for deadlock do processes claim exclusive control of the resources they require?
- a) no preemption
- b) mutual exclusion
- c) circular wait
- d) hold and wait

**Answer**: b) mutual exclusion

---

## Question 7
Consider a system having "n" resources of the same type. These resources are shared by 3 processes, A, B, C. These have peak demands of 3, 4, and 6 respectively. For what value of "n" will deadlock not occur?
- a) 15
- b) 9
- c) 10
- d) 11

**Answer**: d) 11

---

## Question 8
Consider the following process and resource requirement of each process.

| Process | Type 1 Used | Type 1 Max | Type 2 Used | Type 2 Max |
|---------|--------------|-------------|--------------|-------------|
| P1      | 1            | 2           | 1            | 3           |
| P2      | 1            | 3           | 1            | 2           |
| P3      | 2            | 4           | 1            | 4           |

Predict the state of this system, assuming that there are a total of 5 instances of resource type 1 and 4 instances of resource type 2.
- a) Can go to safe or unsafe state based on sequence
- b) Safe state
- c) Unsafe state
- d) Deadlock state

**Answer**: c) Unsafe state

---

## Question 9
Suppose n processes, P1, …. Pn share m identical resource units, which can be reserved and released one at a time. The maximum resource requirement of process Pi is Si, where Si > 0. Which one of the following is a sufficient condition for ensuring that deadlock does not occur?

- A
- B
- C
- D

**Answer**: c) C

---

## Question 10
Consider the following snapshot of a system running n processes. Process i is holding Xi instances of a resource R, where 1 <= i <= n. Currently, all instances of R are occupied. Further, for all i, process i has placed a request for an additional Yi instances while holding the Xi instances it already has. There are exactly two processes p and q such that Yp = Yq = 0. Which one of the following can serve as a necessary condition to guarantee that the system is not approaching a deadlock?
- min (Xp, Xq) < max (Yk) where k != p and k != q
- Xp + Xq >= min (Yk) where k != p and k != q
- max (Xp, Xq) > 1
- min (Xp, Xq) > 1

**Answer**: b) Xp + Xq >= min (Yk) where k != p and k != q