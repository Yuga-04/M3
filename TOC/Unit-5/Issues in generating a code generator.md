### **1. Input to Code Generator**

* **Input:** Intermediate representation (IR) of the source program + symbol table info for run-time addresses.
* **Types of IR:**
  a. Linear (postfix notation)
  b. Three-address code (quadruples)
  c. Virtual machine (stack machine code)
  d. Graphical (syntax trees, DAGs)
* **Note:** The front end performs scanning, parsing, and type checking. Hence, input to the code generator is **error-free**.

---

### **2. Target Program**

* **Output:** The generated **target program**, which may be:
  a. **Absolute machine code** – Executable directly in fixed memory.
  b. **Relocatable code** – Allows separate compilation of subprograms.
  c. **Assembly code** – Easier for debugging and code generation.

---

### **3. Memory Management**

* **Task:** Map source program names to memory addresses at run-time using the **symbol table**.
* **Labels & Addresses:**

  * Example: `j : goto i`

    * If *i < j*: backward jump to instruction i.
    * If *i > j*: forward jump; address filled later when i is processed.

---

### **4. Instruction Selection**

* **Goal:** Choose efficient instructions for the **target machine**.
* **Factors:**

  * Completeness and uniformity of instruction set.
  * Speed and size optimization.
  * Machine idioms and instruction efficiency affect code quality.

---

### **5. Register Allocation**

* **Importance:** Register operands are faster and shorter than memory operands.
* **Two Subproblems:**

  * **Register allocation:** Decide which variables reside in registers.
  * **Register assignment:** Assign specific registers to variables.
* **Example:**
  For division instruction `D x, y`:

  * *x* in even register (dividend)
  * *y* divisor
  * Even register → remainder, Odd register → quotient

---

### **6. Evaluation Order**

* **Definition:** Order of performing computations.
* **Impact:** Affects register usage and execution speed.
* **Goal:** Choose an order requiring minimum registers and yielding efficient target code.

