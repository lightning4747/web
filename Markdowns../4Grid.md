````markdown
# 🧩 CSS GRID — COMPLETE NOTES  

CSS Grid is a **two-dimensional layout system** that gives full control over **rows and columns**, allowing precise placement of items and complex responsive designs.  
Unlike Flexbox (which is one-dimensional), Grid can handle **both directions simultaneously**.

---

## 🏗️ 1. Basic Grid Setup

### 📦 Container Code
```css
.container {
  display: grid;                 /* Enables grid layout */
  border: 3px solid rgb(54, 16, 144);
  padding: 10px;
  grid-auto-columns: 200px;      /* Implicit columns */
  grid-auto-rows: 200px;         /* Implicit rows */
  justify-items: center;         /* Aligns content horizontally inside each cell */
  align-items: center;           /* Aligns content vertically inside each cell */
  gap: 1em;                      /* Space between items */
}
````

### 🧱 Item Code

```css
.items {
  padding: 2em;
  width: 100px;
  height: 100px;
  background-color: aquamarine;
  border: 2px solid black;
  border-radius: 7px;
  font-weight: bold;
  font-family: 'Courier New', Courier, monospace;
  font-style: italic;
  transition: all 0.5s ease;
}

.items:hover {
  background-color: rgb(70, 185, 147);
  cursor: grab;
}

.items:active {
  background-color: bisque;
  cursor: grabbing;
}
```

✅ **Result:** A clean, centered grid layout with hover/active interactions.

---

## 🧩 2. Implicit vs Explicit Grid

* **Explicit Grid** — Defined manually using `grid-template-columns` or `grid-template-rows`
* **Implicit Grid** — Automatically created when grid items overflow the defined structure

```css
.container {
  grid-template-columns: repeat(3, 1fr); /* Explicit */
  grid-auto-rows: 200px;                /* Implicit rows for overflow items */
}
```

---

## 💡 3. Important Grid Functions

### 🔹 `repeat()`

Creates repeated columns or rows:

```css
grid-template-columns: repeat(3, 1fr);
```

### 🔹 `minmax()`

Sets minimum and maximum track sizes:

```css
grid-template-columns: repeat(3, minmax(150px, 1fr));
```

### 🔹 `auto-fit` & `auto-fill`

Used for **responsive grid layouts**:

```css
grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
```

* `auto-fit`: Collapses empty columns, fits tightly around content.
* `auto-fill`: Keeps the grid pattern even if some tracks are empty.

---

## 🧱 4. Placing Grid Items

You can position elements using **grid line numbers** or **named areas**.

### 📐 Line-based placement:

```css
.item1 {
  grid-column: 1 / 3;  /* spans across two columns */
  grid-row: 1 / 2;     /* occupies the first row */
}
```

### 📑 Named area placement:

```css
.container {
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.footer  { grid-area: footer; }
```

---

## 🍱 5. The Bento Grid

A **Bento Grid** is a creative use of CSS Grid that mimics the style of a **Japanese Bento box** — an asymmetric grid with elements of different shapes and sizes.

It’s ideal for **dashboards, portfolios, and aesthetic UI layouts**.

### 🧩 Example:

#### 📦 Container Code

```css
.container {
  display: grid;
  grid-auto-columns: 200px;
  grid-auto-rows: 200px;
  gap: 1em;
  grid-template-areas:
    "box1 box1 box1 box3"
    "box2 box4 box5 box5";
}
```

#### 🧱 Items Code

```css
.item-1 { grid-area: box1; }
.item-2 { grid-area: box2; }
.item-3 { grid-area: box3; }
.item-4 { grid-area: box4; }
.item-5 { grid-area: box5; }
```

🧭 **Result:**

* Item 1 spans three columns on the top row.
* Item 5 spans two columns on the bottom row.
* Perfect for showcasing **asymmetric visual layouts**.

---

## ⚙️ 6. Grid Auto Flow

```css
grid-auto-flow: row | column | dense;
```

* `row`: Fills items by rows (default)
* `column`: Fills items by columns
* `dense`: Backfills smaller items into empty spaces for tighter packing

---

## 🎯 7. Grid Stack (Overlapping Items)

Grid allows **layering** elements by assigning them the same grid area:

```css
.item1 { grid-area: 1 / 1 / 2 / 2; }
.item2 { grid-area: 1 / 1 / 2 / 2; z-index: 2; }
```

Useful for overlays, blur backgrounds, or animations.

---

## 📱 8. Responsive Techniques

Combine **Grid** with **media queries** for mobile-first responsiveness:

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1em;
}

@media (max-width: 768px) {
  .container {
    grid-template-columns: 1fr; /* Single column for small screens */
  }
}
```

💡 Use `auto-fit` with `minmax()` to automatically resize items without breaking the grid.

---

## ⚖️ 9. Grid vs Flexbox

| Feature          | CSS Grid                                | Flexbox                             |
| ---------------- | --------------------------------------- | ----------------------------------- |
| Layout Direction | 2D (rows + columns)                     | 1D (row or column)                  |
| Control          | Precise track & area control            | Best for content flow               |
| Ideal Use        | Page layouts, dashboards, bento designs | Navigation bars, buttons, alignment |
| Responsiveness   | `auto-fit`, `minmax`                    | `flex-wrap`, `justify-content`      |

✅ **Pro Tip:** Use **Grid for overall layout** and **Flexbox inside each grid item** for element alignment.

---

## 🧭 10. Helpful Techniques

| Technique                           | Description                                   |
| ----------------------------------- | --------------------------------------------- |
| `place-items: center;`              | Centers all items vertically and horizontally |
| `gap`                               | Adds consistent spacing between items         |
| `minmax()` + `auto-fit`             | Makes grids responsive                        |
| `grid-template-areas`               | Creates visual structure using names          |
| `grid-auto-rows`                    | Controls implicit rows                        |
| `justify-content` + `align-content` | Aligns the entire grid in the container       |

---

## 🧾 Example: Responsive Bento Grid

```css
.container {
  display: grid;
  grid-template-areas:
    "box1 box1 box1 box3"
    "box2 box4 box5 box5";
  grid-auto-rows: minmax(150px, auto);
  gap: 1rem;
}

@media (max-width: 768px) {
  .container {
    grid-template-areas:
      "box1"
      "box2"
      "box3"
      "box4"
      "box5";
  }
}
```

---

## ✅ Summary

* **Grid** is best for complex, 2D, or asymmetric layouts (like Bento grids).
* Use **Flexbox inside Grid** for better control of inner content.
* Use **`auto-fit`**, **`minmax()`**, and **named areas** for responsive and scalable designs.
* Ideal for **dashboards, galleries, portfolios, landing pages**, and **structured UI systems**.

---

```html
<!-- <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0 ;
            padding: 0;
        }

        body {
            background-color: cornflowerblue;
            height: 100vh;
            display: grid;
            justify-content: center;
            align-content: center;
        }

        .container {
            border: 3px solid rgb(54, 16, 144);
            padding:10px;
            display: grid;
            grid-auto-columns: 200px; /*implicite grid*/
            /* grid-auto-flow:;  */
            grid-auto-rows:200px;
            justify-items:center ;
            align-items: center;
            justify-content: baseline;
            align-items: center;
            gap: 1em;
            
        }
        .items {
            padding: 2em;
            width: 100px;
            height: 100px;
            background-color: aquamarine;
            border: 2px solid black;
            border-radius: 7px;
            font-weight: bolder;
            font-family: 'Courier New', Courier, monospace;
            font-style: italic;
            transition:all 0.5s ease ;
            
        }
        .items:hover {
            background-color: rgb(70, 185, 147);
            cursor:grab;
        }
        .items:active{
            cursor: grabbing;
            background-color: bisque;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="items item-1">item-1</div>
        <div class="items item-2">item-2</div>
        <div class="items item-3">item-3</div>
        <div class="items item-4">item-4</div>
        <div class="items item-5">item-5</div>
        <div class="items item-6">item-6</div>
        <div class="items item-7">item-7</div>
        <div class="items item-8">item-8</div>
        <div class="items item-9">item-9</div>
        <div class="items item-9">item-10</div>
        <div class="items item-9">item-11</div>
    </div>
</body>
</html> -->

<!-- bento grid -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0 ;
            padding: 0;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 2%;

        }

        .container {
            
            
            display: grid;
            grid-auto-columns: 200px;
            grid-auto-rows: 200px ;
            gap:1em;
            grid-template-areas:
            "box1 box1 box1 box3"
            "box2 box4 box5 box5 " ;
        }
        .items {
            padding: 2em;
            /* width: 100px; */
            /* height: 100px; */
            background-color: aquamarine;
            border: 2px solid black;
            border-radius: 7px;
            font-weight: bolder;
            font-family: 'Courier New', Courier, monospace;
            font-style: italic;
            transition:all 0.5s ease ;
            
        }
        .items:hover {
            background-color: rgb(70, 185, 147);
            cursor:grab;
        }
        .items:active{
            cursor: grabbing;
            background-color: bisque;
        }
          .item-1 { grid-area: box1; }
        .item-2 { grid-area: box2; }
        .item-3 { grid-area: box3; }
        .item-4 { grid-area: box4; }
        .item-5 { grid-area: box5; }
    </style>
</head>
<body>
    <div class="container">
        <div class="items item-1">item-1</div>
        <div class="items item-2">item-2</div>
        <div class="items item-3">item-3</div>
        <div class="items item-4">item-4</div>
        <div class="items item-5">item-5</div>
        
    </div>
</body>
</html>
```
---

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>CSS Grid Master Demo</title>

  <style>
    /* ========= GLOBAL RESET ========= */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background: linear-gradient(135deg, #c6d5f9, #e8f0ff);
      font-family: "Courier New", Courier, monospace;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
      min-height: 100vh;
      padding: 2rem;
      gap: 3rem;
    }

    h1, h2 {
      text-align: center;
      margin-bottom: 0.5rem;
      font-style: italic;
    }

    /* ========= COMMON ITEM STYLE ========= */
    .items {
      background-color: aquamarine;
      border: 2px solid black;
      border-radius: 7px;
      padding: 2em;
      font-weight: bolder;
      font-style: italic;
      text-align: center;
      transition: all 0.5s ease;
    }

    .items:hover {
      background-color: rgb(70, 185, 147);
      cursor: grab;
    }

    .items:active {
      cursor: grabbing;
      background-color: bisque;
    }

    /* ========= SECTION 1: IMPLICIT GRID ========= */
    .implicit-container {
      border: 3px solid rgb(54, 16, 144);
      padding: 10px;
      display: grid;
      grid-auto-columns: 200px;   /* Implicit column width */
      grid-auto-rows: 200px;      /* Implicit row height */
      justify-items: center;      /* Centers items horizontally */
      align-items: center;        /* Centers items vertically */
      gap: 1em;                   /* Space between cells */
      background-color: #dfe9ff;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    /* ========= SECTION 2: BENTO GRID ========= */
    .bento-container {
      display: grid;
      grid-template-columns: repeat(4, 200px);
      grid-template-rows: 200px 200px;
      gap: 1em;
      grid-template-areas:
        "box1 box1 box1 box3"
        "box1 box4 box5 box5";
      background-color: #e5fff8;
      border: 3px solid rgb(0, 150, 136);
      padding: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    .item-1 { grid-area: box1; background-color: #a8edea; }
    .item-2 { grid-area: box2; background-color: #f9f871; } /* not used in template */
    .item-3 { grid-area: box3; background-color: #ffd6a5; }
    .item-4 { grid-area: box4; background-color: #bdb2ff; }
    .item-5 { grid-area: box5; background-color: #ffadad; }

    /* ========= OPTIONAL RESPONSIVE ADJUSTMENT ========= */
    @media (max-width: 900px) {
      .bento-container {
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
        grid-template-areas: none;
      }
      .items {
        grid-area: auto !important;
      }
    }
  </style>
</head>

<body>

  <h1>🎯 CSS GRID MASTER DEMO</h1>

  <!-- ========== IMPLICIT GRID SECTION ========== -->
  <section>
    <h2>1️⃣ Implicit Grid Layout</h2>
    <p style="text-align:center; margin-bottom:1rem;">
      Browser auto-creates columns & rows using <code>grid-auto-columns</code> and <code>grid-auto-rows</code>
    </p>

    <div class="implicit-container">
      <div class="items">item-1</div>
      <div class="items">item-2</div>
      <div class="items">item-3</div>
      <div class="items">item-4</div>
      <div class="items">item-5</div>
      <div class="items">item-6</div>
      <div class="items">item-7</div>
      <div class="items">item-8</div>
      <div class="items">item-9</div>
      <div class="items">item-10</div>
      <div class="items">item-11</div>
    </div>
  </section>

  <!-- ========== BENTO GRID SECTION ========== -->
  <section>
    <h2>2️⃣ Bento Grid Layout (Named Areas)</h2>
    <p style="text-align:center; margin-bottom:1rem;">
      Custom layout using <code>grid-template-areas</code> for a modern Bento-style design
    </p>

    <div class="bento-container">
      <div class="items item-1">item-1</div>
      <div class="items item-2">item-2</div>
      <div class="items item-3">item-3</div>
      <div class="items item-4">item-4</div>
      <div class="items item-5">item-5</div>
    </div>
  </section>

</body>
</html>

```
---