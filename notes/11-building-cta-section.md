# Building the CTA Section

This section demonstrates how to create a modern call-to-action button with an animated hover effect where text slides vertically.

## Overview

The CTA (Call-to-Action) section features a button with a sophisticated hover animation. When users hover over the button, the visible text slides down while hidden text slides up to replace it, creating a smooth vertical transition effect.

## Section Structure

```scss
.cta {
  padding: 3.5rem 0;
  text-align: center;

  &__book-now {
    text-transform: uppercase;
    font-size: 1.5rem;
    font-weight: 300;
    margin-bottom: 2.5rem;
  }
}
```

The `.cta` section is centered with vertical padding, while the `__book-now` heading provides context above the button.

## Button Base Styles

```scss
.btn {
  font-size: 1.5rem;
  font-weight: 300;
  text-transform: uppercase;
  border-radius: 200px;
  border: none;
  background-image: linear-gradient(
    to right,
    var(--color-primary-light),
    var(--color-primary-dark)
  );
  color: #fff;
  position: relative;
  overflow: hidden; /* Critical: hides the off-screen text */
  cursor: pointer;
```

**Key points:**

- `position: relative` - Enables absolute positioning for child elements
- `overflow: hidden` - Hides the text positioned outside the button boundaries
- Gradient background flows from left to right

## Text Container Setup

```scss
& > * {
  display: inline-block;
  height: 100%;
  width: 100%;
  transition: all 0.2s;
}
```

All direct children are set to `inline-block` with full dimensions and smooth transitions for the animation effect.

## Visible and Hidden Text

```scss
&__visible {
  padding: 2rem 7.5rem;
}

&__unvisible {
  position: absolute;
  padding: 2rem 0;
  left: 0;
  top: -100%; /* Positioned above the button, out of view */
}
```

- `__visible` - The default text shown to users, with horizontal padding for button width
- `__unvisible` - Positioned 100% above the button (hidden by `overflow: hidden`)

## Hover Effects

```scss
&:hover {
  background-image: linear-gradient(
    to left,
    /* Reversed gradient direction */ var(--color-primary-light),
    var(--color-primary-dark)
  );
}

&:hover &__visible {
  transform: translateY(100%); /* Slides down out of view */
}

&:hover &__unvisible {
  top: 0; /* Slides down into view */
}
```

**Animation sequence:**

1. Gradient reverses direction (left to right becomes right to left)
2. Visible text slides down 100% (disappears below)
3. Hidden text slides from top (-100%) to center (0)

## Focus State

```scss
  &:focus {
    outline: none;
    animation: pulState 1s infinite;
  }
}
```

Removes the default outline and applies a pulsing animation for keyboard navigation accessibility.

## HTML Structure Example

```html
<section class="cta">
  <h2 class="cta__book-now">Book now</h2>
  <button class="btn">
    <span class="btn__visible">Book now</span>
    <span class="btn__unvisible">Only 4 rooms left</span>
  </button>
</section>
```

---

[Next: Writing media queries](./12-writing-media-query.md)
