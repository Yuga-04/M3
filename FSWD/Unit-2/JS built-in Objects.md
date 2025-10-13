

## 🧠 JavaScript Built-in Objects – Explained with Examples

### ✅ What Are Built-in Objects?

Built-in objects in JavaScript are **predefined global objects** provided by the language to perform common tasks like mathematical operations, date handling, string manipulation, and more. They are **not related to the DOM or browser window**, and are available in all JavaScript environments.

---

### 📌 Key Built-in Objects and Their Usage

| Object | Purpose | Example |
|--------|---------|---------|
| `Math` | Performs mathematical operations | `Math.sqrt(16)` → `4` |
| `Date` | Handles date and time | `new Date()` → current date/time |
| `String` | Manipulates text | `"Ajitha".toUpperCase()` → `"AJITHA"` |
| `Array` | Stores multiple values | `[1, 2, 3].length` → `3` |
| `Number` | Handles numeric values | `Number("123")` → `123` |
| `Boolean` | Represents true/false | `Boolean(0)` → `false` |
| `RegExp` | Matches patterns in strings | `/ab+c/.test("abc")` → `true` |
| `Object` | Base for all objects | `typeof {}` → `"object"` |

---

### 🔍 1. Math Object

- Static object used for complex calculations
- No need to create an instance

#### ✅ Example:

```javascript
console.log(Math.PI);         // 3.14159...
console.log(Math.sqrt(25));   // 5
console.log(Math.random());   // Random number between 0 and 1
```

---

### 🔍 2. Date Object

- Used to work with dates and times

#### ✅ Example:

```javascript
let now = new Date();
console.log(now.toDateString()); // e.g., "Mon Oct 13 2025"
```

---

### 🔍 3. Array Object

- Stores multiple values in a single variable

#### ✅ Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];
console.log(fruits.length); // 3
```

---

### 🔍 4. String Object

- Provides methods to manipulate text

#### ✅ Example:

```javascript
let name = "Ajitha";
console.log(name.toUpperCase()); // "AJITHA"
```

---

### 🔍 5. RegExp Object

- Used for pattern matching in strings

#### ✅ Example:

```javascript
let pattern = /ab+c/;
console.log(pattern.test("abc")); // true
```

---

### 🔍 6. Object Literal

- Collection of key-value pairs

#### ✅ Example:

```javascript
let games = { cricket: 11, chess: 2, carrom: 4 };
console.log(games.chess); // 2
```

---

### 📚 Summary Table for Revision

| Object | Key Method/Property | Example |
|--------|---------------------|---------|
| `Math` | `Math.sqrt()` | `Math.sqrt(9)` → `3` |
| `Date` | `new Date()` | `new Date().getFullYear()` |
| `Array` | `.push()`, `.length` | `arr.push("JS")` |
| `String` | `.toUpperCase()` | `"hi".toUpperCase()` |
| `RegExp` | `.test()` | `/abc/.test("abc")` |
| `Object` | `{ key: value }` | `obj.name` |
