
---

## **PETRI NETS – 15 Marks**

**Definition:**
A **Petri Net (PN)** is a mathematical and graphical modeling tool used to describe **system states, events, and transitions**. It is widely used for modeling **software processes, requirements, and architectures**.

---

### **Components of a Petri Net:**

1. **Places (P):** Represent **system states**. Example: `On` and `Off`.
2. **Transitions (T):** Represent **events** that may change the state. Example: `Switch On` and `Switch Off`.
3. **Arcs (I, O, H):** Define the **relationships between places and transitions**.
4. **Tokens:** Reside in **places** and indicate the **current state** of the system.

**Example:**

* Places: `Off`, `On`
* Transitions: `Switch Off`, `Switch On`
* Arcs: Connect places to transitions and vice versa
* Initial state: `Off` has one token
* Transition firing: A transition fires if **an input token exists**, moving one token from the **input place to the output place**.

---

### **Petri Net Properties:**

A PN can be defined as an **8-tuple mathematical model:**

[
M = {P, T, I, O, H, PAR, PRED, MP}
]

| Component   | Description                             |
| ----------- | --------------------------------------- |
| **P**       | Set of places                           |
| **T**       | Set of transitions                      |
| **I, O, H** | Input, Output, and Inhibition functions |
| **PAR**     | Set of parameters                       |
| **PRED**    | Predicates restricting parameter range  |
| **MP**      | Parameter values                        |

* **Linear algebra** can be applied to analyze the network.
* Tokens and transitions define the **dynamic behavior** of the system.

---

### **Advantages of Petri Nets:**

1. **Rich modeling capabilities** for software systems.
2. Can model **requirements, software architecture, and processes** effectively.
3. Supports **formal analysis** using mathematical methods.

### **Drawbacks:**

1. Complex rules for **transition firing and token flow**.
2. **Analysis** becomes difficult for large or highly interconnected systems.

---

**Summary:**
Petri Nets are a **powerful tool for modeling dynamic systems**, capturing both **states (places)** and **events (transitions)**, with **tokens tracking system behavior**. They provide **formal, analyzable representations** but are **complex to apply and analyze** for large systems.

✅ **Keywords included:** Petri Nets, places, transitions, arcs, tokens, firing, 8-tuple, P, T, I, O, H, PAR, PRED, MP, linear algebra, modeling, software requirements, software architecture, processes, analysis.

---
```Diagram
   [Off] o----> (Switch On) ----> o [On]
     ^                             |
     |                             |
     +---- (Switch Off) <----------+
```
