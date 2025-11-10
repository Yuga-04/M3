Perfect 👍 You’ve shared a snapshot of a **blackboard explanation** for designing a **Turing Machine that adds two numbers in unary notation** — similar to what’s typically asked in 15-mark exam questions.

Here’s a **complete, clean, and structured 15-mark answer** written exactly in that academic style:

---

# ✳️ **Design a Turing Machine for Addition of Two Integers in Unary Notation**

---

## 🔹 **Aim**

To design a **Turing Machine (TM)** that performs the **addition of two non-negative integers** represented in **unary notation**.

---

## 🔹 **Representation**

In unary form:

* The number *n* is represented by *n* zeros (0’s).
* Two numbers are separated by a **single ‘1’** (used as a separator).

Example:
If
( a = 4 ) and ( b = 3 )
then the input on the tape is:

```
B 0 0 0 0 1 0 0 0 B
```

(Here B denotes the blank symbol.)

---

## 🔹 **Objective**

After the addition, the Turing Machine should **erase the separator (1)** and combine all zeros into a single block representing the sum.
Final output should be:

```
B 0 0 0 0 0 0 0 B
```

→ representing 7 in unary form.

---

## 🔹 **Turing Machine Description**

A Turing Machine is represented as:
[
M = (Q, Σ, Γ, δ, q_0, q_{accept})
]

### Components:

| Symbol                | Meaning                      |
| :-------------------- | :--------------------------- |
| **Q**                 | { q0, q1, q2, q3, q_accept } |
| **Σ (Input symbols)** | { 0, 1 }                     |
| **Γ (Tape symbols)**  | { 0, 1, B }                  |
| **q₀**                | Initial state                |
| **q_accept (q₃)**     | Final (halting) state        |
| **B**                 | Blank symbol                 |
| **δ**                 | Transition function          |

---

## 🔹 **Algorithm (Step-by-Step Explanation)**

1. **Start** in state `q0` on the leftmost blank (B).
   Move right to reach the first zero.

2. **In q0:**

   * Keep moving right through 0’s (of first number).
   * When the separator `1` is encountered, **replace it with B** (blank).
   * Move right and go to `q1`.

3. **In q1:**

   * Move right through all 0’s (of the second number).
   * When blank (B) is reached, write **B**, move left, and go to `q2`.

4. **In q2:**

   * Move left through all 0’s of the second number until a blank or erased symbol is found.
   * When B is found, move left and go to `q3`.

5. **In q3:**

   * Halt (Addition completed).
   * Now, both blocks of zeros are combined into one continuous block representing the sum.

---

## 🔹 **Transition Table**

| Current State | Read | Write | Move | Next State | Description                              |
| :-----------: | :--: | :---: | :--: | :--------: | :--------------------------------------- |
|       q0      |   0  |   0   |   R  |     q0     | Move through first number                |
|       q0      |   1  |   B   |   R  |     q1     | Erase separator and move to second block |
|       q1      |   0  |   0   |   R  |     q1     | Move through second number               |
|       q1      |   B  |   B   |   L  |     q2     | End of second number                     |
|       q2      |   0  |   0   |   L  |     q2     | Move left to reach beginning             |
|       q2      |   B  |   B   |   R  |     q3     | Move right and halt                      |
|       q3      |   —  |   —   |   —  |    HALT    | Machine stops                            |

---

## 🔹 **Example Trace**

**Input Tape:**

```
B 0 0 0 0 1 0 0 0 B
```

| Step | Tape Content |    Head   | State | Action          |
| :--: | :----------- | :-------: | :---: | :-------------- |
|   1  | B00001 000B  |    On 0   |   q0  | Move right      |
|   2  | B0000B000B   |    On 0   |   q1  | Erase separator |
|   3  | B0000B000B   | On last 0 |   q1  | Move right      |
|   4  | B0000B000B   |    On B   |   q2  | Move left       |
|   5  | B0000000B    |    On B   |   q3  | Halt            |

✅ **Final Tape:**

```
B 0 0 0 0 0 0 0 B
```

→ **Output = 7 (sum of 4 + 3)**

---

## 🔹 **State Diagram (Text Description)**

```
(q0) --0/R--> (q0)
(q0) --1→B/R--> (q1)
(q1) --0/R--> (q1)
(q1) --B/L--> (q2)
(q2) --0/L--> (q2)
(q2) --B/R--> (q3) [HALT]
```

---

## 🔹 **Result**

Thus, the designed **Turing Machine** successfully adds two non-negative integers represented in unary notation by replacing the separator and merging both sets of symbols.

---

## 🔹 **Conclusion**

This Turing Machine demonstrates how a simple computational model can perform **arithmetic operations** such as addition.
It clearly shows the power of Turing Machines to simulate basic arithmetic using only read, write, and move operations on a tape.

---

### 🟩 **Marks Distribution (15 Marks)**

| Section               |        Marks |
| --------------------- | -----------: |
| Aim & Representation  |            2 |
| Algorithm Explanation |            4 |
| Transition Table      |            4 |
| Example Trace         |            3 |
| Diagram & Conclusion  |            2 |
| **Total**             | **15 Marks** |

---

Would you like me to include a **drawn state diagram (like in the board image)** in PNG/PDF format for submission?
