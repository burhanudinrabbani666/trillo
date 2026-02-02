# BUILDING HOTEL OVERVIEW

In this section, we build the hotel overview component. This part focuses on layout alignment using Flexbox, spacing techniques with margin: auto, and adding subtle animations to improve interactivity and user feedback.

## Topics Covered

In this section, you will learn:

- How to create infinite CSS animations
- How to use margin: auto with Flexbox—and why it is so powerful
- How to continue using Flexbox properties for easy positioning and alignment

### Creating the Gallery and Initial Star Layout

The gallery and hotel information (such as stars and rating) are placed inside a Flexbox container.
To create space between elements without changing their widths, we use `margin-right: auto`.

Using `margin: auto` for Flexible Spacing

```scss
&__stars {
  margin-right: auto; // this automaticlly calculate the margin
}
```

**Why This Works**

- margin-right: auto pushes the following elements to the far right
- The width of the stars element remains unchanged
- This technique avoids hard-coded spacing and adapts naturally to different screen sizes

This is one of the most powerful spacing techniques when working with Flexbox.

## Creating the Rating Section

The rating section is visually separated from the rest of the content and aligned vertically.
To achieve this, we combine align-self: stretch with Flexbox centering and a column layout.

```scss
&__rating {
  background-color: var(--color-primary);
  margin-left: 3rem;
  color: #fff;

  align-self: stretch;
  padding: 0 2.4rem;

  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

&__rating-avarage {
  font-size: 2.25rem;
  font-weight: 300;
  margin-bottom: -0.5rem;
}

&__rating-count {
  font-size: 1.4rem;
}
```

**Key Concepts Used**

- align-self: stretch makes the rating box fill the full height of its parent
- flex-direction: column stacks text vertically
- Flexbox centering ensures consistent alignment regardless of content size

### Creating the Animated Button

The inline button uses an infinite animation to provide visual feedback when focused.
This helps highlight interactive elements, especially for keyboard navigation.

```scss
// Button
.btn-inline {
  border: none;
  color: var(--color-primary);
  font-size: inherit;

  border-bottom: 1px solid currentColor;
  padding: 2px;
  display: inline-block;
  background-color: transparent;
  cursor: pointer;

  transition: color 0.3s;

  &:hover {
    color: var(--color-grey-dark-1);
  }

  &:focus {
    outline: none;
    animation: pulState 1s infinite;
  }
}

@keyframes pulState {
  0% {
    transform: scale(1.45rem);
    box-shadow: none;
  }

  50% {
    transform: scale(1.05rem);
    box-shadow: 0 1rem 4rem rgba(0, 0, 0, 0.25);
  }

  100% {
    transform: scale(1rem);
    box-shadow: none;
  }
}
```

Why This Animation Is Effective

- The animation runs infinitely while the button is focused
- Subtle scaling and shadow changes draw attention without being distracting
- Improves accessibility by clearly indicating focus state

[Next: Building description](./09-building-description.md)
