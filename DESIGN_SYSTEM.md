# Walantu Design System

## Table of Contents
1. [Overview](#overview)
2. [Design Tokens](#design-tokens)
3. [Color Palette](#color-palette)
4. [Typography](#typography)
5. [Spacing System](#spacing-system)
6. [Layout & Grid](#layout--grid)
7. [Components](#components)
8. [Responsive Breakpoints](#responsive-breakpoints)
9. [Shadows & Effects](#shadows--effects)
10. [Form Elements](#form-elements)

---

## Overview

The Walantu design system provides a consistent foundation for building user interfaces. It is built on CSS custom properties (CSS variables) and follows a mobile-first responsive approach.

**Base Font Size:** 10px (1rem = 10px)  
**Primary Font Family:** Verdana, Geneva, Tahoma, sans-serif  
**Max Page Width:** 1200px

---

## Design Tokens

### CSS Custom Properties

```css
:root {
  --page-max: 1200px;
  --gutter: 2rem;
}
```

### Base Settings

- **Box Model:** `border-box` for all elements
- **Text Alignment:** Justified by default (`text-justify: inter-word`)
- **Body Layout:** CSS Grid with `auto 1fr auto` rows (header, main, footer)

---

## Color Palette

### Primary Colors

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| **Primary Red** | `#5b2121` | Links, headings, accents, footer background |
| **Primary Red Dark** | `rgb(82, 42, 15)` | Link hover state |
| **Primary Blue** | `#525f75` | Form headings, submit buttons |
| **Primary Blue Light** | `#8898aa` | Form labels, helper text |

### Background Colors

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| **White** | `#ffffff` | Primary background, cards, forms |
| **Pale Blue** | `#eaf2f7` | Main content background |
| **Light Blue** | `#cbdff8` | Article cards background |
| **Very Light Blue** | `#f5faff` | Intro section, testimonials background |
| **Light Gray** | `#f0f0f0` | Navigation hover state |

### Border Colors

| Color Name | Hex/RGBA | Usage |
|------------|----------|-------|
| **Border Gray** | `#ccc` | Default borders, form inputs |
| **Faded Red Border** | `rgba(250, 226, 226, 0.3)` | Main content, articles |
| **Red Border** | `rgba(200, 50, 50, 0.3)` | Article cards, intro sections |
| **Light Gray Border** | `#e6e6e6` | Card borders |

### Text Colors

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| **Text Black** | `#000000` | Primary text, navigation links |
| **Text White** | `#ffffff` | Text on dark backgrounds, header headings |
| **Text Dark Gray** | `#373535` | Text stroke/outline |
| **Text Red** | `#5b2121` | Links, headings, captions |

### Status Colors

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| **Success Green** | `green` | Valid form inputs |
| **Error Red** | `red` | Invalid form inputs |

---

## Typography

### Font Family

**Primary:** `Verdana, Geneva, Tahoma, sans-serif`  
**Secondary (Captions):** `georgia, serif` (italic)

### Font Sizes

| Element | Size (rem) | Size (px) | Line Height | Usage |
|---------|------------|-----------|-------------|-------|
| **HTML Base** | `1rem` | `10px` | - | Root font size |
| **Body** | `1.5rem` | `15px` | Default | Main content text |
| **H1** | `3rem` | `30px` | Default | Main headings (header) |
| **H2** | `2.8rem` | `28px` | Default | Section headings |
| **H2 (Form)** | `1.6rem` | `16px` | Default | Form section titles |
| **H3** | `1.6rem` | `16px` | Default | Testimonial names |
| **Label** | `1.2rem` | `12px` | Default | Form labels |
| **Helper Text** | `1.2rem` | `12px` | Default | Helper notes, captions |
| **Input/Button** | `1.4rem` | `14px` | Default | Form controls |
| **Figcaption** | `1rem` | `10px` | Default | Image captions |

### Font Weights

- **Normal:** `400` (default)
- **Bold:** `700` (headings, emphasis)

### Text Styles

#### H1 (Header)
```css
font-size: 3rem;
color: white;
-webkit-text-stroke: 0.5px #373535;
text-transform: uppercase;
```

#### H2
```css
font-size: 2.8rem;
text-align: left;
color: #525f75; /* in forms */
```

#### Links
```css
color: #5b2121;
/* Hover */
color: rgb(82, 42, 15);
text-decoration: none;
```

#### Captions
```css
font: italic 1rem georgia, serif;
color: #5b2121;
text-align: justify;
```

---

## Spacing System

### Base Unit
**Base:** `1rem` (10px)

### Spacing Scale

| Token | Value | Usage |
|-------|-------|-------|
| **xs** | `0.4rem` (4px) | Minimal spacing |
| **sm** | `0.5rem` (5px) | Tight spacing |
| **md** | `0.75rem` (7.5px) | Small gaps |
| **base** | `1rem` (10px) | Standard spacing |
| **lg** | `1.2rem` (12px) | Medium spacing |
| **xl** | `1.5rem` (15px) | Large spacing |
| **2x** | `2rem` (20px) | Extra large spacing (gutter) |
| **2.4rem** | `2.4rem` (24px) | Form padding |

### Common Spacing Patterns

- **Gutter:** `2rem` (20px)
- **Section Padding:** `2rem` (20px)
- **Card Padding:** `1.5rem` (15px) - `2rem` (20px)
- **Form Padding:** `24px`
- **Form Field Gap:** `8px`
- **Form Grid Gap:** `16px`
- **Grid Gap:** `2rem` (20px)
- **Button Padding:** `12px 18px`
- **Input Padding:** `10px 12px`

---

## Layout & Grid

### Page Structure

```css
/* Centered layout with max-width */
nav, header, main, footer {
  width: 100%;
  max-width: var(--page-max); /* 1200px */
  margin-inline: auto;
  position: relative;
}
```

### Grid Systems

#### 4-Column Grid (Primary)
```css
.grid-4 {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 2rem;
  align-items: stretch;
}
```

**Breakpoints:**
- Desktop: 4 columns
- ≤1200px: 3 columns
- ≤800px: 2 columns
- ≤600px: 1 column

#### 3-Column Grid
```css
main section {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 300px));
  gap: 2rem;
  justify-content: center;
}
```

**Breakpoints:**
- Desktop: 3 columns
- ≤900px: 2 columns
- ≤600px: 1 column

#### Form Grid
```css
.form-grid {
  display: grid;
  grid-template-columns: repeat(4, minmax(200px, 1fr));
  gap: 16px;
}
```

**Breakpoints:**
- Desktop: 4 columns
- ≤1100px: 3 columns
- ≤820px: 2 columns
- ≤560px: 1 column

### Container Utility

```css
.container {
  width: 100%;
  max-width: var(--page-max);
  margin-inline: auto;
  padding-inline: var(--gutter);
}
```

---

## Components

### Navigation

#### Desktop Navigation
```css
nav {
  background-color: white;
  box-shadow: 3px 3px 5px rgba(0, 0, 0, 0.1);
}

nav ul {
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

nav li {
  height: 50px;
}

nav a {
  padding: 0 30px;
  color: black;
}

nav a:hover {
  background-color: #f0f0f0;
}
```

#### Mobile Sidebar
```css
.sidebar {
  position: fixed;
  top: 0;
  right: 0;
  height: 100vh;
  width: 250px; /* 100% on ≤400px */
  background-color: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(12px);
  box-shadow: -10px 0 10px rgba(0, 0, 0, 0.1);
}
```

### Header/Hero

```css
header {
  background-color: #ffffff;
  color: #ffffff;
  padding: 2rem;
  background-image: url(../images/head-1.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  min-height: clamp(220px, 35vh, 420px);
}
```

**Responsive:**
- ≤800px: `padding: 1.2rem`, `min-height: clamp(180px, 40vh, 360px)`

### Cards

#### Standard Card
```css
.card {
  background: #fff;
  border: 1px solid #e6e6e6;
  border-radius: 8px;
  overflow: hidden;
  text-align: justify;
}

.card img {
  display: block;
  width: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  margin: 0;
}
```

#### Article Card
```css
main article {
  background-color: #cbdff8;
  border: 1px solid rgba(200, 50, 50, 0.3);
  padding: 2rem;
  margin-block: 2rem;
  border-radius: 6px;
  box-sizing: border-box;
}
```

#### Testimonial Card
```css
.testimonial {
  background: #ffffff;
  border-radius: 6px;
  padding: 1.5rem;
  text-align: justify;
  line-height: 1.6;
  box-shadow: 0 1px 3px rgba(0,0,0,0.05);
}
```

### Sections

#### Intro Section
```css
.intro {
  background-color: #f5faff;
  border: 1px solid rgba(200, 50, 50, 0.3);
  padding: 2rem;
  border-radius: 6px;
  box-sizing: border-box;
}
```

#### Main Content
```css
main {
  background-color: #eaf2f7;
  border: 1px solid rgba(250, 226, 226, 0.3);
  padding: 2rem;
  margin-block: 2rem;
  border-radius: 6px;
  box-sizing: border-box;
}
```

#### Testimonials Section
```css
.testimonials {
  background-color: #f5faff;
  border: 1px solid rgba(200, 50, 50, 0.3);
  padding: 2rem;
  margin-block: 2rem;
  border-radius: 6px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
}
```

**Breakpoints:**
- Desktop: 4 columns
- ≤1200px: 3 columns
- ≤900px: 2 columns
- ≤600px: 1 column

### Footer

```css
footer {
  background-color: #5b2121;
  color: #fff;
  text-align: justify;
  padding: 2rem;
  font-size: 1rem;
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 2rem;
  align-items: start;
}

footer a {
  color: #fff;
  opacity: 0.95;
}

footer a:hover {
  opacity: 1;
  text-decoration: underline;
}
```

**Breakpoints:**
- Desktop: 3 columns
- ≤900px: 2 columns
- ≤600px: 1 column

---

## Responsive Breakpoints

| Breakpoint | Max Width | Usage |
|------------|-----------|-------|
| **Mobile Small** | `400px` | Sidebar full-width |
| **Mobile** | `560px` | Form single column, full-width buttons |
| **Tablet Small** | `600px` | Grids collapse to 1 column |
| **Tablet** | `800px` | Navigation mobile menu, header adjustments |
| **Desktop Small** | `820px` | Form 2 columns |
| **Desktop Medium** | `900px` | 3-column sections to 2 columns |
| **Desktop Large** | `1100px` | Form 3 columns |
| **Desktop XL** | `1200px` | Max page width, 4-column grids to 3 columns |

### Media Query Pattern

```css
@media (max-width: 800px) {
  /* Mobile styles */
}

@media (max-width: 400px) {
  /* Small mobile styles */
}
```

---

## Shadows & Effects

### Box Shadows

#### Navigation Shadow
```css
box-shadow: 3px 3px 5px rgba(0, 0, 0, 0.1);
```

#### Sidebar Shadow
```css
box-shadow: -10px 0 10px rgba(0, 0, 0, 0.1);
```

#### Form/Card Shadow
```css
box-shadow: 0 1px 3px rgba(50,50,93,0.15),
            0 4px 6px rgba(112,157,199,0.15);
```

#### Testimonial Card Shadow
```css
box-shadow: 0 1px 3px rgba(0,0,0,0.05);
```

### Effects

#### Backdrop Filter (Sidebar)
```css
backdrop-filter: blur(12px);
```

#### Button Hover
```css
filter: brightness(1.05);
```

---

## Form Elements

### Form Container
```css
form {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 24px;
  max-width: 1200px;
  margin: 0 auto;
  background: white;
  box-shadow: 0 1px 3px rgba(50,50,93,0.15),
              0 4px 6px rgba(112,157,199,0.15);
}
```

### Form Field
```css
.form-field {
  display: flex;
  flex-direction: column;
  gap: 8px;
}
```

### Labels
```css
label {
  color: #8898aa;
  font-size: 12px;
  letter-spacing: .02em;
}
```

### Inputs, Selects, Textareas
```css
input, select, textarea, button {
  font-size: 14px;
  padding: 10px 12px;
  border: 1px solid #ccc;
  border-radius: 6px;
  outline: none;
  background: #fff;
}
```

### Validation States
```css
input:valid {
  border: 2px solid green;
}

input:invalid {
  border: 2px solid red;
}
```

### Textarea
```css
textarea {
  resize: vertical;
  min-height: 40px;
}
```

### Submit Button
```css
button[type="submit"] {
  background: #525f75;
  color: #fff;
  border: none;
  padding: 12px 18px;
  cursor: pointer;
  border-radius: 6px;
}

button[type="submit"]:hover {
  filter: brightness(1.05);
}
```

### Form Actions
```css
.actions {
  display: flex;
  justify-content: flex-end;
  gap: 12px;
}
```

### Grid Spans
```css
.span-2 { grid-column: span 2; }
.span-3 { grid-column: span 3; }
.span-4 { grid-column: 1 / -1; }
```

### Helper Text
```css
.helper {
  font-size: 12px;
  color: #8898aa;
  margin-top: 4px;
}
```

---

## Border Radius

| Element | Radius | Usage |
|---------|--------|-------|
| **Cards** | `8px` | Standard cards |
| **Forms** | `8px` | Form containers |
| **Buttons** | `6px` | All buttons |
| **Inputs** | `6px` | Form inputs |
| **Sections** | `6px` | Intro, articles, testimonials |

---

## Image Standards

### Aspect Ratio
- **Cards:** `16:9`
- **Responsive:** `max-width: 100%`, `height: auto`
- **Display:** `block`, `margin: 0 auto` (centered)

---

## Accessibility Considerations

### ARIA Labels
- Navigation: `aria-label="Primary"`
- Sidebar: `role="menu"`, `role="menuitem"`
- Sections: `aria-labelledby`
- Testimonials: `aria-label`

### Focus States
- Links remove underline on hover
- Buttons use brightness filter on hover
- Form inputs have validation states

### Semantic HTML
- Proper heading hierarchy (h1 → h2 → h3)
- Semantic elements (nav, header, main, footer, article, section)
- Form labels properly associated with inputs

---

## Usage Guidelines

### Do's
- ✅ Use design tokens (CSS variables) for consistent spacing and sizing
- ✅ Follow the responsive breakpoint system
- ✅ Maintain consistent color usage from the palette
- ✅ Use semantic HTML elements
- ✅ Apply proper ARIA labels for accessibility
- ✅ Follow the grid system for layouts

### Don'ts
- ❌ Don't use arbitrary color values outside the palette
- ❌ Don't skip responsive breakpoints
- ❌ Don't mix different spacing units inconsistently
- ❌ Don't override base font sizes without reason
- ❌ Don't use inline styles when classes are available

---

## Future Enhancements

### Recommended Additions
1. **Dark Mode Support** - Add color tokens for dark theme
2. **Animation Tokens** - Define transition durations and easing functions
3. **Component Variants** - Document button sizes, card variants
4. **Icon System** - Standardize icon usage and sizing
5. **Loading States** - Define skeleton loaders and spinners
6. **Error States** - Expand error messaging patterns
7. **Success States** - Define success feedback patterns

---

**Last Updated:** 2025  
**Version:** 1.0.0

