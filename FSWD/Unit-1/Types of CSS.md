
# 🎨 **Types of CSS with Example**

### 🌐 **Introduction**

**CSS (Cascading Style Sheets)** is a stylesheet language used to describe the **look and formatting of a webpage** written in HTML.
It controls the layout, color, fonts, spacing, and overall presentation of web elements.
The main goal of CSS is to **separate content (HTML)** from **presentation (design)**.

---

## ⚙️ **1️⃣ Types of CSS**

CSS can be applied to an HTML document in **three different ways**:

| Type                        | Description                                                                          | Scope          |
| --------------------------- | ------------------------------------------------------------------------------------ | -------------- |
| **Inline CSS**              | Styles applied directly to an HTML element using the `style` attribute.              | Single element |
| **Internal CSS (Embedded)** | Styles defined inside the `<style>` tag within the `<head>` section of an HTML page. | Single page    |
| **External CSS**            | Styles written in a separate `.css` file and linked to multiple HTML pages.          | Multiple pages |

---

## 🧩 **2️⃣ Inline CSS**

### 📘 **Definition**

Inline CSS is used to apply a **unique style to a single HTML element** using the `style` attribute inside the tag.

### 🧠 **Syntax**

```html
<tag style="property: value;">
```

### 💡 **Example**

```html
<!DOCTYPE html>
<html>
<head>
<title>Inline CSS Example</title>
</head>
<body>
<h1 style="color:blue; text-align:center;">Welcome to Inline CSS</h1>
<p style="font-size:18px; color:green;">This text is styled using inline CSS.</p>
</body>
</html>
```

### ✅ **Output**

A blue centered heading and a green paragraph styled directly within the HTML tags.

---

## ⚙️ **3️⃣ Internal CSS**

### 📘 **Definition**

Internal CSS (also known as **Embedded CSS**) is defined inside the `<style>` tag located in the `<head>` section of the HTML document.
It applies style rules to elements within the **same HTML page**.

### 🧠 **Syntax**

```html
<style>
selector {
   property: value;
}
</style>
```

### 💡 **Example**

```html
<!DOCTYPE html>
<html>
<head>
<title>Internal CSS Example</title>
<style>
h1 {
   color: red;
   text-align: center;
}
p {
   color: green;
   font-size: 18px;
}
</style>
</head>
<body>
<h1>Welcome to Internal CSS</h1>
<p>This paragraph uses internal CSS styling.</p>
</body>
</html>
```

### ✅ **Output**

The heading appears in **red and centered**, while the paragraph appears **green** and **larger** in size.

---

## 🧾 **4️⃣ External CSS**

### 📘 **Definition**

External CSS is used when styles are defined in a **separate file** (with a `.css` extension) and **linked** to multiple HTML pages.
This allows consistent styling across the website.

### 🧠 **Linking Syntax (in HTML file)**

```html
<link rel="stylesheet" href="style.css">
```

### 💡 **Example**

**📄 external.html**

```html
<!DOCTYPE html>
<html>
<head>
<title>External CSS Example</title>
<link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
<h1>Welcome to External CSS</h1>
<p>This is an example of external CSS.</p>
</body>
</html>
```

**📄 style.css**

```css
h1 {
   color: purple;
   text-align: center;
}
p {
   color: orange;
   font-size: 20px;
}
```

### ✅ **Output**

The heading appears **purple and centered**, and the paragraph appears **orange and larger** — styles are fetched from an external file.

---

## 🧠 **5️⃣ Comparison Table**

| Feature         | Inline CSS     | Internal CSS    | External CSS         |
| --------------- | -------------- | --------------- | -------------------- |
| **Location**    | Inside element | Inside `<head>` | Separate `.css` file |
| **Scope**       | One element    | One HTML page   | Multiple HTML pages  |
| **Reusability** | ❌ No           | ❌ Limited       | ✅ High               |
| **Maintenance** | Hard           | Moderate        | Easy                 |
| **Priority**    | Highest        | Medium          | Lowest               |

---

## 🧩 **6️⃣ Advantages of Using CSS**

1. **Separation of content and design** – HTML for structure, CSS for styling.
2. **Improved maintainability** – One change in CSS reflects everywhere.
3. **Faster page loading** – External CSS reduces duplication.
4. **Consistency** – Ensures a uniform look across all pages.
5. **Better accessibility and device compatibility.**

---

## 🏁 **Conclusion**

CSS enhances the presentation and layout of web pages.
Among the three types:

* **Inline CSS** is quick but limited,
* **Internal CSS** is useful for single pages,
* **External CSS** is the most efficient for large websites.

Together, they make web design **modular, maintainable, and visually appealing**.

