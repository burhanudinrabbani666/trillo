# BUILDING NAV

topics:

- How to use `scaleY` and multiaple transition properties with different settings, to create a creative hover effect
- How and why use the `currentColor` CSS variable
- How to use some more advanced flexbox alignmet techniques, including `flex-direction`, `justify-content` and `align-items`

### Set initial side bar

using `flex-direction: column` for make `justify-between: space-between` vertical

```scss
.sidebar {
  background-color: var(--color-grey-dark-1);

  flex: 0 0 18%;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
```
