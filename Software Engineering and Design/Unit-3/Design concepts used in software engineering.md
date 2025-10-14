### **Design Concepts in Software Engineering (15 Marks)**

**Design** creates a **model of software**, detailing **architecture, data structures, interfaces, and components** for implementation. **Fundamental design concepts** provide a framework for building correct, maintainable, and high-quality software.

---

### **Important Software Design Concepts**

1. **Abstraction**

   * Focus on **essential features**, ignoring low-level details.
   * **Procedural Abstraction:** Named sequences of instructions with limited function (e.g., `open` door).
   * **Data Abstraction:** Named collection of attributes describing an object (e.g., door type, dimensions).
   * **Control Abstraction:** Control mechanisms without revealing internal details (e.g., semaphore).

2. **Architecture**

   * Structure and interaction of **program components (modules)** and data.
   * **Desired properties:**

     * Structural (component interaction)
     * Extra-functional (performance, reliability, security)
     * Reusable **architectural building blocks**
   * **Models:** Structural, Framework, Dynamic, Process, Functional
   * **Partitioning:**

     * Horizontal (function-wise: Input, Process, Output)
     * Vertical (top-down control, maintainable, fewer side effects)

3. **Pattern**

   * **Design patterns** solve specific design problems in context.
   * Guide for applicability, reuse, and creating similar solutions.

4. **Separation of Concerns**

   * Divide complex problems into independent pieces.
   * Supports **divide-and-conquer strategy** for easier problem solving.

5. **Modularity**

   * Software divided into **modules**; supports manageability, testing, maintenance.
   * **Objectives:** Decomposability, Composability, Understandability, Continuity, Protection.
   * **Benefits:** Efficient planning, incremental development, easier testing, reduced side effects.

6. **Information Hiding**

   * Modules hide internal **algorithms and data**; communicate only through interfaces.
   * **Benefits:** Limits global impact, reduces errors, supports encapsulation, enhances quality.

7. **Functional Independence**

   * Modules have **single-minded function** with minimal interaction.
   * **Measured by:**

     * **Cohesion:** Strength of internal relationships. Levels: Coincidental → Functional → Informational.
     * **Coupling:** Degree of inter-module dependency. Types: Data, Stamp, Control, Common, Content, Subclass.
   * Aim: **High cohesion, low coupling**.

8. **Refinement**

   * Elaborating high-level instructions into detailed steps (**stepwise refinement**).
   * Top-down iterative design to reveal low-level details.

9. **Aspects**

   * Represent **crosscutting concerns** (e.g., security, logging) in separate modules.

10. **Refactoring**

    * **Reorganize design/code** to improve structure without changing external behavior.
    * Removes redundancy, inefficiency, and poor structures.

11. **Object-Oriented Design Concepts**

    * Use **classes, objects, inheritance, polymorphism, and messages** for high-quality software.

12. **Design Classes**

    * Refine **analysis classes** into **design classes** with implementation details.
    * **Types:** User Interface, Business Domain, Process, Persistent, System.
    * **Characteristics:** Complete, primitive (focused methods), high cohesion, low coupling.
    * **Law of Demeter:** Methods interact minimally with neighboring classes.
