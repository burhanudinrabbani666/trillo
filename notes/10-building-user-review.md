# BUILDING USER REVIEW

- Using html entity in CSS

```scss
.review {
  background-color: #fff;
  box-shadow: var(--shadow-light);
  padding: 3rem;
  margin-bottom: 3.5rem;

  position: relative;
  overflow: hidden;
  &__text {
    margin-bottom: 2rem;
    z-index: 10;
    position: relative;
  }

  &__user {
    display: flex;
    align-items: center;
    gap: 1.5rem;
  }

  &__photo {
    width: 4.5rem;
    height: 4.5rem;
    border-radius: 50%;
  }

  &__user-box {
    display: flex;
    flex-direction: column;
    margin-right: auto;
    gap: 0.4rem;
  }

  &__user-name {
    font-weight: 600;
    font-size: 1.1rem;
    text-transform: uppercase;
  }

  &__user-date {
    font-size: 1rem;
    color: var(--color-grey-light-4);
  }

  &__rating {
    color: var(--color-primary);
    font-size: 2.2rem;
    font-weight: 300;
  }

  &::before {
    content: "\201C";
    position: absolute;
    top: -4rem;
    left: -1rem;
    line-height: 1;
    font-size: 20rem;
    color: var(--color-grey-light-2);
    font-family: sans-serif;
  }
}
```

[Next: Building cta section](./11-building-cta-section.md)
