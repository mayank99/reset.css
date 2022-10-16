# reset.css

A style reset that embraces modern CSS features to give you a better base to start off with.

## Features

- Designed for cascade layers while still using `:where` to keep a low specificity for non-layer setups.
- Auto dark mode using `color-scheme`.
- `system-ui` font pre-applied.
- Accessible, consistent focus outlines.

## Usage

Install and import the package (requires a bundler):

```shell
npm install @acab/reset.css
```

```css
/* in a CSS file or <style> tag */
@import '@acab/reset.css';
```

```js
// or in a JS file
import '@acab/reset.css';
```

Or use it directly from a CDN:

```html
@import 'https://unpkg.com/@acab/reset';
```

### Cascade layers

It is recommended to import this reset into the very first layer.

Ideally, you should predefine your layers as the first thing in the first stylesheet.

```css
@layer reset, page, overrides;
```

And then apply the first layer name while importing this reset.

```css
@import '@acab/reset.css' layer(reset);
```
