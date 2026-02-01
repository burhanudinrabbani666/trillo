# BUIDLING OVERALL LAYOUT

The direct children of a Flex Container (elements with display: flex or display: inline-flex set on them) become flex items.

Continuous runs of text inside flex containers will also become flex items.

[Flex item](https://developer.mozilla.org/en-US/docs/Glossary/Flex_Item)

```scss
.container {
  max-width: 120rem;
  margin: 8rem auto;
  background-color: var(--color-grey-light-1);
  box-shadow: var(--shadow-dark);

  min-height: 100rem;
}

.header {
  height: 7rem;
  background-color: #fff;
  border-bottom: var(--color-grey-light-2);
}

.content {
  display: flex;

  .sidebar {
    background-color: var(--color-grey-dark-2);

    flex: 0 0 18%;
  }

  .hotel-view {
    color: #fff;
    background-color: red;
    flex: 1;
  }

  //
}
```

[Next: Building header](./06-building-header.md)
