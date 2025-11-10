## 💡 The Code You Gave

```c
for (i = 0; i < n; i++)
    for (j = 0; j < n; j++)
        c[i][j] = 0.0;

for (i = 0; i < n; i++)
    for (j = 0; j < n; j++)
        for (k = 0; k < n; k++)
            c[i][j] = c[i][j] + a[i][k] * b[k][j];
```

This is a simple **matrix multiplication** program.

Let’s see what each part of the question means 👇

---

## 🧩 (i) What is “Translate into Three-Address Statements”?

A **Three Address Code (TAC)** is like a simpler version of your program that a compiler understands easily.

It breaks big expressions into small steps, each having **one operator and up to three operands** (like `x = y + z`).

---

### 🧮 For the first part (`c[i][j] = 0`)

This code:

```c
for (i=0; i<n; i++)
    for (j=0; j<n; j++)
        c[i][j] = 0.0;
```

becomes this in **three-address form**:

```
1. i = 0
2. if i >= n goto 10
3. j = 0
4. if j >= n goto 8
5. t1 = i * n + j          // position in matrix
6. c[t1] = 0.0
7. j = j + 1
8. goto 4
9. i = i + 1
10. goto 2
11. END
```

👉 Each step is simple — only one operation per line.

---

### 🧮 For the multiplication part

```c
for (i=0; i<n; i++)
    for (j=0; j<n; j++)
        for (k=0; k<n; k++)
            c[i][j] = c[i][j] + a[i][k] * b[k][j];
```

Now let’s break it into three-address form:

```
12. i = 0
13. if i >= n goto 30
14. j = 0
15. if j >= n goto 28
16. k = 0
17. if k >= n goto 26

18. t1 = i * n + j           // position for c[i][j]
19. t2 = i * n + k           // position for a[i][k]
20. t3 = k * n + j           // position for b[k][j]
21. t4 = a[t2] * b[t3]       // multiply
22. c[t1] = c[t1] + t4       // add to result
23. k = k + 1
24. goto 17

25. j = j + 1
26. goto 15

27. i = i + 1
28. goto 13
29. END
```

✅ This version shows exactly what the compiler does —
just small, easy-to-execute steps.

---

## 🧭 (ii) Construct the **Flow Graph**

Now that we have all the steps, we group them into **Basic Blocks**.

### 🔹 What’s a “Basic Block”?

A **Basic Block** is a group of statements that run one after another, with **no jumps** in between — only the end jumps to another place.

Think of it like a straight road between two turns 🚦

---

### ⚙️ Basic Blocks in Your Code

#### For initialization (`c[i][j]=0.0`)

| Block  | Contents                      |
| ------ | ----------------------------- |
| **B1** | `i=0`                         |
| **B2** | `if i>=n goto B6`             |
| **B3** | `j=0`                         |
| **B4** | `if j>=n goto B5`             |
| **B5** | `c[i][j]=0.0; j=j+1; goto B4` |
| **B6** | `i=i+1; goto B2`              |

#### For multiplication

| Block   | Contents                                                         |
| ------- | ---------------------------------------------------------------- |
| **B7**  | `i=0`                                                            |
| **B8**  | `if i>=n goto END`                                               |
| **B9**  | `j=0`                                                            |
| **B10** | `if j>=n goto B8`                                                |
| **B11** | `k=0`                                                            |
| **B12** | `if k>=n goto B9`                                                |
| **B13** | compute `c[i][j] = c[i][j] + a[i][k]*b[k][j]`; `k=k+1; goto B12` |
| **B14** | `j=j+1; goto B10`                                                |
| **B15** | `i=i+1; goto B8`                                                 |

---

### 🧭 Flow Graph (Simplified Visual)

```
        +-----+
        | B1  | i=0
        +--+--+
           |
           v
        +--+--+       +-----+
        | B2  | --->  | B6  |
        +--+--+       +-----+
           |false
           v
        +--+--+       +-----+
        | B3  | --->  | B4  |
        +--+--+       +-----+
           |false
           v
        +--+--+
        | B5  |
        +--+--+
           |
           v
          back to B4
```

(similar flow for the multiplication loops with deeper nesting)

---

## 🔁 (iii) Identify Loops in the Flow Graph

### There are **5 total loops** (3 main ones for multiplication + 2 for initialization):

| Loop   | Variables         | What it does                                   |
| ------ | ----------------- | ---------------------------------------------- |
| **L1** | `i` (outer init)  | Goes through each row of `c` to set it to zero |
| **L2** | `j` (inner init)  | Goes through each column of that row           |
| **L3** | `i` (outer mult)  | Outer loop for each row of result matrix       |
| **L4** | `j` (middle mult) | Each column of result matrix                   |
| **L5** | `k` (inner mult)  | Does the actual sum of products (dot product)  |

---

## 🧠 So, in short:

| Part      | Meaning                                                                                                     |
| --------- | ----------------------------------------------------------------------------------------------------------- |
| **(i)**   | We rewrite the code into step-by-step **Three Address Code** (simple machine-level steps).                  |
| **(ii)**  | We build a **Flow Graph**, showing how the program moves between loops and statements.                      |
| **(iii)** | We identify **loops** in that graph — i.e., which parts repeat (outer i-loop, middle j-loop, inner k-loop). |

---

### ✅ Final Summary (Exam-Ready Answer)

1. **TAC (Three Address Code):**

   * Breaks each loop and arithmetic operation into small steps with at most one operator.
   * Handles array indexing using `i*n + j`.

2. **Flow Graph:**

   * Shows control flow between basic blocks using arrows (edges).
   * Conditional jumps (`if`) create edges that make loops.

3. **Loops:**

   * Initialization loops (for `i` and `j`).
   * Multiplication loops (nested `i`, `j`, `k`).
   * Innermost loop (`k`) performs the actual multiplication and addition.

