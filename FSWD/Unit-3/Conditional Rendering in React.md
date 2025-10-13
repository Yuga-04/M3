

# ⚛️ **Conditional Rendering in React**

---

## 🌐 **Introduction**

In **React**, *Conditional Rendering* means displaying different content or components based on **certain conditions** — just like using **if-else statements** in JavaScript.
React allows developers to control **what should appear on the screen** depending on the **state**, **props**, or **user interactions**.

For example, a login button should be shown if a user is not logged in, and a logout button if they are logged in.

Conditional rendering helps in creating **dynamic, responsive, and user-friendly interfaces.**

---

## ⚙️ **1️⃣ What is Conditional Rendering?**

Conditional rendering in React works similarly to conditions in JavaScript.
Instead of manipulating the DOM manually, React updates the **Virtual DOM** automatically when the condition changes.

---

## 💡 **2️⃣ Example of Conditional Rendering**

### 🧠 **Example 1: Using if–else Statement**

```jsx
import React from "react";

function Greeting(props) {
  if (props.isLoggedIn) {
    return <h1>Welcome Back, User!</h1>;
  } else {
    return <h1>Please Login</h1>;
  }
}

export default Greeting;
```

### 📘 **Explanation:**

* If `isLoggedIn` is **true**, it returns **“Welcome Back, User!”**
* If **false**, it returns **“Please Login”**

### ✅ **Output**

```
Welcome Back, User!
```

*(if isLoggedIn = true)*

---

## ⚙️ **3️⃣ Using if–else inside Render Method (Class Component)**

```jsx
import React, { Component } from "react";

class LoginControl extends Component {
  constructor(props) {
    super(props);
    this.state = { isLoggedIn: false };
  }

  render() {
    if (this.state.isLoggedIn) {
      return <h2>Welcome, Yuga!</h2>;
    } else {
      return <h2>Please Sign In</h2>;
    }
  }
}

export default LoginControl;
```

### ✅ **Output**

```
Please Sign In
```

If `isLoggedIn` is changed to `true`, it will display:

```
Welcome, Yuga!
```

---

## ⚙️ **4️⃣ Using Ternary Operator ( ? : )**

The **ternary operator** is a compact way to handle conditional rendering.

### 💡 **Example**

```jsx
function Greeting(props) {
  return (
    <div>
      {props.isLoggedIn ? <h1>Welcome Back!</h1> : <h1>Please Login</h1>}
    </div>
  );
}
```

### ✅ **Output**

```
Welcome Back!
```

**Explanation:**
If `isLoggedIn` is true, **Welcome Back!** is shown; otherwise, **Please Login** appears.

---

## ⚙️ **5️⃣ Using Logical AND ( && ) Operator**

When you only want to render something **if a condition is true**, you can use the `&&` operator.

### 💡 **Example**

```jsx
function Message(props) {
  return (
    <div>
      <h2>Hello User</h2>
      {props.unreadMessages.length > 0 &&
        <p>You have {props.unreadMessages.length} unread messages.</p>}
    </div>
  );
}
```

### ✅ **Output**

```
Hello User
You have 3 unread messages.
```

If `unreadMessages` is empty, the second line won’t appear.

---

## ⚙️ **6️⃣ Using Switch Case for Conditional Rendering**

### 💡 **Example**

```jsx
function StatusMessage(props) {
  switch (props.status) {
    case "loading":
      return <h3>Loading...</h3>;
    case "success":
      return <h3>Data Loaded Successfully!</h3>;
    case "error":
      return <h3>Error Loading Data!</h3>;
    default:
      return <h3>Unknown Status</h3>;
  }
}
```

### ✅ **Output**

```
Data Loaded Successfully!
```

*(if status = “success”)*

---

## 🧩 **7️⃣ Conditional Rendering with Elements**

You can also store a component or element in a variable and render it conditionally.

### 💡 **Example**

```jsx
function UserAccess(props) {
  let button;
  if (props.isLoggedIn) {
    button = <button>Logout</button>;
  } else {
    button = <button>Login</button>;
  }

  return (
    <div>
      <h1>Welcome!</h1>
      {button}
    </div>
  );
}
```

### ✅ **Output**

```
Welcome!
[Login]
```

*(Changes to [Logout] when isLoggedIn = true)*

---

## ✨ **8️⃣ Features of Conditional Rendering**

| Feature                 | Description                                                        |
| ----------------------- | ------------------------------------------------------------------ |
| **Dynamic UI**          | Renders different components or messages based on user state.      |
| **No Page Reloads**     | React updates only parts of UI that change.                        |
| **Cleaner Logic**       | Multiple conditions can be handled with short syntax.              |
| **Efficient Rendering** | Works with React’s Virtual DOM for faster updates.                 |
| **Reusable Components** | The same component can behave differently based on props or state. |

---

## 🧾 **9️⃣ Advantages**

1. **Improves user experience** by displaying context-based messages.
2. **Reduces code duplication** by reusing the same component.
3. **Enhances performance** through selective updates.
4. **Makes debugging easier** since logic is clearly separated.
5. **Simplifies complex UI** behavior into readable conditional blocks.

---

## 🏁 **Conclusion**

Conditional rendering in React allows developers to build **dynamic and interactive web applications**.
By using **if–else**, **ternary**, **&&**, and **switch** methods, React components can efficiently display different views without reloading the page.
It’s one of the **core concepts** for creating **responsive, real-world React applications**.


