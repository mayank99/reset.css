# reset.css

A style reset that embraces modern CSS features to give you a better base to start off with.

## Features

- Designed for cascade layers while still using `:where` to keep a low specificity for unlayered setups.
- Auto dark mode using `color-scheme`.
- `system-ui` font pre-applied.
- Accessible, consistent focus outlines.
- `.visually-hidden` class baked in.

See the [source code](https://github.com/mayank99/reset.css/blob/main/package/index.css) if you're curious about the full set of rules.

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

```css
@import 'https://unpkg.com/@acab/reset.css';
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

### Visually hidden (aka SR only)

Every project needs "visually hidden" styles for screenreader-only text, so this reset has it built in.

It's available through the `.visually-hidden` class and all the rules in it use `!important` so that they can't be overridden by a higher-priority layer.

When a visually-hidden element is focused or an element inside it is focused, then these styles will automatically be undone. Additionally, a `.not-visually-hidden` class is available to undo these styles on some other condition.

### Focus outlines

By default, focus styles can be very inconsistent (and even inaccessible) across browsers. This reset normalizes them to a 2px solid outline that has the [`Highlight`](https://www.w3.org/TR/css-color-4/#system-color-values) color. You can modify this using the `--focus-color` custom property (you might want it to match your accent color).

## Acknowledgements

This project was inspired by some of the existing, popular CSS resets:

- Andy Bell's [modern CSS reset](https://piccalil.li/blog/a-modern-css-reset/)
- Josh W Comeau's [custom CSS reset](https://www.joshwcomeau.com/css/custom-css-reset/)
- Jen Simmons's [CSS remedy](https://github.com/jensimmons/cssremedy)
