

# *Redux (13 Marks)*

---

### *1. Introduction (2 marks)*

Modern web applications often handle large amounts of data and complex user interactions. Managing this data consistently across different components becomes challenging.
*Redux* is a *state management library* for JavaScript applications, commonly used with *React* (but also compatible with Angular, Vue, etc.).

It provides a *centralized store* to manage the entire application’s state in a predictable and structured way.

---

### *2. Definition (1 mark)*

*Definition:*
*Redux* is an *open-source JavaScript library* used to manage the *state of an application* in a predictable manner using a *single source of truth* called the store.

It follows the principle of *unidirectional data flow*, ensuring that the application’s state behaves consistently.

---

### *3. Core Concept (2 marks)*

At its core, Redux revolves around three fundamental principles:

1. *Single Source of Truth:*
   The entire state of the application is stored in a single JavaScript object called the *store*.

2. *State is Read-Only:*
   The only way to change the state is to *dispatch an action*, which describes what happened.

3. *Changes are Made with Pure Functions:*
   To specify how the state changes, you write *reducers*, which are pure functions that take the previous state and an action, and return the next state.

---

### *4. Redux Architecture Diagram (2 marks)*


          +---------------------+
          |      View (UI)      |
          +----------+----------+
                     |
                     | Dispatch Action
                     |
          +----------v----------+
          |      Action         |
          +----------+----------+
                     |
                     | Sent to Reducer
                     |
          +----------v----------+
          |      Reducer        |
          +----------+----------+
                     |
                     | Updates State
                     |
          +----------v----------+
          |       Store         |
          +----------+----------+
                     |
                     | New State sent back
                     |
          +----------v----------+
          |      View (UI)      |
          +---------------------+


---

### *5. Components of Redux (3 marks)*

1. *Store:*

   * The centralized place where the entire state of the app is kept.
   * Only one store exists in a Redux application.

2. *Action:*

   * An object that describes what happened.
   * Must have a type property (e.g., { type: 'INCREMENT' }).

3. *Reducer:*

   * A pure function that takes the current state and an action, and returns a new state.
   * Example:

     js
     function counter(state = 0, action) {
       switch(action.type) {
         case 'INCREMENT': return state + 1;
         case 'DECREMENT': return state - 1;
         default: return state;
       }
     }
     

4. *Dispatch:*

   * The method used to send an action to the store.

5. *Subscriber / View (UI):*

   * React components that listen for state changes and update the UI automatically.

---

### *6. Data Flow in Redux (1 mark)*

Redux follows a *unidirectional data flow*:

1. User interacts with the *UI*.
2. UI *dispatches an action*.
3. *Reducer* processes the action and returns a new state.
4. The *Store* updates the state.
5. The *UI* re-renders based on the updated state.

---

### *7. Advantages of Redux (1 mark)*

* Predictable and centralized state management.
* Easier debugging and testing.
* Consistent behavior across environments.
* Supports time-travel debugging (using Redux DevTools).
* Useful for large-scale, complex applications.

---

### *8. Disadvantages of Redux (1 mark)*

* Requires a lot of boilerplate code.
* May be overkill for small applications.
* Learning curve for beginners.

---

### *9. Example Use Case (1 mark)*

In a *React-based e-commerce app*, Redux can manage:

* User authentication state,
* Shopping cart data,
* Product lists,
* Order history —
  All from a single centralized store.

---

### *10. Conclusion (1 mark)*

Redux provides a *structured, predictable, and scalable* way to handle state in modern web applications.
By maintaining a *single source of truth* and *pure function-based updates*, Redux enhances code maintainability, making it a key tool in front-end development.

