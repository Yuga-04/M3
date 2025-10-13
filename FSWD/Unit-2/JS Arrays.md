

## 🧠 Arrays in JavaScript – Explained with Examples

### ✅ What Is an Array?

An **array** in JavaScript is a data structure used to store **multiple values** in a single variable. These values can be of **same or different types**, and each value is called an **element**.

- Arrays are **zero-indexed**: the first element is at index `0`.
- Arrays are **dynamic**: they can grow or shrink in size.

---

### 📌 Ways to Create Arrays

#### 1. **Array Literal**

```javascript
let courses = ["HTML", "CSS", "JavaScript", "React"];
```

#### 2. **Array Constructor**

```javascript
let courses = new Array("HTML", "CSS", "JavaScript", "React");
```

#### 3. **Empty Array**

```javascript
let names = [];
let names2 = new Array();
```

---

### 🔍 Accessing Array Elements

```javascript
console.log(courses[0]); // HTML
console.log(courses[3]); // React
```

To access the **last element**:

```javascript
let lastItem = courses[courses.length - 1];
```

---

### 🔄 Modifying Array Elements

```javascript
courses[1] = "Bootstrap"; // Replaces "CSS" with "Bootstrap"
```

---

### ➕ Adding Elements

```javascript
courses.push("Node.js");       // Adds to end
courses.unshift("Web Dev");    // Adds to beginning
```

---

### ➖ Removing Elements

```javascript
courses.pop();     // Removes last element
courses.shift();   // Removes first element
courses.splice(1, 2); // Removes 2 elements from index 1
```

---

### 📏 Array Length

```javascript
let len = courses.length;
console.log(len); // Number of elements
```

You can also **increase or decrease** array length:

```javascript
courses.length = 7; // Adds empty slots
courses.length = 2; // Truncates array
```

---

### 🔁 Iterating Over Arrays

#### Using `for` loop:

```javascript
for (let i = 0; i < courses.length; i++) {
  console.log(courses[i]);
}
```

#### Using `forEach` loop:

```javascript
courses.forEach(function(item) {
  console.log(item);
});
```

---

### 🔗 Concatenating Arrays

```javascript
let otherCourses = ["Node.js", "Express.js"];
let allCourses = courses.concat(otherCourses);
```

---

### 🔄 Converting Array to String

```javascript
console.log(courses.toString()); // "HTML,CSS,JavaScript,React"
```

---

### 🔍 Checking Array Type

```javascript
console.log(typeof courses); // "object"
console.log(Array.isArray(courses)); // true
console.log(courses instanceof Array); // true
```

---

### 📚 Summary Table for Revision

| Operation | Method | Example |
|-----------|--------|---------|
| Create | `[]` or `new Array()` | `let arr = [1, 2]` |
| Access | `arr[i]` | `arr[0]` |
| Modify | `arr[i] = value` | `arr[1] = "CSS"` |
| Add | `push()`, `unshift()` | `arr.push("JS")` |
| Remove | `pop()`, `shift()`, `splice()` | `arr.pop()` |
| Length | `arr.length` | `arr.length` |
| Iterate | `for`, `forEach()` | `arr.forEach()` |
| Type Check | `Array.isArray()` | `Array.isArray(arr)` |
