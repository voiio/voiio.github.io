# SCSS

We use BEM with unlimited component nesting, but maximum one level of child components.

This [website](https://9elements.com/bem-cheat-sheet/) has a good visual guide on how we use BEM.

## Glossary

### Block `.button`

### Element`.button__text`

### Modifier`.button--green`



# Rule zero - style ordering

Ordering of styles in scss files.

The ordering of the elements should be related to the top to bottom occurrences of the class in html.

1. `@extend`
2. `@include`
3. `Modifiers`
4. `Elements`

### Example

```scss
.block {
  // first extend
  @extend .box;
  // second include
  @include arrow-mixin;
  // third modifiers
  &--blue {}
  // forth elements
  &__child {}
}
```



# Rule one - reusable components

Add new components to component library.

## Why

- to have a reusable component library

## Don't

```html
<div class="page__component__modification"></div>
```

```scss
.page__component__modification {
  @extend .component;

  // modification styles
}
```



## Do

```html
<div class="component component--red"></div>
```

```scss
.component {
  // Add a modifier if different version is needed
  &--red {

  }
}
```

# Rule two - use CSS classes

Only modify elements by directly assigning a class.

## Why

- Make styling explicit
- Keep CSS specificity low
- Prevent indirect styling that would not be visible by the class name (less obvious and clean)

## Don't

```scss
.component {
  h1 {
    margin-bottom: 1rem;
  }
}
```

```html
<div class="component">
  <h1>Some Title</h1>
</div>
```

## Do

```scss
.component {
  &__title {
    font-size: 120%;
  }
}
```

```html
<div class="component">
  <h1 class="component__title">Some Title</h1>
</div>
```

# Rule three - use style to a certain degree

It's possible to use `style` attribute on HTML-Tags.
But usually, it should only be one CSS-Style.

## Why

- prevent creating of css classes with only one attribute
- make edge cases more visible

## Don't

```scss
.component-text-color {
  color: var(--brand-color);
}
```

```html
<h1 class="component-text-color">Some Title</h1>
```

## Do

```scss
// no css
```

```html
<h1 style="color: var(--brand-color);">Some Title</h1>
```
