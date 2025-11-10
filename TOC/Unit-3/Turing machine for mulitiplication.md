Perfect 👍 Yuga!
You’ve uploaded a whiteboard showing the **Turing Machine for Multiplication of Two Unary Numbers** — the exact type of 15-mark question that appears in *Theory of Computation (TOC)* or *Compiler Design* exams.

Here’s the **complete 15-mark written theory answer**, formatted exactly like a board/exam explanation with full marks clarity.

---

# ✳️ **Design a Turing Machine for Multiplication of Two Unary Numbers**

---

## 🔹 **Aim**

To design a **Turing Machine (TM)** that multiplies two non-negative integers represented in **unary notation**.

---

## 🔹 **Representation**

In unary form:

* Each number is represented by a sequence of **1’s**.
* The two numbers are **separated by a single 0** (used as a separator).
* The input tape begins and ends with **blank (B)** symbols.

Example:
Let
( x = 2 ), ( y = 3 )
then input on the tape is:

```
B 1 1 0 1 1 1 B
```

Expected Output:

```
B 1 1 1 1 1 1 B
```

→ representing ( 2 × 3 = 6 ).

---

## 🔹 **Idea Behind the Algorithm**

Multiplication in unary can be viewed as **repeated addition**.
That means:

[
x × y = y + y + y + ... \text{(x times)}
]

So the TM:

1. Reads each `1` from the first number (x).
2. For every such `1`, it **copies** the entire second block of 1’s to the end.
3. Repeats until all 1’s of the first number are processed.
4. Finally, erases extra markers and halts.

---

## 🔹 **Turing Machine Description**

Formally,
[
M = (Q, Σ, Γ, δ, q_0, q_{accept})
]

### Components

| Symbol            | Meaning                                      |
| :---------------- | :------------------------------------------- |
| **Q**             | { q0, q1, q2, q3, q4, q5, q6, q7, q_accept } |
| **Σ**             | { 1, 0 }                                     |
| **Γ**             | { 1, 0, X, B } where X = mark symbol         |
| **q₀**            | Initial state                                |
| **q_accept (q7)** | Halting state                                |
| **B**             | Blank symbol                                 |

---

## 🔹 **Algorithm (Step-by-Step)**

1. **Start (q0):**
   Scan the first block of 1’s.

   * Replace the first 1 with **B** to mark it as processed.
   * Move right to find the separator (0).

2. **Move to q1:**
   Skip all remaining 1’s of the first number and reach the separator (0).
   Move one cell right to reach the start of the second number.

3. **q2–q4:**
   For each 1 in the second number, move to the end of the tape and write an extra 1 (i.e., copy the second number).
   Then return left to the start of the second number.

4. **q5–q6:**
   After all 1’s in the second number are copied, go back to find another unmarked 1 in the first number and repeat.

5. **q7 (Halt):**
   When all 1’s of the first number are processed (i.e., replaced with B’s), remove the separator (0) and halt with the final result on the tape.

---

## 🔹 **Transition Table (Simplified)**

| Current State | Read | Write | Move | Next State | Description          |
| :-----------: | :--: | :---: | :--: | :--------: | :------------------- |
|       q0      |   1  |   B   |   R  |     q1     | Mark first 1 of x    |
|       q1      |   1  |   1   |   R  |     q1     | Skip remaining 1’s   |
|       q1      |   0  |   0   |   R  |     q2     | Move to y part       |
|       q2      |   1  |   X   |   R  |     q3     | Mark 1 of y for copy |
|       q3      |   1  |   1   |   R  |     q3     | Move to end of tape  |
|       q3      |   B  |   1   |   L  |     q4     | Write copy of y      |
|       q4      |   1  |   1   |   L  |     q4     | Return left          |
|       q4      |   X  |   1   |   R  |     q2     | Next y copy          |
|       q2      |   0  |   0   |   L  |     q5     | One x processed      |
|       q5      |   B  |   B   |   R  |     q0     | Go for next 1 of x   |
|       q0      |   0  |   B   |   R  |     q7     | Halt (All done)      |

---

## 🔹 **Example Trace**

**Input Tape:**

```
B 1 1 0 1 1 1 B
```

| Step | Tape Content          | State | Head Action         |
| :--: | :-------------------- | :---: | :------------------ |
|   1  | B B 1 0 1 1 1 B       |   q1  | Marked first 1 of x |
|   2  | B B 1 0 1 X 1 1 1 B   |   q3  | Copying y           |
|   3  | B B 1 0 1 1 1 1 1 1 B |   q4  | Added one copy      |
|   4  | B B B 0 1 1 1 1 1 1 B |   q0  | Second x processed  |
|   5  | B 1 1 1 1 1 1 B       |   q7  | Halt                |

✅ **Output:**

```
B 1 1 1 1 1 1 B
```

→ ( 2 × 3 = 6 )

---

## 🔹 **State Diagram (Text Description)**

```
(q0) --1→B/R--> (q1)
(q1) --0/R--> (q2)
(q2) --1→X/R--> (q3)
(q3) --B→1/L--> (q4)
(q4) --X→1/R--> (q2)
(q2) --0/L--> (q5)
(q5) --B/R--> (q0)
(q0) --0→B/R--> (q7 HALT)
```

---

## 🔹 **Result**

The Turing Machine successfully multiplies two unary numbers ( x ) and ( y ) by performing **repeated addition**.
The result is represented as a sequence of 1’s equal to ( x × y ).

---

## 🔹 **Conclusion**

A Turing Machine can perform arithmetic operations such as **addition and multiplication** using only basic read–write–move operations.
This multiplication TM demonstrates the **power of Turing computation**, showing that even simple instructions can express complex operations.

---

### 🟩 **Marks Distribution (15 Marks)**

| Section               |        Marks |
| :-------------------- | -----------: |
| Aim & Representation  |            2 |
| Algorithm Explanation |            4 |
| Transition Table      |            4 |
| Example Trace         |            3 |
| Diagram / Conclusion  |            2 |
| **Total**             | **15 Marks** |

---

Would you like me to include the **state diagram (same as your board)** neatly redrawn as an image or LaTeX diagram for your PDF/notes?
