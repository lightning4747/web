

# 🧱 Common & Useful HTML Tags — Modern Reference

This guide lists the **most common HTML tags**, their **purpose**, and **how they are used in real-world development**.
Each section includes short explanations and examples following **HTML5 best practices**.

---

## 🏗️ 1. Structure & Metadata Tags

| Tag               | Purpose                                                                            | Example                        |
| ----------------- | ---------------------------------------------------------------------------------- | ------------------------------ |
| `<!DOCTYPE html>` | Defines the document type (HTML5). Should be at the top of every HTML file.        | `<!DOCTYPE html>`              |
| `<html>`          | Root element wrapping all content. Use `lang` attribute for accessibility and SEO. | `<html lang="en"> ... </html>` |
| `<head>`          | Holds metadata, title, links, scripts, styles — not visible in the browser.        | `<head> ... </head>`           |
| `<body>`          | Contains everything visible on the webpage.                                        | `<body> ... </body>`           |

### 🧩 Example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Web Page</title>
</head>
<body>
  <h1>Hello World!</h1>
</body>
</html>
```

---

## 📰 2. Text & Content Tags

| Tag             | Purpose                                                | Example                               |
| --------------- | ------------------------------------------------------ | ------------------------------------- |
| `<h1>` – `<h6>` | Headings (1 = most important, 6 = least).              | `<h1>Main Title</h1>`                 |
| `<p>`           | Paragraph — for text content.                          | `<p>This is a paragraph.</p>`         |
| `<span>`        | Inline container — for styling or small text sections. | `<span class="highlight">word</span>` |
| `<strong>`      | Indicates important text (usually bold).               | `<strong>Important!</strong>`         |
| `<em>`          | Emphasized text (usually italic).                      | `<em>Be careful</em>`                 |
| `<br>`          | Line break (no closing tag).                           | `Line one<br>Line two`                |
| `<hr>`          | Horizontal line divider.                               | `<hr>`                                |

---

## 🔗 3. Links & Navigation

| Tag     | Purpose                                  | Example                                   |
| ------- | ---------------------------------------- | ----------------------------------------- |
| `<a>`   | Creates a hyperlink.                     | `<a href="https://example.com">Visit</a>` |
| `<nav>` | Semantic container for navigation links. | `<nav><a href="#">Home</a></nav>`         |

### Example:

```html
<nav>
  <a href="#home">Home</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>
```

---

## 🖼️ 4. Images, Media & Visual Elements

| Tag            | Purpose                                                 | Example                                                                |
| -------------- | ------------------------------------------------------- | ---------------------------------------------------------------------- |
| `<img>`        | Displays an image. Requires `src` and `alt` attributes. | `<img src="photo.jpg" alt="A photo">`                                  |
| `<figure>`     | Groups media content with a caption.                    | `<figure><img src="pic.jpg"><figcaption>Caption</figcaption></figure>` |
| `<figcaption>` | Caption for a figure or image.                          | `<figcaption>Sunset view</figcaption>`                                 |
| `<video>`      | Embeds a video.                                         | `<video controls src="movie.mp4"></video>`                             |
| `<audio>`      | Embeds audio playback.                                  | `<audio controls src="song.mp3"></audio>`                              |

---

## 🧱 5. Sectioning & Layout

| Tag         | Purpose                                                 | Example                                  |
| ----------- | ------------------------------------------------------- | ---------------------------------------- |
| `<header>`  | Represents the header or top section of a page/section. | `<header><h1>Site Title</h1></header>`   |
| `<footer>`  | Represents footer or bottom section.                    | `<footer>© 2025 MySite</footer>`         |
| `<main>`    | Main unique content of the document.                    | `<main>...</main>`                       |
| `<section>` | Groups related content.                                 | `<section><h2>About Us</h2></section>`   |
| `<article>` | Self-contained piece (e.g., blog post).                 | `<article><h2>Post Title</h2></article>` |
| `<aside>`   | Sidebar or tangential content.                          | `<aside>Related links</aside>`           |
| `<div>`     | Generic container (block-level).                        | `<div class="box"></div>`                |

### Example:

```html
<main>
  <section id="about">
    <h2>About Us</h2>
    <p>We create modern websites.</p>
  </section>
  <aside>
    <h3>Resources</h3>
    <p>Learn HTML, CSS, and JS.</p>
  </aside>
</main>
```

---

## 🧮 6. Lists

| Tag    | Purpose                                   | Example                                          |
| ------ | ----------------------------------------- | ------------------------------------------------ |
| `<ul>` | Unordered (bulleted) list.                | `<ul><li>Item</li></ul>`                         |
| `<ol>` | Ordered (numbered) list.                  | `<ol><li>First</li></ol>`                        |
| `<li>` | List item inside `<ul>` or `<ol>`.        | `<li>Element</li>`                               |
| `<dl>` | Description list (term-definition pairs). | `<dl><dt>HTML</dt><dd>Markup language</dd></dl>` |

---

## 📋 7. Tables

| Tag                             | Purpose                              | Example                            |
| ------------------------------- | ------------------------------------ | ---------------------------------- |
| `<table>`                       | Defines a table.                     | `<table>...</table>`               |
| `<tr>`                          | Table row.                           | `<tr>...</tr>`                     |
| `<td>`                          | Table cell (data).                   | `<td>Cell</td>`                    |
| `<th>`                          | Table header cell (bold & centered). | `<th>Header</th>`                  |
| `<caption>`                     | Title/caption for the table.         | `<caption>Monthly Sales</caption>` |
| `<thead>`, `<tbody>`, `<tfoot>` | Group table sections.                | `<thead><tr>...</tr></thead>`      |

### Example:

```html
<table>
  <caption>Monthly Sales</caption>
  <thead>
    <tr><th>Month</th><th>Sales</th></tr>
  </thead>
  <tbody>
    <tr><td>January</td><td>$1000</td></tr>
  </tbody>
</table>
```

---

## 📄 8. Forms & Input

| Tag          | Purpose                                         | Example                                           |
| ------------ | ----------------------------------------------- | ------------------------------------------------- |
| `<form>`     | Collects user input.                            | `<form action="/submit" method="post">...</form>` |
| `<input>`    | User input field (text, email, password, etc.). | `<input type="text" name="username">`             |
| `<label>`    | Labels an input field (improves accessibility). | `<label for="email">Email</label>`                |
| `<textarea>` | Multi-line text input.                          | `<textarea></textarea>`                           |
| `<select>`   | Dropdown list.                                  | `<select><option>One</option></select>`           |
| `<option>`   | Item inside a dropdown.                         | `<option value="1">Option 1</option>`             |
| `<button>`   | Clickable button.                               | `<button type="submit">Send</button>`             |
| `<fieldset>` | Groups related form fields.                     | `<fieldset>...</fieldset>`                        |
| `<legend>`   | Caption for a `<fieldset>`.                     | `<legend>User Info</legend>`                      |

### Example:

```html
<form action="/register" method="post">
  <fieldset>
    <legend>Sign Up</legend>
    <label for="name">Name:</label>
    <input id="name" type="text" name="name" required>

    <label for="email">Email:</label>
    <input id="email" type="email" name="email" required>

    <button type="submit">Register</button>
  </fieldset>
</form>
```

---

## ⚙️ 9. Scripting & Linking

| Tag        | Purpose                                  | Example                                    |
| ---------- | ---------------------------------------- | ------------------------------------------ |
| `<script>` | Embeds or links JavaScript.              | `<script src="app.js"></script>`           |
| `<link>`   | Links external files (CSS, icons, etc.). | `<link rel="stylesheet" href="style.css">` |
| `<style>`  | Internal CSS block.                      | `<style>body { color: black; }</style>`    |

---

## 🧭 10. Semantic & Accessibility Tags

| Tag          | Purpose                               | Example                                           |
| ------------ | ------------------------------------- | ------------------------------------------------- |
| `<time>`     | Represents date/time values.          | `<time datetime="2025-10-26">Oct 26, 2025</time>` |
| `<mark>`     | Highlights text.                      | `<mark>Important term</mark>`                     |
| `<abbr>`     | Abbreviation with full form on hover. | `<abbr title="Cascading Style Sheets">CSS</abbr>` |
| `<code>`     | Inline code snippet.                  | `<code>console.log()</code>`                      |
| `<pre>`      | Preformatted text (preserves spaces). | `<pre>function test() {}</pre>`                   |
| `<progress>` | Shows progress bar.                   | `<progress value="70" max="100"></progress>`      |
| `<meter>`    | Displays a scalar measurement.        | `<meter value="0.6">60%</meter>`                  |

---

## 📦 11. Multimedia & Interactive Elements

| Tag         | Purpose                                      | Example                                                             |
| ----------- | -------------------------------------------- | ------------------------------------------------------------------- |
| `<iframe>`  | Embeds another page (e.g., YouTube video).   | `<iframe src="https://example.com"></iframe>`                       |
| `<canvas>`  | For drawing graphics via JavaScript.         | `<canvas id="game"></canvas>`                                       |
| `<details>` | Expandable/collapsible content.              | `<details><summary>More info</summary><p>Hidden text</p></details>` |
| `<summary>` | The visible label for a `<details>` element. | `<summary>Click me</summary>`                                       |

---

## 🧠 Final Notes

✅ **Use semantic tags** — improves SEO & accessibility.
✅ **Validate your HTML** at [validator.w3.org](https://validator.w3.org/).
✅ **Always include `alt`** for images.
✅ **Keep your HTML readable** — indentation, lowercase tags, and proper nesting.
✅ **Combine with CSS and JS** for layout and interactivity.

---

> **“Structure defines meaning. Style defines beauty. Behavior defines life.”**
> — A Web Developer’s Motto 🌐

---

