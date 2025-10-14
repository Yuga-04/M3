## **Cohesion and Coupling in Software Design (15 Marks)**

**Functional Independence** is achieved by designing modules with **single-minded function** and minimal interaction with other modules. The quality of functional independence is measured using **cohesion** and **coupling**.

---

### **1. Cohesion**

**Definition:** Cohesion measures the **internal functional strength** of a module — how closely related its components are. **High cohesion** improves understandability, maintainability, and reusability.

**Types of Cohesion with Examples:**

| **Type**        | **Description**                                       | **Example**                                                                |
| --------------- | ----------------------------------------------------- | -------------------------------------------------------------------------- |
| Coincidental    | Unrelated parts bundled                               | Module handles logging, error handling, and input validation together      |
| Logical         | Similar functions grouped                             | Module handles all types of input processing (keyboard, mouse, touch)      |
| Temporal        | Tasks executed at the same time                       | Startup module initializing system variables, config, and logs             |
| Procedural      | Single control sequence                               | Module executes a sequence of calculation steps in order                   |
| Communicational | Operates on same data                                 | Module updates a customer record: changes name and address                 |
| Sequential      | Output of one part serves as input to another         | Module calculates salary → passes to tax module → passes to payroll module |
| Informational   | Multiple functions with independent code on same data | Module manages a bank account: deposit, withdraw, check balance            |
| Functional      | Performs a single task                                | Module computes square root of a number                                    |

**Rule:** Strive for **high cohesion** (functional or informational) for easier maintenance and testing.

---

### **2. Coupling**

**Definition:** Coupling measures the **interdependence** between modules. **Low coupling** is desirable for functional independence.

**Types of Coupling with Examples:**

| **Type**          | **Description**                                 | **Example**                                                     |
| ----------------- | ----------------------------------------------- | --------------------------------------------------------------- |
| Data Coupling     | Modules pass only necessary data                | `calculateTax(amount)` passes just `amount`                     |
| Stamp Coupling    | Pass part of a data structure                   | `updateEmployee(Employee e)` uses only `e.salary`               |
| Control Coupling  | One module controls the flow of another         | `processOrder(order, mode)` where `mode` directs behavior       |
| Common Coupling   | Modules share global data                       | Multiple modules access a global `config` variable              |
| Content Coupling  | One module accesses internal content of another | Module directly modifies array inside another module            |
| Subclass Coupling | Coupling between class and parent class         | Child class overrides parent method and depends on parent logic |

**Rule:** Strive for **low coupling** to reduce dependency, facilitate reuse, and isolate errors.

---

### **3. Relation to Functional Independence**

* **High cohesion + Low coupling** = Functionally independent modules.
* Modules perform **single-minded functions**.
* Easier to **test, maintain, and reuse**.
* Changes in one module **minimally affect others**.

---

✅ **Keywords Covered:** Functional Independence, module, cohesion, coupling, high cohesion, low coupling, types of cohesion, types of coupling, maintainability, reusability, single-minded function.
