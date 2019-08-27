# A11Y demo

## Accessible Icon Buttons

This example is totally a11y

```html
<button>Help!</button>
```

Can anybody tell me what is wrong w/ this example?

```html
<button>
  <i class="icon icon-help"></i>
</button>
```

here is how we could refactor it to make it a11y

```html
<button>
  <span class="visuallyhidden">Help!</span>
  <i class="icon icon-help" aria-hidden="true"></i>
</button>
```

or both solutions above and below work equally well

```html
<button aria-label="Help!">
  <i class="icon icon-help" aria-hidden="true"></i>
</button>
```

Div button example - what is wrong w/ this?

```html
<div class="button">
  <svg
    width="32"
    height="32"
    viewBox="0 0 32 32"
    class="icon"
    aria-labelledby="svgtitle"
  >
    <path
      d="M14 24h4v-4h-4v4zM16 8c-3 0-6 3-6 6h4c0-1 1-2 2-2s2 1 2 2c0 2-4 2-4 4h4c2-0.688 4-2 4-5s-3-5-6-5zM16 0c-8.844 0-16 7.156-16 16s7.156 16 16 16 16-7.156 16-16-7.156-16-16-16zM16 28c-6.625 0-12-5.375-12-12s5.375-12 12-12 12 5.375 12 12-5.375 12-12 12z"
    ></path>
  </svg>
</div>
```

Solution would be to add a role and tabindex to the div and a title element to the svg. Note title element must have unique id.

```html
<div class="button" role="button" tabindex="0">
  <svg
    width="32"
    height="32"
    viewBox="0 0 32 32"
    class="icon"
    aria-labelledby="svgtitle"
  >
    <title id="svgtitle">Help!</title>
    <path
      d="M14 24h4v-4h-4v4zM16 8c-3 0-6 3-6 6h4c0-1 1-2 2-2s2 1 2 2c0 2-4 2-4 4h4c2-0.688 4-2 4-5s-3-5-6-5zM16 0c-8.844 0-16 7.156-16 16s7.156 16 16 16 16-7.156 16-16-7.156-16-16-16zM16 28c-6.625 0-12-5.375-12-12s5.375-12 12-12 12 5.375 12 12-5.375 12-12 12z"
    ></path>
  </svg>
</div>
```
