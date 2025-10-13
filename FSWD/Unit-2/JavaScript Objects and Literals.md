

## 🧠 JavaScript Objects and Literals – Explained with Examples

### ✅ What Is a JavaScript Object?

A **JavaScript object** is a non-primitive data type used to store **key-value pairs**. It acts like a container that holds multiple values under a single name, making it ideal for representing structured data.

- Keys (also called properties) must be strings or symbols.
- Values can be any data type: string, number, boolean, array, function, or another object.

---

### 📌 Syntax of Object Creation

```javascript
let person = {
  name: "Ajitha",
  age: 22,
  isStudent: true
};
```

- `name`, `age`, and `isStudent` are **keys**
- `"Ajitha"`, `22`, and `true` are **values**

---

### 🧾 Accessing Object Properties

```javascript
console.log(person.name);       // Dot notation
console.log(person["age"]);     // Bracket notation
```

---

### 🔄 Modifying Object Properties

```javascript
person.age = 23;                // Update value
person.city = "Chennai";       // Add new property
```

---

### 🧩 What Is an Object Literal?

An **object literal** is a way to define an object directly using curly braces `{}` with key-value pairs.

#### ✅ Example:

```javascript
let car = {
  brand: "Tesla",
  model: "Model S",
  year: 2025
};
```

This is an object literal. It’s the most common and readable way to create objects in JavaScript.

---

### 🧪 Nested Object Literals

Objects can contain other objects as values.

```javascript
let student = {
  name: "Ajitha",
  marks: {
    math: 95,
    science: 90
  }
};
console.log(student.marks.math); // Output: 95
```

---

### 📚 Built-in Object Literal Example

```javascript
let games = {
  cricket: 11,
  chess: 2,
  carrom: 4
};
console.log(games.chess); // Output: 2
```

---

### 🧠 Benefits of Using Object Literals

- Easy to read and write
- Ideal for configuration and structured data
- Supports nesting and dynamic property access
- Can be passed as arguments to functions

---

### 🔍 Recognizing an Object

Use `typeof` or `instanceof`:

```javascript
console.log(typeof car);             // "object"
console.log(car instanceof Object);  // true
```

---

### 🧾 Summary Table for Revision

| Concept | Description | Example |
|--------|-------------|---------|
| Object | Key-value pair container | `{ name: "Ajitha", age: 22 }` |
| Object Literal | Direct object declaration | `let obj = { key: value }` |
| Access | Dot or bracket notation | `obj.key` or `obj["key"]` |
| Modify | Update or add property | `obj.newKey = value` |
| Nested Object | Object inside object | `obj.inner.key` |

