
# 🌐 HTML & CSS Basics — Modern Standards & Best Practices

This document gives you a **clean, modern overview** of HTML & CSS fundamentals with **proper structure, accessibility, and best practices**.

---

## 🧱 1. HTML Structure

Modern HTML should be **semantic**, **accessible**, and **organized**.

### ✅ Example Layout

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="A modern HTML and CSS example following best practices.">
  <title>Modern HTML & CSS Example</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header class="site-header">
    <nav class="navbar" aria-label="Main navigation">
      <a href="/" class="logo">BrandName</a>
      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section id="home" class="hero">
      <h1>Welcome to Modern Web Design</h1>
      <p>Learn how to write clean and accessible HTML and CSS.</p>
      <a href="#about" class="btn-primary">Get Started</a>
    </section>

    <section id="about" class="about">
      <h2>About</h2>
      <p>We follow semantic HTML and responsive CSS to create better web experiences.</p>
    </section>
  </main>

  <footer class="site-footer">
    <p>&copy; 2025 BrandName. All rights reserved.</p>
  </footer>
</body>
</html>
```

---

## 🎨 2. CSS Basics (Modern Best Practices)

CSS should be **modular**, **readable**, and **responsive**.

### ✅ Example Stylesheet — `styles.css`

```css
/* 1️⃣ Reset & Base Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
  line-height: 1.6;
  color: #333;
  background-color: #fafafa;
}

/* 2️⃣ Layout & Structure */
header, footer {
  background: #fff;
  border-bottom: 1px solid #eaeaea;
  padding: 1rem 2rem;
}

/* 3️⃣ Navigation */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1rem;
}

.nav-links a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  transition: color 0.2s ease-in-out;
}

.nav-links a:hover {
  color: #0070f3;
}

/* 4️⃣ Hero Section */
.hero {
  text-align: center;
  padding: 5rem 2rem;
  background: linear-gradient(135deg, #0070f3, #00b4d8);
  color: #fff;
}

.hero h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.btn-primary {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background: #fff;
  color: #0070f3;
  border-radius: 0.5rem;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn-primary:hover {
  background: #eaeaea;
  transform: translateY(-2px);
}

/* 5️⃣ Responsive Design */
@media (max-width: 768px) {
  .nav-links {
    flex-direction: column;
    gap: 0.5rem;
  }

  .hero h1 {
    font-size: 2rem;
  }
}
```

---

## 🧩 3. HTML Best Practices

- ✅ Always use **semantic tags** (`<header>`, `<main>`, `<footer>`, `<section>`, etc.)
- ✅ Use **alt attributes** for images.
- ✅ Keep your HTML **indented and readable**.
- ✅ Use **`aria-labels`** for accessibility when needed.
- ✅ Separate structure (HTML) and style (CSS).

---

## 🎨 4. CSS Best Practices

- ✅ Use **flexbox or grid** for layout — no floats.
- ✅ Keep **consistent units** (`rem`, `%`, `vh/vw` — avoid mixing too many).
- ✅ Follow a **naming convention** (like BEM or kebab-case).
- ✅ Prefer **mobile-first** responsive design.
- ✅ Use **CSS variables** for colors, spacing, and typography.

```css
:root {
  --primary-color: #0070f3;
  --text-color: #333;
  --border-radius: 0.5rem;
}
```

---

## ⚙️ 5. Project Structure

```
project/
├── index.html
├── styles.css
└── assets/
    ├── images/
    └── icons/
```

---

## 🚀 6. Final Notes

- Test your site with **Lighthouse** for accessibility and performance.
- Validate your HTML with [W3C Validator](https://validator.w3.org/).
- Use **Prettier or ESLint** to keep code clean and consistent.
- Consider using **CSS frameworks** (Tailwind, Bootstrap) once you’re solid with vanilla CSS.

---

🧠 *Learn the rules like a pro, so you can break them like an artist.*  
— Pablo Picasso
