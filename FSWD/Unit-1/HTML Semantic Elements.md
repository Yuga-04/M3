

## ✨ HTML Semantic Elements – Explained with Examples

### ✅ What Are Semantic Elements?

Semantic elements in HTML clearly describe their meaning to both the browser and the developer. Unlike non-semantic elements (e.g., `<div>`, `<span>`), semantic tags convey the purpose of the content they enclose.

---

### 📌 Importance of Semantic Elements

- Improve **code readability** and **maintainability**
- Enhance **SEO** (Search Engine Optimization)
- Support **accessibility** tools like screen readers
- Facilitate **structured content** for better styling and scripting

---

### 🧩 Common Semantic Elements and Their Usage

| Semantic Tag | Purpose | Example |
|--------------|---------|---------|
| `<header>` | Represents introductory content or navigation links | `<header><h1>Welcome</h1></header>` |
| `<nav>` | Defines navigation links | `<nav><a href="/home">Home</a></nav>` |
| `<main>` | Specifies the main content of the document | `<main><h2>Article</h2><p>Content here</p></main>` |
| `<section>` | Groups related content | `<section><h3>Features</h3><ul><li>Fast</li></ul></section>` |
| `<article>` | Represents self-contained content | `<article><h2>Blog Post</h2><p>Text...</p></article>` |
| `<aside>` | Contains content indirectly related to the main content | `<aside><p>Related links</p></aside>` |
| `<footer>` | Defines footer content like copyright or contact info | `<footer><p>&copy; 2025 Ajitha</p></footer>` |
| `<figure>` | Wraps media content like images with captions | `<figure><img src="pic.jpg"><figcaption>Image caption</figcaption></figure>` |
| `<figcaption>` | Provides caption for `<figure>` | See above |
| `<mark>` | Highlights text | `<p>This is <mark>important</mark> info.</p>` |
| `<time>` | Represents a date/time | `<time datetime="2025-10-13">Oct 13, 2025</time>` |

---

### 🧠 Example: Semantic HTML Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Semantic Page</title>
</head>
<body>
  <header>
    <h1>My Portfolio</h1>
    <nav>
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
    </nav>
  </header>

  <main>
    <section id="about">
      <h2>About Me</h2>
      <p>I am a full stack developer...</p>
    </section>

    <section id="projects">
      <article>
        <h3>Project One</h3>
        <p>This project uses Node.js and Express.</p>
      </article>
    </section>
  </main>

  <aside>
    <h4>Contact Info</h4>
    <p>Email: ajitha@example.com</p>
  </aside>

  <footer>
    <p>&copy; 2025 Ajitha</p>
  </footer>
</body>
</html>
```

---

### 📚 Summary Table for Revision

| Tag | Description |
|-----|-------------|
| `<header>` | Top section, branding/navigation |
| `<nav>` | Navigation links |
| `<main>` | Central content |
| `<section>` | Thematic grouping |
| `<article>` | Independent content |
| `<aside>` | Sidebar or extra info |
| `<footer>` | Bottom section |
| `<figure>` | Media with caption |
| `<mark>` | Highlighted text |
| `<time>` | Date/time info |

