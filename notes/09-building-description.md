# BUILDING DESCRIPTION

In this section, we build the description area of the hotel page. This part focuses on structuring content using Flexbox, creating multi-column lists, and styling SVG icons using modern CSS masking techniques.

## Topics Covered

In this section, you will learn:

- How to continue using Flexbox, including flex-wrap, to build a multi-column list
- How and why to use CSS masks with mask-image and mask-size
- How to color SVG icons using background-color combined with CSS masking

## Creating a Multi-Column Feature List

The feature list is displayed in two columns using Flexbox.
Instead of using floats or grid, we rely on flex-wrap to keep the layout flexible and responsive.

```scss
.list {
  list-style: none;
  margin: 3rem 0;
  padding: 3rem 0;

  border-top: var(--line);
  border-bottom: var(--line);

  display: flex;
  flex-wrap: wrap;

  &__item {
    flex: 0 0 50%;
    margin-bottom: 0.7rem;
  }

  &__item::before {
    content: "";
    display: inline-block;
    width: 1rem;
    height: 1rem;
    margin-right: 0.7rem;

    // Older browser
    // background-image: url(../img/SVG/chevron-thin-right.svg);
    // background-size: cover;

    // Newer Browser - mask
    background-color: var(--color-primary);
    mask-image: url(../img/SVG/chevron-thin-right.svg);
    mask-size: cover;
  }
}
```

**Key Concepts Used**

- flex-wrap: wrap allows list items to flow into multiple rows
- flex: 0 0 50% creates two equal-width columns
- Pseudo-elements (::before) are used to insert icons without extra markup

### Coloring SVG Icons with CSS Masks

Instead of using traditional background images, we use **CSS masking** to style SVG icons.

Why Use CSS Masks?

- Allows full control of icon color using background-color
- Works well with CSS variables and themes
- Keeps SVG files clean and reusable

The SVG acts as a mask, while the background-color defines the visible color.

### Building the Recommendation Section

The recommendation section shows how many people recommend the hotel and displays overlapping user avatars.

```scss
// Recommend
.recommend {
  font-size: 1.3rem;
  color: var(--color-grey-dark-3);

  display: flex;
  align-items: center;
  justify-content: space-between;
  &__count {
  }

  &__friends {
  }

  &__photo {
    box-sizing: border-box;
    height: 4rem;
    width: 4rem;
    border-radius: 50%;
    border: 3px solid #fff;

    &:not(:last-child) {
      margin-right: -1.5rem;
    }
  }
}
```

**Techniques Used Here**

- Flexbox for horizontal alignment and spacing
- Negative margins to create overlapping profile images
- box-sizing: border-box to keep borders from affecting layout size

[Next: Building user review](./10-building-user-review.md)
