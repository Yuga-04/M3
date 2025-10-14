### **Cyclomatic Complexity (15 Marks)**

**Cyclomatic Complexity** is a **software metric** that provides a **quantitative measure** of the **logical complexity** of a program. It helps determine the **number of independent paths** in the **basis set** of a program and gives an **upper bound** on the **number of tests** needed to ensure that **all statements** are executed at least once. It is based on **graph theory** and is highly useful in **white-box testing** and **basis path testing**.

---

### **Computation of Cyclomatic Complexity**

Cyclomatic complexity can be computed in **three ways**:

1. **By regions:**
   The **number of regions** of the **flow graph** corresponds to the **cyclomatic complexity**.

2. **By edges and nodes:**
   ( V(G) = E - N + 2 )
   where

   * *E* = number of **edges** in the flow graph
   * *N* = number of **nodes**

3. **By predicate nodes:**
   ( V(G) = P + 1 )
   where

   * *P* = number of **predicate nodes** (decision points) in the flow graph.

---

### **Example:**

For the flow graph in Figure 18.2b:

1. Number of **regions** = 4
2. ( V(G) = 11 - 9 + 2 = 4 )
3. ( V(G) = 3 + 1 = 4 )

Hence, **Cyclomatic Complexity V(G) = 4**, meaning there are **4 independent paths**.

---

### **Deriving Test Cases Using Basis Path Testing**

Cyclomatic complexity helps identify **independent paths** for testing.
Steps:

1. **Draw the flow graph** from design or code using standard symbols.
2. **Compute V(G)** using any of the above formulas.
3. **Identify the basis set** of **linearly independent paths** equal to the value of V(G).
4. **Design test cases** to execute each path at least once.

---

### **Example: Procedure “Average”**

For the *average* procedure:

* ( V(G) = 6 ) (6 regions, 17 edges, 13 nodes, 5 predicate nodes).
* Therefore, there are **6 independent paths** such as:

  1. 1-2-10-11-13
  2. 1-2-10-12-13
  3. 1-2-3-10-11-13
  4. 1-2-3-4-5-8-9-2…
  5. 1-2-3-4-5-6-8-9-2…
  6. 1-2-3-4-5-6-7-8-9-2…

Each **path** ensures every **statement** and **condition** is executed at least once.

---

### **Conclusion**

* **Cyclomatic complexity** measures **program complexity** and **testing effort**.
* Higher values indicate **more complex logic** and **higher testing needs**.
* It ensures **complete statement and branch coverage**, improving **software reliability**.


