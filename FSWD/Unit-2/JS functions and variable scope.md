

## 🧠 JavaScript Functions and Variable Scope – Explained with Examples

### ✅ What Is a JavaScript Function?

A **function** in JavaScript is a reusable block of code designed to perform a specific task. Functions help organize code, reduce repetition, and improve readability.

---

### 📌 Syntax of a Function

```javascript
function functionName(parameters) {
  // Code to execute
}
```

#### ✅ Example:

```javascript
function greet(name) {
  console.log("Hello, " + name + "!");
}
greet("Ajitha"); // Output: Hello, Ajitha!
```

---

### 🔄 Types of Functions

| Type | Description | Example |
|------|-------------|---------|
| Named Function | Declared with a name | `function add(a, b) { return a + b; }` |
| Anonymous Function | No name, often used in expressions | `let sum = function(a, b) { return a + b; };` |
| Arrow Function | Short syntax using `=>` | `const greet = (name) => "Hi " + name;` |

---

### 🧩 Parameters and Return Values

Functions can accept **parameters** and return **values** using the `return` keyword.

```javascript
function square(x) {
  return x * x;
}
console.log(square(5)); // Output: 25
```

---

## 🌐 Global vs Local Variables in JavaScript

### 🔍 Global Variables

- Declared **outside** any function or block.
- Accessible **anywhere** in the script.
- Can lead to **unexpected behavior** if not managed properly.

#### ✅ Example:

```javascript
let petName = "Raguuu"; // Global variable

function showPet() {
  console.log("Pet name is " + petName);
}
showPet(); // Output: Pet name is Raguuu
```

---

### 🔒 Local Variables

- Declared **inside** a function.
- Accessible **only within** that function.
- Helps avoid **naming conflicts** and improves modularity.

#### ✅ Example:

```javascript
function myFunction() {
  let petName = "Sizzer"; // Local variable
  console.log(petName);
}

function anotherFunc() {
  let petName = "Tom"; // Local variable
  console.log(petName);
}

myFunction();      // Output: Sizzer
anotherFunc();     // Output: Tom
console.log(petName); // Error: petName is not defined
```

---

### 🧠 Key Points on Variable Scope

- Variables declared with `var` are **function-scoped**.
- Variables declared with `let` and `const` are **block-scoped**.
- Omitting `var`, `let`, or `const` makes a variable **global** (not recommended).

---

### 📚 Summary Table for Revision

| Concept | Global Variable | Local Variable |
|--------|------------------|----------------|
| Scope | Entire script | Inside function only |
| Declaration | Outside functions | Inside functions |
| Access | Anywhere | Only within function |
| Risk | Can cause conflicts | Safer and modular |
