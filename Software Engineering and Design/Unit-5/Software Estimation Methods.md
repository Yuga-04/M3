## **ESTIMATION (Simple Explanation)**

### **Meaning**

* Software **cost and effort estimation** means predicting how much **money, time, and manpower** are needed to develop a software project.
* It can **never be exact**, because many factors (human, technical, political, environmental) can affect it.

---

### **Ways to Improve Estimation**

1. **Delay estimation** until later in the project when you know more details.
2. **Base estimates** on similar completed projects.
3. **Use decomposition techniques** – break the project into smaller parts to estimate easily.
4. **Use empirical models** – use mathematical models based on past data (like COCOMO-II).

A general model is written as:
👉 **d = f(vi)**
Where:

* **d** = estimated value (effort, cost, or duration)
* **vi** = independent variable (like Lines of Code or Function Points)

---

## **Decomposition Techniques**

1. **LOC-based estimation** – uses Lines of Code.
2. **FP-based estimation** – uses Function Points.

---

## **Empirical Models**

* These are **mathematical models** built from real data of old projects.
* Example: **COCOMO-II model**

---

## **Software Sizing**

To make accurate estimates, we must know:

1. The estimated **size** of the product.
2. The ability to convert size into **effort, time, and cost**.
3. How capable the **team** is.
4. How **stable** the project requirements are.

### **Four Methods of Sizing**

1. **Fuzzy Logic Sizing** – Guess size using a qualitative scale (e.g., small, medium, large).
2. **Function Point (FP) Sizing** – Estimate based on inputs, outputs, files, and interfaces.
3. **Standard Component Sizing** – Count common modules or screens and estimate each.
4. **Change Sizing** – Used when modifying an existing system (count changes to be made).

---

## **Problem-Based Estimation**

* LOC and FP are used to estimate the project size and cost.
* Productivity metrics like **LOC/person-month** or **FP/person-month** are used.
* You can also take **optimistic, most likely, and pessimistic** size values and find an average.

Expected size (S) = (sopt + 4 × sm + spess) / 6

---

## **1. Lines of Code (LOC)**

* **LOC** means counting the total number of **source lines of code** in the program.
* Comments and blank lines are not counted.
* Estimation is done by dividing the system into modules and using past project data.

### **Advantages**

* Very **simple** to use.
* **Widely used** and well-documented.

### **Disadvantages**

* Depends on **programming language**.
* Does not show **complexity** of the problem.
* Not suitable for **non-procedural languages**.
* **Difficult to estimate** at the start of the project.

### **Example (LOC Approach)**

Given:

* Productivity = 620 LOC/person-month
* Labor cost = Rs. 8000/month

Then cost per LOC = 8000 / 620 = Rs. 13
If estimated LOC = 33,200 → Total cost = 33,200 × 13 = Rs. 4,31,000
Effort = 54 person-months

---

## **2. Function Point (FP)**

* FP measures **software size** by counting the **functions** it performs.
* Depends on number of **inputs, outputs, inquiries, files, and interfaces**.

### **Formula**

**UFP = (Inputs × 4) + (Outputs × 5) + (Inquiries × 4) + (Files × 10) + (Interfaces × 10)**

Then compute **TCF (Technical Complexity Factor):**
TCF = 0.65 + 0.01 × DI
Where DI = Degree of Influence (0–70)

Finally, **FP = UFP × TCF**

### **Advantages**

* Can be estimated **from the problem description** (no need for actual code).

### **Disadvantages**

* Does not consider **algorithm complexity** (assumes all functions take same effort).

---

## **Feature Point Metric**

* Improved version of FP that includes **algorithm complexity**.
* Shows that more complex functions take **more effort and time**.
* Uses **three-point estimation** (optimistic, most likely, pessimistic) for better accuracy.

---

### **Example (FP Approach)**

Given:

* Productivity = 6.5 FP/person-month
* Labor cost = $8000 per month ($1230 per FP)

Total estimated cost = $461,000
Estimated effort = 58 person-months

---

## **Summary**

| Aspect                  | LOC Based          | FP Based                 |
| ----------------------- | ------------------ | ------------------------ |
| Basis                   | Lines of code      | Number of functions      |
| Easy to estimate early? | No                 | Yes                      |
| Language dependent?     | Yes                | No                       |
| Considers complexity?   | No                 | Not fully                |
| When to use             | After design phase | During requirement phase |

---

✅ **In short:**
Software estimation helps to **plan cost, time, and effort** needed for development.
It can be done using **LOC**, **FP**, or **empirical models** like **COCOMO-II**.
Though not 100% accurate, it helps in **better project planning and control.**

