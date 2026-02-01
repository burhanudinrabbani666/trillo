# BUILDING HEADER

Topics Covered

By the end of this section, you will understand:

- Why SVG icons are preferred over font icons
- How to find, generate, and use SVG sprites in HTML
- How to style and change SVG icons using CSS
- How to apply advanced Flexbox alignment techniques, including:
  - `justify-content`
  - `align-items`
  - `align-self`
  - flexible sizing with `flex`

---

### Why Use SVG Icons Instead of PNG or Font Icons?

We replace PNG icons with SVGs to improve accessibility, performance, and styling flexibility.

**Benefits of SVG icons:**

- Easier for browsers and screen readers to interpret
- Scales perfectly on all screen sizes without losing quality
- Can be styled directly with CSS (e.g. color, size, hover effects)
- Smaller file size when using SVG sprites

**Using an SVG Sprite**

Instead of loading multiple icon files, we use a single SVG sprite file and reference individual icons using the `<use>` element.

```html
<svg class="search__icon">
  <use xlink:href="img/sprite.svg#icon-magnifying-glass"></use>
</svg>
```

This approach improves performance and keeps icon management clean and centralized.

### Building the Search Component

The search component consists of:

- An input field
- A button placed inside the input area
- A smooth focus animation

Flexbox is used to center and align elements horizontally and vertically.

```scss
.search {
  flex: 0 0 40%;

  display: flex;
  align-items: center;
  justify-content: center;

  &__input {
    font-family: inherit;
    font-size: inherit;
    color: inherit;

    background-color: var(--color-grey-light-2);
    border: none;
    padding: 0.7rem 2rem;
    border-radius: 200px;
    width: 90%;
    margin-right: -3.25rem;

    transition: all 0.3s;

    &:focus {
      outline: none;
      width: 100%;
      background-color: var(--color-grey-light-3);
    }

    &::-webkit-input-placeholder {
      font-weight: 100;
      color: var(--color-grey-light-4);
    }
  }

  &__input:focus + &__button {
    background-color: var(--color-grey-light-3);
  }

  &__button {
    border: none;
    background-color: var(--color-grey-light-2);

    &:focus {
      outline: none;
    }

    &:active {
      transform: translateY(2px);
    }
  }

  &__icon {
    height: 2rem;
    width: 2rem;

    fill: var(--color-grey-dark-3);
  }
}
```

**Key Concepts Used Here**

- Negative margin to place the button inside the input
- Sibling selector (+) to react to input focus
- SVG fill property to control icon color via CSS
- Smooth transitions for better user experience

### Creating the User Navigation

The user navigation includes:

- Notification icons
- A user profile image
- Hover interactions

To make the navigation items fill the entire height of the header, we override the default alignment behavior using `align-self: stretch.`

```scss
.user-nav {
  align-self: stretch;

  display: flex;
  align-items: center;

  & > * {
    padding: 0 2rem;
    cursor: pointer;
    height: 100%;

    display: flex;
    align-items: center;

    transition: all 0.3s;
  }

  & > *:hover {
    background-color: var(--color-grey-light-2);
  }

  &__icon-box {
    position: relative;
  }

  &__icon {
    height: 2.25rem;
    width: 2.25rem;

    fill: var(--color-grey-dark-2);
  }

  &__notification {
    font-size: 0.8rem;
    height: 1.75rem;
    width: 1.75rem;

    border-radius: 100px;
    background-color: var(--color-primary);
    color: #fff;

    position: absolute;
    top: 1.5rem;
    right: 1.1rem;

    display: flex;
    justify-content: center;
    align-items: center;
  }

  &__user-photo {
    height: 3.75rem;
    width: 3.75rem;
    border-radius: 50%;

    margin-right: 1rem;
  }
}
```

**Important Flexbox Techniques Used**

- `align-self: stretch` to make navigation items fill the header height
- Nested Flexbox for icon and text alignment
- Absolute positioning for notification badges
- Hover states applied consistently across child elements

**What You’ve Learned So Far**

How to replace PNG icons with SVGs for better accessibility
How to use SVG sprites efficiently
How to style SVG icons using CSS
How to build complex header layouts using Flexbox
How to override default alignment behavior with `align-self`

[Next: Building navigation](./07-building-nav.md)
