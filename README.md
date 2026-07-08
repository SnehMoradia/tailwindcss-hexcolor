# tailwindcss-hexcolor

> A powerful Tailwind CSS plugin that enables arbitrary color utilities without square bracket syntax.

`tailwindcss-hexcolor` recursively scans your project for custom color utility classes and automatically generates the required CSS using Tailwind's `matchUtilities` API.

It supports **Tailwind CSS v4** (CSS-first configuration) and **Tailwind CSS v3** (JavaScript configuration) out of the box.

---

## ✨ Features

* 🎨 Supports **HEX**, **RGB**, **RGBA**, **HSL**, **HSLA**, and **CSS `color-mix()`**
* 🚀 No arbitrary value syntax (`[]`) required
* ⚡ Supports **16 built-in Tailwind color utilities**
* 📂 Recursively scans your project
* 📄 Works with HTML, JSX, TSX, Vue, Svelte, Astro, PHP, Blade, Twig, MDX, Markdown, and more
* 🔄 Automatically rebuilds during watch mode
* 💾 Smart cache system for faster rebuilds
* 🛠️ Works with both **Tailwind CSS v3** and **v4**

---

# Example

Instead of writing:

```html
<div class="bg-[#ffffff] text-[#111111] border-[#333333]"></div>
```

You can simply write:

```html
<div class="bg-fff text-111111 border-333333"></div>
```

Or use other supported formats:

```html
<div
  class="
    bg-rgb-255-0-0
    text-rgba-255-255-255-0_8
    border-hsl-220-100-50
    outline-hsla-220-100-50-0_6
    from-mix-in-srgb--red-40--blue
  "
></div>
```

---

# Supported Color Formats

## HEX

```html
bg-fff
bg-333
text-ff0000
border-ff000080
```

Generates

```css
background-color: #fff;
background-color: #333;
color: #ff0000;
border-color: #ff000080;
```

---

## RGB

```html
bg-rgb-255-0-0
text-rgb_0_128_255
```

↓

```css
background-color: rgb(255, 0, 0);
color: rgb(0, 128, 255);
```

---

## RGBA

```html
bg-rgba-255-0-0-0.5
bg-rgba_255_0_0_0_5
```

↓

```css
background-color: rgba(255,0,0,0.5);
```

Underscores are automatically converted to decimal points.

```
0_5 → 0.5
```

---

## HSL

```html
bg-hsl-220-100-50
```

↓

```css
background-color: hsl(220,100%,50%);
```

---

## HSLA

```html
bg-hsla-120-100-40-0.8
```

↓

```css
background-color: hsla(120,100%,40%,0.8);
```

---

## color-mix()

```html
bg-mix-in-srgb--red-30--blue
```

↓

```css
background-color: color-mix(in srgb, red 30%, blue);
```

You can even mix different color formats.

```html
text-mix-in-oklch--rgb-255-0-0-40--hsl-120-100-50
```

↓

```css
color: color-mix(
  in oklch,
  rgb(255,0,0) 40%,
  hsl(120,100%,50%)
);
```

If no color space is specified, **`srgb`** is used automatically.

---

# Supported Utility Prefixes

| Prefix         | CSS Property                    |
| -------------- | ------------------------------- |
| `bg-`          | `background-color`              |
| `text-`        | `color`                         |
| `border-`      | `border-color`                  |
| `outline-`     | `outline-color`                 |
| `ring-`        | `--tw-ring-color`               |
| `shadow-`      | `--tw-shadow-color`             |
| `fill-`        | `fill`                          |
| `stroke-`      | `stroke`                        |
| `accent-`      | `accent-color`                  |
| `caret-`       | `caret-color`                   |
| `decoration-`  | `text-decoration-color`         |
| `placeholder-` | `::placeholder`                 |
| `divide-`      | `border-color` between siblings |
| `from-`        | Gradient start                  |
| `via-`         | Gradient middle                 |
| `to-`          | Gradient end                    |

---

# Installation

## npm

```bash
npm install tailwindcss-hexcolor
```

or

```bash
pnpm add -D tailwindcss-hexcolor
```

or

```bash
yarn add -D tailwindcss-hexcolor
```

---

# Tailwind CSS v4

```css
@import "tailwindcss";

@plugin "tailwindcss-hexcolor" {
  srcDir: "./src";
  cachePath: "./colors-cache.json";
  inputCssPath: "./src/input.css";
};
```

---

# Tailwind CSS v3

```js
module.exports = {
  content: ["./src/**/*.{html,js,jsx,ts,tsx,vue,svelte}"],

  plugins: [
    require("tailwindcss-hexcolor")({
      srcDir: "./src",
      cachePath: "./colors-cache.json",
      inputCssPath: "./src/input.css",
    }),
  ],
};
```

---

# Configuration

| Option         | Type     | Default               | Description                             |
| -------------- | -------- | --------------------- | --------------------------------------- |
| `srcDir`       | `string` | `./src`               | Directory to scan recursively           |
| `cachePath`    | `string` | `./colors-cache.json` | Cache file location                     |
| `inputCssPath` | `string` | `./src/input.css`     | Input CSS file used to trigger rebuilds |

All options are optional.

---

# Supported File Types

The plugin automatically scans:

```
html
js
jsx
ts
tsx
vue
svelte
astro
php
blade.php
twig
erb
liquid
md
mdx
```

and many other common template files.

---

# How It Works

1. Recursively scans your project.
2. Finds matching color utility classes.
3. Generates Tailwind utilities using `matchUtilities`.
4. Stores results in a cache.
5. Watches for file changes.
6. Automatically rebuilds when colors change.

---

# Why use this plugin?

✅ Cleaner than arbitrary values

```html
bg-fff
```

instead of

```html
bg-[#fff]
```

✅ Supports every major CSS color format.

✅ Zero manual configuration.

✅ Fast incremental rebuilds.

✅ Compatible with Tailwind CSS v3 & v4.

---

# License

MIT License.

---

I would also recommend adding badges at the very top to make the README look more professional:

```md
# tailwindcss-hexcolor

[![npm](https://img.shields.io/npm/v/tailwindcss-hexcolor)
[![downloads](https://img.shields.io/npm/dm/tailwindcss-hexcolor)
[![license](https://img.shields.io/npm/l/tailwindcss-hexcolor)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-v3%20%7C%20v4-38BDF8)
```

This gives your README a polished, production-quality appearance similar to popular open-source Tailwind plugins.
