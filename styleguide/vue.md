# Vue.js

## Rule zero - component mounting

Use `data-vue-id` selector to mount components.

### Why

`id` selectors are generic and could be used for multiple purposes. They are easy to forget.
Example: There is a component with a certain id. It was later refactored, the id changed..
However, this id was also used for analytics. It was forgotten and not updated.

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
