# Vue.js

## Rule zero - component mounting

Use `data-vue-id` selector to mount components.

### Why

`id` selectors are generic and could be used for multiple purposes, which then easy to forget.
Example: there was a component with certain id, which was later refactored (thus id changed).
However, this id was also used for analytics, which was forgotten and not updated.
By using data selectors, we can separate concerns and avoid issues like this.

### Don't

```javascript
<div id="my-component-id">
  <h1>Hello World</h1>
</div>

new Vue({ el: '#my-component-id' })
```

### Do

```javascript
<div data-vue-id="my-component-id">
  <h1>Hello World</h1>
</div>

new Vue({ el: '[data-vue-id="my-component-id"]' })
```
