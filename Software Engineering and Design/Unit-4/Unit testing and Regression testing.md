Here’s the **complete extracted text** from all the images you uploaded — cleanly formatted and organized for clarity:

---

## **UNIT TESTING**

### **Definition:**

Unit Testing focuses verification efforts on the **smallest unit of software design** — the software component or module.
The goal is to ensure that each individual part of the program functions correctly in isolation before integrating it into the larger system.

---

### **Purpose:**

* To validate that each unit of the software performs as expected.
* To identify and fix bugs early in development, reducing the cost and complexity of later fixes.

---

### **Features and Focus Areas:**

1. **Module Interface Testing** – Ensures information flows properly into and out of the component.
2. **Local Data Structures** – Checks that temporary data maintains integrity during all algorithm steps.
3. **Boundary Conditions** – Verifies proper operation at limits such as array bounds and loop limits.
4. **Independent Paths** – Exercises all control paths within the module to ensure complete execution coverage.
5. **Error Handling Paths** – Validates that the module responds correctly to specific error conditions.

---

### **Process:**

* Each unit is tested independently, often using **drivers and stubs**.
* **Driver:** A control program that passes test data to the component and displays results.
* **Stub:** A dummy module that simulates components not yet developed.
* Test cases are designed to uncover errors such as incorrect computations, improper control flow, and data boundary issues.
* Unit testing is simplified when the module design has **high cohesion** and **low coupling**.

---

### **Drivers and Stubs in Unit Testing:**

Since a component is not a stand-alone program, **drivers** and **stubs** are used to simulate the missing parts of the software.

* **Driver:**
  A simple main program that provides test data to the component under test and prints the results.
  It acts as a temporary calling program for the unit being tested.

* **Stub:**
  A dummy subprogram that simulates subordinate modules called by the component being tested.
  It performs minimal data manipulation, verifies the entry, and returns control to the main module.

➡️ Both **drivers and stubs** represent **testing overhead** as they need to be written specifically for testing but are not delivered with the final software product.

---

### **Advantages:**

* Detects bugs early in development.
* Simplifies debugging and error correction.
* Ensures each module functions correctly.
* Reduces integration issues later.
* Improves software reliability and quality.

---

### **Disadvantages:**

* Time-consuming to test every small unit.
* Requires creation of drivers and stubs (extra effort).
* Cannot detect integration or system-level issues.
* May miss interface errors between modules.

---

## **REGRESSION TESTING**

### **Definition:**

Regression Testing is the **re-execution of previously conducted test cases** to ensure that new code changes or module additions do not introduce unintended side effects or errors into previously working software.

---

### **Purpose:**

* To verify that modifications, enhancements, or bug fixes do not negatively affect existing functionality.
* To maintain system stability throughout development and maintenance.

---

### **Key Concepts:**

* Performed **after integration testing** or whenever code changes occur.
* Can be done **manually** or using **automated capture/playback tools** for efficiency.
* Ensures that existing features continue to function correctly after updates.

---

### **Regression Test Suite Includes:**

1. **A representative sample** of tests that exercise all software functions.
2. **Additional tests** focusing on software functions likely to be affected by recent changes.
3. **Tests** specifically targeting the modified or newly added components.

---

### **Process:**

1. Execute the regression test suite after any software change.
2. Compare the results with previous test outcomes.
3. Identify and fix any new defects introduced during modification.

---

### **Benefits:**

* Detects side effects from new code additions.
* Ensures overall software reliability after updates.
* Reduces the risk of breaking existing functionality.
* Builds confidence in software stability during maintenance.
* Supports long-term quality assurance and continuous improvement.

---

### **Advantages:**

* Ensures new changes do not affect existing features.
* Maintains software stability after updates.
* Detects side effects from new code.
* Builds confidence in software maintenance.
* Can be automated for efficiency.

---

### **Disadvantages:**

* Can be repetitive and time-consuming.
* Large regression test suites are difficult to manage.
* Automation tools may be costly.
* Does not test new functionalities directly.

---

Would you like me to combine this and your **COCOMO notes** into a single, downloadable **Word or PDF document** for easy studying?
