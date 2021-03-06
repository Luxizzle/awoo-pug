# awoo-pug

A [pug](https://github.com/pugjs/pug) parsing plugin for [awoo](https://github.com/awoojs/awoo)!

## Installation

```
npm install --save awoo-pug
```

## Usage

```js
const awoo = require('awoo')
const pug = require('awoo-pug')

// start a awoo site
awoo(async site => {
  // register the pug plugin
  site.use(pug)

  return site
})
```

### Locals

When using pug you can add locals that can be accessed in your pug file.

Just like any other plugin you can add options to the plugin

```js
...
  site.use(pug, {
    locals: {
      title: 'My awesome awoo site powered by pug!' // This can be accessed in your pug file!
    }
  })
...
```

```pug
head
  title= title
body
  p Hello world!
```

- A pug vfile's `.data` can be accessed under `data`
- Any front-matter generated by `awoo-matter` can be accessed under `metadata`

Just like other plugins in [awoojs/core](https://github.com/awoojs/core), a custom filter method can be given under `options.filter`.