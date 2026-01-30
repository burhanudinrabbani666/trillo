# WHY FLEXBOX: AN OVERVIEW OF THE PHILOSOPHY BEHIND FLEXBOX

- Felxbox is new module n CSS3 that makes easy to align elemenets to one anothe in differnet directions and orders.
- The main ides behnd felxbox is to give the container the abillity to expand and to shrink elements to best use all the avaible space.
- Flexbox repalcaes float layout, using less, and more readable and logical code.
- Flexbox completally changes the way that we build one-dimensional layouts.

## MAIN FLEXBOX CONCEPTS

```css
.app {
  display: flex;
}
```

## FLEXBOX PROPERTIES OVERVIEW

### CONTAINER

1. **flex-direction: row** | row-reverse | column | column-reverse
2. **flex-wrap: nowrap** | wrap | wrap-reverse
3. **justify-content: flex-start** | flex-end | center | space-between | spce-around | spce-evenly
4. **align-items: strech** | flex-start | flex-end | center | baselinre
5. **align-content: strech** | flex-start | flex-end | center | space-between | space-between

### ITEM

1. **align-self: auto** | strech | felx-start | felx-end | center | baseline
2. **order: 0** | integer
3. **flex-grow: 0** | integer
4. **flex-shrink: 1** | integer
5. **flex-basis: auto** | integer

[Next: Flex container](./02-flex-container.md)
