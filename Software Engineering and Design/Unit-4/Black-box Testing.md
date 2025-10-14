### **BLACK-BOX TESTING (20 Marks)**

**Definition:**
Black-box testing (behavioral testing) focuses on *functional requirements* of software. It derives input conditions to test all functional requirements without considering internal logic. It complements white-box testing by detecting different error classes.

**Error Categories:**

1. Incorrect/missing functions
2. Interface errors
3. Data structure or external database errors
4. Behavior/performance errors
5. Initialization/termination errors

**Focus Questions:**

* How is functional validity tested?
* How are behavior and performance tested?
* What input classes make effective test cases?
* Sensitivity to input values?
* Boundary isolation?
* Data rate/volume tolerance?
* Effect of input combinations?

**Objectives:**
Black-box techniques derive test cases that (1) minimize redundancy and (2) reveal classes of errors rather than individual ones.

---

### **Graph-Based Testing Methods:**

* Identify *software objects* and *relationships* using **graphs** (nodes = objects, links = relationships).
* **Node weights** describe object properties; **link weights** describe relationship characteristics.
* **Directed**, **bidirectional**, and **parallel links** represent various relationship types.

**Models:**

* **Transaction Flow Modeling:** Nodes = transaction steps; Links = logical connections.
* **Finite State Modeling:** Nodes = user-visible states; Links = transitions between states.
* **Data Flow Modeling:** Nodes = data objects; Links = data transformations.
* **Timing Modeling:** Nodes = program objects; Links = sequential connections with timing constraints.

---

### **Equivalence Partitioning (EP):**

Divides input domain into *equivalence classes* of valid/invalid data to minimize test cases.
Guidelines:

1. For range: 1 valid + 2 invalid classes.
2. For specific value: 1 valid + 2 invalid.
3. For set membership: 1 valid + 1 invalid.
4. For Boolean: 1 valid + 1 invalid.
   → Each test case covers the maximum attributes of a class.

---

### **Boundary Value Analysis (BVA):**

Errors occur at *input/output boundaries*. BVA designs tests at limits of input/output domains.
Guidelines:

1. For range [a,b]: test at a, b, just above and below.
2. For discrete values: test min, max, and just beyond.
3. Apply same for output.
4. Test internal data structure limits (e.g., table with 100 entries).

BVA complements EP and enhances error detection at edges.

---

### **Orthogonal Array Testing (OAT):**

Used when *input domain* is limited but exhaustive testing is impractical. It ensures uniform and balanced test coverage.

* Example: For 3 inputs (X,Y,Z) with 3 values each → 27 possible cases.
* Using **L9 orthogonal array**, only 9 cases give balanced coverage.

**Advantages:**

* Detects *single-mode faults* (errors from single parameter values).
* Detects *double-mode faults* (errors from parameter interactions).
* Can reveal some *multimode faults*.
  Provides higher coverage with fewer tests compared to exhaustive or one-variable-at-a-time testing.

---

**Summary:**
Black-box testing evaluates *functionality* without internal details. Methods like **Graph-based**, **Equivalence Partitioning**, **Boundary Value Analysis**, and **Orthogonal Array Testing** ensure efficient, comprehensive, and structured detection of functional and logical errors.
