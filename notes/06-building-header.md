# BUILDING HEADER

**topics:**

- Why to use SVG icons vs font icons
- How to find, generate and use SVG .sprites in HTML.
- How to change of an SVG icon in CSS.
- How to use more advanced felxbox alignment technique, including justify-content, align-items, align-slef and flex.

---

Change the PNG icon to SVG for accessibility. SVG is easier for browsers to read.

```html
<svg class="search__icon">
  <use xlink:href="img/sprite.svg#icon-magnifying-glass"></use>
</svg>
```

Creating simple search input with the button inside field

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
