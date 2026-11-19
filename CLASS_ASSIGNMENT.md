
# Operating System Assignment

## Exercise 1: Preemptive Priority vs. Round Robin (RR)

### I. Preemptive Priority Scheduling

✍️ **Gantt Chart:**

```text
| P1 |   P2   |   P4   |    P1    | P3 | P5 |
0    1        5       10         17   19   22
```

✍️ **Calculation Table:**

| Process | AT | BT | CT | TAT = CT − AT | WT = TAT − BT |
|:--:|--:|--:|--:|--:|--:|
| P1 | 0 | 8 | 17 | 17 | 9 |
| P2 | 1 | 4 | 5 | 4 | 0 |
| P3 | 2 | 2 | 19 | 17 | 15 |
| P4 | 3 | 5 | 10 | 7 | 2 |
| P5 | 4 | 3 | 22 | 18 | 15 |
| **Total** | | | | **63** | **41** |

✍️ **Average Turnaround Time:**

\[
ATAT = \frac{63}{5} = 12.6\ ms
\]

✍️ **Average Waiting Time:**

\[
AWT = \frac{41}{5} = 8.2\ ms
\]

### II. Round Robin Scheduling (Time Quantum = 2 ms)

✍️ **Gantt Chart:**

```text
| P1 | P2 | P3 | P1 | P4 | P5 | P2 | P1 | P4 |P5| P1 | P4 |
0    2    4    6    8   10   12   14   16   18 19   21   22
```

✍️ **Calculation Table:**

| Process | AT | BT | CT | TAT = CT − AT | WT = TAT − BT |
|:--:|--:|--:|--:|--:|--:|
| P1 | 0 | 8 | 21 | 21 | 13 |
| P2 | 1 | 4 | 14 | 13 | 9 |
| P3 | 2 | 2 | 6 | 4 | 2 |
| P4 | 3 | 5 | 22 | 19 | 14 |
| P5 | 4 | 3 | 19 | 15 | 12 |
| **Total** | | | | **72** | **50** |

✍️ **Average Turnaround Time:**

\[
ATAT = \frac{72}{5} = 14.4\ ms
\]

✍️ **Average Waiting Time:**

\[
AWT = \frac{50}{5} = 10\ ms
\]

### III. Comparison

✍️ **Comparison Table:**

| Algorithm | Average TAT | Average WT |
|:--|--:|--:|
| Preemptive Priority | **12.6 ms** | **8.2 ms** |
| Round Robin | 14.4 ms | 10 ms |

✍️ **Result:**

Preemptive Priority Scheduling performs better because it has lower average turnaround time and waiting time than Round Robin.

---

## Exercise 2: SJF vs. SRTF

### I. Non-Preemptive Shortest Job First (SJF)

✍️ **Gantt Chart:**

```text
|      A      | D |   C   |   B   |    E    |
0            10   11     14      18        23
```

✍️ **Calculation Table:**

| Process | AT | BT | First ST | CT | TAT | WT | RT |
|:--:|--:|--:|--:|--:|--:|--:|--:|
| A | 0 | 10 | 0 | 10 | 10 | 0 | 0 |
| B | 2 | 4 | 14 | 18 | 16 | 12 | 12 |
| C | 4 | 3 | 11 | 14 | 10 | 7 | 7 |
| D | 5 | 1 | 10 | 11 | 6 | 5 | 5 |
| E | 8 | 5 | 18 | 23 | 15 | 10 | 10 |
| **Total** | | | | | **57** | **34** | **34** |

✍️ **Average Turnaround Time:**

\[
ATAT = \frac{57}{5} = 11.4\ ms
\]

✍️ **Average Waiting Time:**

\[
AWT = \frac{34}{5} = 6.8\ ms
\]

✍️ **Average Response Time:**

\[
ART = \frac{34}{5} = 6.8\ ms
\]

### II. Preemptive Shortest Remaining Time First (SRTF)

✍️ **Gantt Chart:**

```text
| A |   B   | D |   C   |   E   |       A       |
0   2       6   7      10      15              23
```

✍️ **Calculation Table:**

| Process | AT | BT | First ST | CT | TAT | WT | RT |
|:--:|--:|--:|--:|--:|--:|--:|--:|
| A | 0 | 10 | 0 | 23 | 23 | 13 | 0 |
| B | 2 | 4 | 2 | 6 | 4 | 0 | 0 |
| C | 4 | 3 | 7 | 10 | 6 | 3 | 3 |
| D | 5 | 1 | 6 | 7 | 2 | 1 | 1 |
| E | 8 | 5 | 10 | 15 | 7 | 2 | 2 |
| **Total** | | | | | **42** | **19** | **6** |

✍️ **Average Turnaround Time:**

\[
ATAT = \frac{42}{5} = 8.4\ ms
\]

✍️ **Average Waiting Time:**

\[
AWT = \frac{19}{5} = 3.8\ ms
\]

✍️ **Average Response Time:**

\[
ART = \frac{6}{5} = 1.2\ ms
\]

### III. Comparison

✍️ **Comparison Table:**

| Algorithm | Average Response Time |
|:--|--:|
| Non-Preemptive SJF | 6.8 ms |
| Preemptive SRTF | **1.2 ms** |

✍️ **Result:**

SRTF minimizes the average response time because its average response time (1.2 ms) is lower than SJF (6.8 ms).

---

## Exercise 3: FCFS vs. C-SCAN

### I. First-Come, First-Served (FCFS)

✍️ **Head Path:**

```text
53 → 98 → 183 → 37 → 122 → 14 → 124 → 65 → 67
```

✍️ **Head Movement Calculation:**

| Movement | Cylinders |
|:--|--:|
| 53 → 98 | 45 |
| 98 → 183 | 85 |
| 183 → 37 | 146 |
| 37 → 122 | 85 |
| 122 → 14 | 108 |
| 14 → 124 | 110 |
| 124 → 65 | 59 |
| 65 → 67 | 2 |
| **Total** | **640** |

✍️ **Total Seek Time:**

\[
640 \times 2 = 1280\ ms
\]

### II. SCAN (Moving Towards 0 First)

✍️ **Head Path:**

```text
53 → 37 → 14 → 0 → 65 → 67 → 98 → 122 → 124 → 183
```

✍️ **Total Head Movement:**

\[
(53-0) + (183-0)
\]

\[
= 53 + 183 = 236\ cylinders
\]

✍️ **Total Seek Time:**

\[
236 \times 2 = 472\ ms
\]

### III. Comparison

✍️ **Comparison Table:**

| Algorithm | Total Head Movement | Total Seek Time |
|:--|--:|--:|
| FCFS | 640 cylinders | 1280 ms |
| SCAN | **236 cylinders** | **472 ms** |

✍️ **Result:**

SCAN provides better performance because it requires less head movement and seek time than FCFS.

**Note:** The exercise title mentions C-SCAN, but Task II explicitly asks for SCAN with the head moving towards cylinder 0 first. Therefore, the solution follows Task II.

---

## Exercise 4: FCFS vs. SSTF

### I. First-Come, First-Served (FCFS)

✍️ **Head Path:**

```text
1800 → 2100 → 750 → 3200 → 1450 → 900 → 2300 → 150
```

✍️ **Head Movement Calculation:**

| Movement | Cylinders |
|:--|--:|
| 1800 → 2100 | 300 |
| 2100 → 750 | 1350 |
| 750 → 3200 | 2450 |
| 3200 → 1450 | 1750 |
| 1450 → 900 | 550 |
| 900 → 2300 | 1400 |
| 2300 → 150 | 2150 |
| **Total** | **9950** |

✍️ **Total Seek Time:**

\[
9950 \times 0.5 = 4975\ ms
\]

### II. Shortest Seek Time First (SSTF)

✍️ **Head Path:**

```text
1800 → 2100 → 2300 → 1450 → 900 → 750 → 150 → 3200
```

✍️ **Head Movement Calculation:**

| Movement | Cylinders |
|:--|--:|
| 1800 → 2100 | 300 |
| 2100 → 2300 | 200 |
| 2300 → 1450 | 850 |
| 1450 → 900 | 550 |
| 900 → 750 | 150 |
| 750 → 150 | 600 |
| 150 → 3200 | 3050 |
| **Total** | **5700** |

✍️ **Total Seek Time:**

\[
5700 \times 0.5 = 2850\ ms
\]

### III. Comparison

✍️ **Comparison Table:**

| Algorithm | Total Head Movement | Total Seek Time |
|:--|--:|--:|
| FCFS | 9950 cylinders | 4975 ms |
| SSTF | **5700 cylinders** | **2850 ms** |

✍️ **Result:**

SSTF provides better access time because it has less total head movement and seek time than FCFS.
