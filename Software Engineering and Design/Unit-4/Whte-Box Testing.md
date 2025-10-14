

## **WHITE-BOX TESTING (15 Marks)**

**Definition:**
White-box testing (also called *glass-box testing*) uses the **internal control structure** of software to design test cases. It ensures that:

1. All **independent paths** are executed at least once.
2. All **logical decisions** are tested for true and false outcomes.
3. All **loops** are executed within their limits.
4. **Internal data structures** are validated.

---

### **BASIS PATH TESTING**

Proposed by **Tom McCabe**, it measures the **logical complexity** of a program using **flow graphs** and defines a **basis set of independent paths**.
Each test case executes one path, ensuring every statement runs at least once.

**Flow Graph:** Represents control flow using **nodes (statements)** and **edges (control links)**.

**Cyclomatic Complexity (V(G))** gives the number of independent paths:

1. Number of regions in the flow graph.
2. **V(G) = E - N + 2** (E = edges, N = nodes).
3. **V(G) = P + 1** (P = predicate nodes).
   It gives the **upper bound** of required test cases.

**Steps:**

1. Draw flow graph.
2. Compute cyclomatic complexity.
3. Identify independent paths.
4. Design test cases to execute each path.

**Graph Matrix:**
Tabular form of flow graph; helps automate test generation. **Link weights** (1 or 0) may represent connection, probability, or time.

---

### **CONTROL STRUCTURE TESTING**

Includes other white-box techniques that enhance coverage:

#### **1. Condition Testing**

Tests all **logical and relational conditions**.
Detects **Boolean, relational, and operator errors**.
Conditions may be simple or compound using **AND, OR, NOT**.

#### **2. Data Flow Testing**

Based on **variable definitions (DEF)** and **uses (USE)**.
Ensures every **Definition-Use (DU) chain** [X, S, S’] is covered.
Detects variable misuse and data dependency errors.

#### **3. Loop Testing**

Validates **loop constructs** (simple, nested, concatenated, unstructured).

**Simple Loops:**

* Skip loop
* One pass
* Two passes
* m passes (m < n)
* n–1, n, n+1 passes

**Nested Loops:** Start from innermost; test outward with minimal values.
**Concatenated Loops:** Test as simple if independent; else treat as nested.
**Unstructured Loops:** Should be redesigned.

---

### **Summary:**

White-box testing ensures complete **structural coverage** through:

* **Basis Path Testing**
* **Condition Testing**
* **Data Flow Testing**
* **Loop Testing**

It validates internal logic, decision outcomes, data flow, and loop behavior, improving software reliability and quality.
