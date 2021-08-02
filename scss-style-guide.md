# SCSS Style-Guide

We use BEM with unlimited component nesting.

## Glossar

### Block `.button`

### Element`.button__text`

### Modifier`.button--green`



# Rule zero

Ordering of styles in scss files.

The ordering of the elements should be related to the top to bottom occurances of the class in html.

1. `@extend`
2. `@include`
3. `Modifiers`
4. `Elements`

### Example

```
.block {
	// first extend
	@extend .box;
	// second include
	@include arrow-mixin;
	// third modifiers
	&--blue {
	
	}
	// forth elements
	&__child {
	
	}
}
```



# Rule one

For each HTML-Element there should be at maximum one block-element.

## Why

- We want to prevent that we end up with a lot of classe in the html.

## Don't

```html
<div class="box grid__space__y"></div>
```

## Do

```html
<div class="my_custom_class"></div>
```



```scss
.my_custom_class {
	@extend .box, .grid__space__y;
}
```

# Rule two

Only modify elements by directly assigning a class.

## Why

- Make styling explicit. 
- Keep a low css specifity. 
- Prevent indirect styling that would not be visible by the class name (less obvious and clean).

## Don't 

```scss
.button {
	h1 {
		font-size: 120%;
	}
}
```

## Do

```scss
.button {
	&__title {
		font-size: 120%;
	}
}
```
