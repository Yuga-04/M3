

## **PATH TESTING AND VALIDATION TECHNIQUES (15 Marks)**

### **1. Validation Testing**

Performed after **integration testing** when the full software system is assembled. Focuses on **user-visible actions** and **outputs** to ensure the system meets **Software Requirements Specification (SRS)** and **validation criteria**.

**Goal:**
To confirm that the software functions as expected by the user.

**Validation Test Criteria:**
Tests verify:

* Functional and performance requirements
* Accuracy of content and documentation
* Usability, compatibility, maintainability, and error recovery

**Results:**

* Conforms → accepted
* Deviations → deficiency list and resolution with customer

**Configuration Review (Audit):**
Checks all configuration elements are properly developed and documented.

**Alpha & Beta Testing:**

* **Alpha Testing:** At developer site, by end users in controlled setup.
* **Beta Testing:** At customer site in real environment, without developer presence.
* **Customer Acceptance Testing:** Formal testing by client before software acceptance.

---

### **2. Basis Path Testing (White-Box Testing)**

Proposed by **Tom McCabe**, it measures program **logical complexity** and ensures all statements execute at least once through **independent paths**.

**Flow Graph:**
Uses **nodes** (processing statements) and **edges** (control links); **predicate nodes** show decisions.

**Independent Paths:**
Each new path adds unique processing or condition; ensures all branches are tested.

**Cyclomatic Complexity (V(G))** gives number of independent paths:

* ( V(G) = E - N + 2 )
* ( V(G) = P + 1 )
* Or equals number of **regions** in the flow graph.

Example: 11 edges, 9 nodes, 3 predicates → ( V(G)=4 ) → 4 paths to test.

**Steps:**

1. Draw flow graph.
2. Compute ( V(G) ).
3. Identify independent paths.
4. Create test cases for each path to cover all statements and conditions.

**Graph Matrix:**
Tabular form of flow graph; entries represent edges. Adding **link weights** (e.g., probability, time, memory) aids automation of test design.

---

### **Summary:**

* **Validation Testing** confirms system meets user requirements via configuration review and alpha/beta/acceptance testing.
* **Basis Path Testing** ensures logic correctness using cyclomatic complexity and path coverage.
  Together, they ensure **functional validation** and **structural verification** of software quality.

