# BUILDING NAVIGATION SIDE BAR

In this section, we build the sidebar navigation for the application. The focus is on layout structure, smooth hover animations, and scalable icon styling. We rely heavily on Flexbox and modern CSS features to create a clean and interactive sidebar.

## Topics Covered

In this section, you will learn:

- How to use scaleY() and multiple transition properties with different timing settings to create a creative hover animation
- How and why to use the currentColor CSS variable
- How to apply more advanced Flexbox alignment techniques, including:
  - flex-direction
  - justify-content
  - align-items

### Setting Up the Sidebar Layout

The sidebar is a vertical layout that contains:

- The navigation menu at the top
- Legal or footer text at the bottom

To achieve this, we use flex-direction: column and justify-content: space-between.
This allows us to distribute elements vertically inside the sidebar.

**Key Concepts Used**

- flex-direction: column changes the main axis to vertical
- justify-content: space-between pushes the first element to the top and the last element to the bottom
- Fixed flex basis (18%) keeps the sidebar width consistent

```scss
.sidebar {
  background-color: var(--color-grey-dark-1);

  flex: 0 0 18%;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
```

### Styling the Navigation List

The navigation list is where most of the interaction happens.
We create a smooth and modern hover effect using:

- The ::before pseudo-element
- The scaleY() transform
- Multiple transitions with different durations and delays

```scss
.side-nav {
  font-size: 1.4rem;
  list-style: none;
  margin-top: 3.5rem;

  &__item {
    position: relative;

    &:not(:last-child) {
      margin-bottom: 0.5rem;
    }
  }

  &__item::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;

    height: 100%;
    width: 3px;
    background-color: var(--color-primary);
    transform: scaleY(0);
    transition:
      transform 0.4s,
      width 0.4s cubic-bezier(1, 0, 0, 1) 0.4s,
      background-color 0.1s;
  }

  &__item:hover::before,
  &__item--active::before {
    transform: scaleY(1);
    width: 100%;
  }

  &__item:active::before {
    background-color: var(--color-primary-light);
  }

  &__link:link,
  &__link:visited {
    color: var(--color-grey-light-1);
    text-decoration: none;
    text-transform: uppercase;

    display: inline-block;
    padding: 1.5rem 3rem;

    position: relative;
    z-index: 10;

    display: flex;
    align-items: center;
  }

  &__icon {
    width: 1.75rem;
    height: 1.75rem;

    margin-right: 2rem;
    fill: currentColor;
  }
}

// Legal text
.legal {
  font-size: 1.2rem;
  text-align: center;
  padding: 2.5rem;

  color: var(--color-grey-light-4);
}
```

### Creating the Hover Animation with scaleY()

The hover effect is built using a pseudo-element that starts with scaleY(0) and expands to scaleY(1) on hover.

**Why This Works Well**

- scaleY() animates from the center, creating a smooth reveal effect
- Multiple transitions allow different properties to animate independently
- The delayed width transition adds a layered, polished animation feel

This technique avoids layout shifts and keeps animations performant.

---

**Using currentColor for Icon Styling**

The icons inside the navigation links use `fill: currentColor`.

**Why currentColor Is Useful**

- Icons automatically inherit the text color
- No need to manually update icon colors on hover or active states
- Makes theme changes easier and more consistent

This keeps icons and text visually synchronized at all times.

[Next: Building hotel overview](./08-building-hotel-overview.md)
