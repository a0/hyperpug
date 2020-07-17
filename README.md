# HyperPug

[![npm version](https://badge.fury.io/js/hyperpug.svg)](https://badge.fury.io/js/hyperpug)

Lighter Pug for browser/Electron. With Pug filters' support.

## Usage

```typescript
import HyperPug from 'hyperpug'
const hp = new HyperPug()

console.log(hp.parse(HYPERPUG_STRING))
```

## Usage with filters

Filters are normalized for Markdown and other indented languages are well.

```typescript
import HyperPug from 'hyperpug'
const hp = new HyperPug({
  markdown: (s) => {
    return markdownMaker(s)
  }
})

console.log(hp.parse(HYPERPUG_STRING))
```

## Usage on the browser

```html
<div id="hyperpug"></div>
<script src="https://unpkg.com/hyperpug"></script>
<script>
const hp = new HyperPug({
  markdown: (s) => {
    return markdownMaker(s)
  }
})

document.getElementById("hyperpug").innerHTML = hp.parse(`
style.
  .red {
    color: red;
  }

div(class="x")
  div hello
  div
    .red goodbye
  :markdown
    # This is some heading
br
small Yes, this is a good idea.
`)
</script>
```
