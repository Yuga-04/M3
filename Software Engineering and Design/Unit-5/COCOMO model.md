Got it 👍 — you’ve uploaded several images containing notes about the **COCOMO Model**.
Here’s the **complete extracted text** from all those images combined and formatted clearly:

---

## **COCOMO MODEL (Constructive Cost Estimation Model)**

The **COCOMO (Constructive Cost Estimation Model)** was proposed by **Barry Boehm in 1981**.
It is used to **estimate the effort, development time, and cost** required to develop a software project.

COCOMO estimates are based on the **size of the software** (in **KLOC – Kilo Lines of Code**).

---

### **Types of Software Projects**

COCOMO classifies software projects into three categories based on their complexity:

1. **Organic:**

   * Small, simple projects.
   * Experienced team and familiar environment.
   * **Example:** Payroll system, Inventory management.

2. **Semidetached:**

   * Medium-size projects.
   * Team has mixed experience levels.
   * **Example:** Database or compiler for a specific system.

3. **Embedded:**

   * Complex, real-time systems with hardware constraints.
   * **Example:** Flight control system, medical equipment software.

---

### **Effort and Development Time Formulas**

| **Project Type** | **Effort Formula (PM)** | **Development Time (Months)** |
| ---------------- | ----------------------- | ----------------------------- |
| **Organic**      | 2.4 × (KLOC)^1.05       | 2.5 × (Effort)^0.38           |
| **Semidetached** | 3.0 × (KLOC)^1.12       | 2.5 × (Effort)^0.35           |
| **Embedded**     | 3.6 × (KLOC)^1.20       | 2.5 × (Effort)^0.32           |

---

### **Example Calculation**

If **size = 32 KLOC (Organic project):**

Effort = 2.4 × (32)^1.05 = **91 PM**
Tdev = 2.5 × (91)^0.38 = **14 months**

If **salary = ₹15,000 per month → Cost = 14 × 15,000 = ₹2,10,000**

---

## **Levels of COCOMO Model**

Boehm proposed **three levels** of COCOMO for better accuracy:

1. **Basic COCOMO Model**
2. **Intermediate COCOMO Model**
3. **Complete (Detailed) COCOMO Model**

---

### **1) Basic COCOMO Model**

It provides a **rough estimate** of the project effort and time.

**Formula:**

Effort (in PM) = a₁ × (KLOC)^b₁
Tdev (in months) = b₁ × (Effort)^b₂

Where:

* PM → Person-Months
* KLOC → Thousand Lines of Code
* a₁, b₁, b₂ are constants for each project type

---

### **2) Intermediate COCOMO Model**

* Improves the accuracy of the Basic Model by considering **15 Cost Drivers (multipliers)**.
* These factors affect cost depending on:

  * **Product attributes** (reliability, complexity)
  * **Hardware attributes** (performance, memory constraints)
  * **Personnel attributes** (experience, skill)
  * **Project attributes** (tools, schedule)

**Formula:**

Effort = a₁ × (KLOC)^b₁ × EAF
Tdev = b₁ × (Effort)^b₂

Where **EAF (Effort Adjustment Factor)** is the product of all cost drivers (usually **0.9 to 1.4**).

---

### **3) Complete (Detailed) COCOMO Model**

* Used for **large systems** divided into **subsystems** (like GUI, Database, Communication).
* Estimates cost **separately for each component**, and adds them up for total cost.
* Gives the **most accurate estimate** among all COCOMO versions.

---

## **COCOMO II Model**

An **updated version** of the original model.
It includes **modern software development practices**.

### **Stages of COCOMO II:**

1. **Application Composition Model** – for early prototyping.
2. **Early Design Model** – when architecture is fixed.
3. **Post-Architecture Model** – during actual coding and testing.

**COCOMO II uses:**

* **Object Points**
* **Function Points**
* **Lines of Code (LOC)**
  for size measurement.

---

### **Key Points**

* Effort grows **super-linearly** with project size.
* Development time grows **sub-linearly** due to parallel work.
* **Basic →** for quick estimate.
* **Intermediate →** more accurate (uses cost drivers).
* **Complete →** most detailed and accurate.

---

Would you like me to convert this into a **Word document or PDF** for download?
