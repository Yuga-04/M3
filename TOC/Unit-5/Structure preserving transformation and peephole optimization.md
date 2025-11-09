## **1️⃣ Structure-Preserving Transformations**

**Definition:**
Structure-preserving transformations are **local optimizations** applied on a **basic block** without changing the order or meaning of computations. These transformations **preserve the structure** of the program while improving its **efficiency**.

### **Main Types of Structure-Preserving Transformations:**

1. **Common Subexpression Elimination**

   * If an expression like `b + c` is computed multiple times, it is evaluated once and reused.
     **Example:**

   ```
   a = b + c  
   d = b + c  
   ```

   becomes

   ```
   a = b + c  
   d = a
   ```

   ➜ Avoids redundant computation.

2. **Dead-Code Elimination**

   * Statements whose results are **never used later** can be safely removed.
     **Example:**

   ```
   x = y + z;   // if x is never used later
   ```

   ➜ Remove this statement to save time and space.

3. **Renaming of Temporary Variables**

   * Temporary variables can be renamed to improve clarity or reuse registers.
     **Example:**

   ```
   t1 = b + c  
   ```

   can be changed to

   ```
   u1 = b + c
   ```

   ➜ Creates a **normal-form block**.

4. **Interchange of Independent Statements**

   * Two statements can be interchanged if they **do not depend** on each other.
     **Example:**

   ```
   t1 = b + c  
   t2 = x + y  
   ```

   can be swapped safely if no dependency exists.

✅ **Result:** Simplifies code, reduces redundancy, and improves execution speed without changing the logic.

---

## **2️⃣ Peephole Optimization**

**Definition:**
Peephole optimization is a **local optimization technique** that improves the **target code** by examining a **small window (peephole)** of consecutive instructions and replacing inefficient sequences with better ones.

### **Characteristics:**

* Applied on **target machine code or assembly code**.
* Works through a **sliding window** of a few instructions.
* Each replacement can lead to new optimization opportunities.

---

### **Types of Peephole Optimizations:**

1. **Redundant Instruction Elimination**
   Removes unnecessary loads, stores, or moves.
   **Example:**

   ```
   MOV R0, a  
   MOV a, R0
   ```

   ➜ The second instruction is redundant and can be deleted.

2. **Flow-of-Control Optimization**
   Removes unnecessary or chained jumps.
   **Example:**

   ```
   goto L1  
   L1: goto L2
   ```

   ➜ Simplify to `goto L2`.

3. **Algebraic Simplification**
   Replaces expressions with simpler equivalents.
   **Examples:**

   ```
   x = x + 0   → eliminate  
   x = x * 1   → eliminate
   ```

4. **Unreachable Code Elimination**
   Removes code that will **never execute**.
   **Example:**
   Code following an **unconditional jump** or false condition.

5. **Use of Machine Idioms**
   Replaces generic code with **efficient machine-specific instructions**.
   **Example:**

   ```
   i = i + 1  → INC i  
   i = i - 1  → DEC i
   ```

---

✅ **Advantages of Peephole Optimization:**

* Reduces code size and execution time.
* Simplifies the final machine code.
* Easy to implement and effective even on small programs.

wer (Summary for 15 Marks):**
Structure-preserving transformations optimize **basic blocks** by eliminating redundancies and dead code without altering program structure, while **peephole optimization** focuses on improving small sequences of **target instructions** by removing inefficiencies and simplifying operations — both improving overall **code efficiency** and **execution speed**.
