## **Functional and Non-Functional Requirements (15 Marks)**

Software requirements are classified into **functional** and **non-functional requirements**, which together define **what the system does** and **how it performs**.

---

### **1. Functional Requirements**

**Definition:** Statements describing the **services** a system should provide, its **behavior** in response to inputs, and actions in specific situations. Functional requirements may also specify what the system **should not do**.

**Key Points:**

* **Scope:** From general system-level services to specific organizational workflows.
* **Importance:** Imprecise functional specifications cause many software engineering problems.
* **Criteria:**

  * **Completeness:** All required services must be defined.
  * **Consistency:** No contradictory definitions.
* **Examples:** User authentication, order processing, report generation.

**Categories Related to Functional Requirements:**

* **Product requirements:** Specify or constrain software behavior.
* **Organizational requirements:** Derived from policies/procedures in customer or developer organization.
* **External requirements:** Derived from external factors affecting the system or development process.

---

### **2. Non-Functional Requirements**

**Definition:** Constraints on the **services/functions** offered by the system. These often apply to the **system as a whole** rather than individual features.

**Characteristics:**

* Concerned with **emergent system properties**, such as reliability, response time, and capacity.
* Difficult to assign to specific components because they affect **overall architecture**.
* May generate additional functional requirements (e.g., security requirement → new authentication services).

**Examples of Non-Functional Properties and Measures:**

| **Property** | **Measure**                                                                     |
| ------------ | ------------------------------------------------------------------------------- |
| Speed        | Processed transactions per second, user/event response time                     |
| Size         | KBytes, number of RAM chips                                                     |
| Ease of Use  | Training time, number of help frames                                            |
| Reliability  | Mean time to failure, probability of unavailability, rate of failure occurrence |
| Availability | Time to restart after failure                                                   |
| Robustness   | % of events causing failure, probability of data corruption on failure          |
| Portability  | % of target-dependent statements, number of target systems                      |

**Key Points:**

* Non-functional requirements constrain **timing, standards, or development process**.
* Implementation may be **diffused throughout the system**.
* Critical for system **quality, user satisfaction, and maintainability**.

---

**Summary:**

* **Functional requirements** define **what the system must do** (services and behavior).
* **Non-functional requirements** define **how the system performs** (quality attributes, constraints).
* Both are essential for a complete, consistent, and usable software system.

✅ **Keywords Covered:** Functional requirements, Non-functional requirements, completeness, consistency, system services, constraints, reliability, performance, availability, robustness, product/organizational/external requirements.
