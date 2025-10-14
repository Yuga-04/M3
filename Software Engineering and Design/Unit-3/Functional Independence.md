### **Functional Independence in Software Design (15 Marks)**

**Functional Independence** is the design principle of developing modules with a **single-minded function** and minimal interaction with other modules. Each module addresses a specific subset of requirements and has a **simple interface**, allowing independent implementation and easier maintenance.

---

#### **Key Points**

1. **Definition:**

   * Modules perform a specific function with minimal reliance on other modules.
   * Critical for dividing complex systems into independently implementable parts.

2. **Measurement Criteria:**

   * **Cohesion:** Measures **internal functional strength** of a module. High cohesion means the module focuses on a single task.

     * **Levels of Cohesion:**

       1. **Coincidental:** Unrelated parts bundled together. Hard to understand, not reusable.
       2. **Logical:** Similar functions grouped; interface complex, maintenance difficult.
       3. **Temporal:** Functions activated together (e.g., startup/shutdown); moderate cohesion.
       4. **Procedural:** Single control sequence (e.g., loop); weakly connected.
       5. **Communicational:** Operates on same input/output data; moderately cohesive.
       6. **Sequential:** Output of one part serves as input to another; stronger cohesion.
       7. **Informational:** Multiple functions with independent code on same data; high cohesion.
       8. **Functional:** Module performs a single function; highly reusable and maintainable.
   * **Coupling:** Measures **interdependence** between modules. Lower coupling is better.

     * **Types of Coupling:** Data, Stamp, Control, Common, Content, Subclass.
     * Goal: **High cohesion + Low coupling** for well-designed, independent modules.

3. **Importance of Functional Independence:**

   * Simplifies maintenance and testing.
   * Enhances **modularity** and understandability.
   * Reduces ripple effects of changes in one module on others.
   * Improves **reusability** of modules in different systems.

