<div align="center">

# 🎨 tailwindcss-hexcolor

### Dynamic Arbitrary Color Utilities for Tailwind CSS

Write beautiful color utilities **without square bracket syntax (`[]`)**.

Supports **HEX**, **RGB**, **RGBA**, **HSL**, **HSLA**, and **CSS `color-mix()`** for **Tailwind CSS v3 & v4**.

<p>

<a href="https://www.npmjs.com/package/tailwindcss-hexcolor">
<img src="https://img.shields.io/npm/v/tailwindcss-hexcolor?style=for-the-badge&logo=npm" alt="NPM Version">
</a>

<a href="https://www.npmjs.com/package/tailwindcss-hexcolor">
<img src="https://img.shields.io/npm/dm/tailwindcss-hexcolor?style=for-the-badge&logo=npm" alt="Downloads">
</a>

<a href="LICENSE">
<img src="https://img.shields.io/npm/l/tailwindcss-hexcolor?style=for-the-badge" alt="License">
</a>

<a href="https://tailwindcss.com">
<img src="https://img.shields.io/badge/Tailwind-v3%20%26%20v4-38BDF8?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS">
</a>

<a href="https://github.com/SnehMoradia/tailwindcss-hexcolor/stargazers">
<img src="https://img.shields.io/github/stars/SnehMoradia/tailwindcss-hexcolor?style=for-the-badge" alt="GitHub Stars">
</a>

<a href="https://github.com/SnehMoradia/tailwindcss-hexcolor/network/members">
<img src="https://img.shields.io/github/forks/SnehMoradia/tailwindcss-hexcolor?style=for-the-badge" alt="Forks">
</a>

<a href="https://github.com/SnehMoradia/tailwindcss-hexcolor/issues">
<img src="https://img.shields.io/github/issues/SnehMoradia/tailwindcss-hexcolor?style=for-the-badge" alt="Issues">
</a>

</p>

**✨ Clean Syntax • 🚀 Zero Configuration • ⚡ Fast • 🎨 Multiple Color Formats**

</div>

---

## 📖 Overview

`tailwindcss-hexcolor` is a lightweight Tailwind CSS plugin that automatically discovers custom color utility classes inside your project and generates the corresponding CSS using Tailwind's powerful `matchUtilities()` API.

Forget writing long arbitrary value classes like:

```html
<div class="bg-[#6366f1] text-[rgb(255,255,255)]"></div>
```

Instead, write clean, readable classes:

```html
<div class="bg-6366f1 text-rgb-255-255-255"></div>
```

The plugin recursively scans your project files, extracts supported color utilities, caches the results for faster rebuilds, and automatically regenerates CSS whenever new colors are added.

Whether you're using **Tailwind CSS v4's CSS-first configuration** or **Tailwind CSS v3's JavaScript configuration**, `tailwindcss-hexcolor` works out of the box with zero hassle.

---

# ✨ Features

- 🎨 Supports **HEX**, **RGB**, **RGBA**, **HSL**, **HSLA**, and **CSS `color-mix()`**
- 🚀 No square bracket (`[]`) syntax required
- ⚡ Supports **16 built-in Tailwind color utilities**
- 📂 Recursive project scanning
- 🔍 Automatically detects new colors
- ⚡ Smart cache for ultra-fast rebuilds
- 🔄 Automatically rebuilds during watch mode
- 📄 Supports HTML, JSX, TSX, Vue, Svelte, Astro, Blade, Twig, PHP, MDX, Markdown, and many more
- 🛠 Powered by Tailwind's `matchUtilities()`
- 💡 Zero configuration required
- 🌈 Supports 3, 4, 6, and 8-digit HEX colors
- 🔥 Fully compatible with **Tailwind CSS v3 & v4**

---

# 📚 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Installation](#-installation)
- [Quick Start](#-quick-start)
- [Examples](#-examples)
- [Supported Color Formats](#-supported-color-formats)
- [Supported Utility Prefixes](#-supported-utility-prefixes)
- [Configuration](#-configuration)
- [Supported File Types](#-supported-file-types)
- [How It Works](#-how-it-works)
- [Why Use This Plugin?](#-why-use-this-plugin)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

# 📦 Installation

Choose your preferred package manager.

## npm

```bash
npm install tailwindcss-hexcolor
```

## pnpm

```bash
pnpm add -D tailwindcss-hexcolor
```

## yarn

```bash
yarn add -D tailwindcss-hexcolor
```

## bun

```bash
bun add -d tailwindcss-hexcolor
```

---

# ⚡ Quick Start

## Tailwind CSS v4

Add the plugin directly inside your CSS.

```css
@import "tailwindcss";

@plugin "tailwindcss-hexcolor" {
  srcDir: "./src";
  cachePath: "./colors-cache.json";
  inputCssPath: "./src/input.css";
}
```

---

## Tailwind CSS v3

Register the plugin inside your `tailwind.config.js`.

```js
module.exports = {
  content: [
    "./src/**/*.{html,js,jsx,ts,tsx,vue,svelte}"
  ],

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

## That's it! 🎉

Now you can use clean utility classes like:

```html
<div
  class="
    bg-6366f1
    text-ffffff
    border-333333
    ring-8b5cf6
    shadow-00000033
  "
></div>
```

Instead of writing:

```html
<div
  class="
    bg-[#6366f1]
    text-[#ffffff]
    border-[#333333]
    ring-[#8b5cf6]
    shadow-[#00000033]
  "
></div>
```

No extra configuration.

No custom CSS.

No arbitrary value syntax.

Just install, configure once, and start using beautiful color utilities.

---
# 🧪 Examples

Below are a few examples of how `tailwindcss-hexcolor` makes your Tailwind classes cleaner and easier to read.

---

## Traditional Tailwind Arbitrary Values

```html
<div
  class="
    bg-[#6366f1]
    text-[#ffffff]
    border-[#e5e7eb]
    ring-[#8b5cf6]
    shadow-[#00000033]
  "
></div>
```

---

## Using `tailwindcss-hexcolor`

```html
<div
  class="
    bg-6366f1
    text-ffffff
    border-e5e7eb
    ring-8b5cf6
    shadow-00000033
  "
></div>
```

Much cleaner, easier to read, and no square bracket syntax.

---

# 🎨 Supported Color Formats

The plugin supports every major CSS color format.

| Format | Supported |
|---------|-----------|
| HEX | ✅ |
| RGB | ✅ |
| RGBA | ✅ |
| HSL | ✅ |
| HSLA | ✅ |
| CSS `color-mix()` | ✅ |

---

# HEX Colors

Supports:

- 3-digit HEX
- 4-digit HEX
- 6-digit HEX
- 8-digit HEX (with alpha)

### Usage

```html
bg-fff
```

↓

```css
background-color: #fff;
```

---

```html
bg-333
```

↓

```css
background-color: #333;
```

---

```html
text-ff0000
```

↓

```css
color: #ff0000;
```

---

```html
border-ff000080
```

↓

```css
border-color: #ff000080;
```

---

```html
ring-8b5cf6
```

↓

```css
--tw-ring-color: #8b5cf6;
```

---

# RGB Colors

Supports both dash-separated and underscore-separated syntax.

## Dash syntax

```html
bg-rgb-255-0-0
```

↓

```css
background-color: rgb(255, 0, 0);
```

---

## Underscore syntax

```html
text-rgb_0_128_255
```

↓

```css
color: rgb(0,128,255);
```

---

## Another Example

```html
border-rgb-34-197-94
```

↓

```css
border-color: rgb(34,197,94);
```

---

# RGBA Colors

RGBA supports opacity values.

```html
bg-rgba-255-0-0-0.5
```

↓

```css
background-color: rgba(255,0,0,0.5);
```

---

Underscore notation is also supported.

```html
bg-rgba_255_0_0_0_5
```

↓

```css
background-color: rgba(255,0,0,0.5);
```

---

### Decimal Conversion

Underscores are automatically converted into decimal points.

```
0_1 → 0.1

0_25 → 0.25

0_5 → 0.5

0_75 → 0.75

1_0 → 1.0
```

---

# HSL Colors

```html
bg-hsl-220-100-50
```

↓

```css
background-color: hsl(220,100%,50%);
```

---

```html
text-hsl-120-60-45
```

↓

```css
color: hsl(120,60%,45%);
```

---

```html
border-hsl-15-80-60
```

↓

```css
border-color: hsl(15,80%,60%);
```

---

# HSLA Colors

Supports alpha transparency.

```html
bg-hsla-220-100-50-0.5
```

↓

```css
background-color: hsla(220,100%,50%,0.5);
```

---

```html
outline-hsla-120-100-40-0.8
```

↓

```css
outline-color: hsla(120,100%,40%,0.8);
```

---

# CSS `color-mix()`

Generate modern CSS color combinations directly from utility classes.

---

## Basic Example

```html
bg-mix-in-srgb--red-30--blue
```

↓

```css
background-color: color-mix(
  in srgb,
  red 30%,
  blue
);
```

---

## Using HEX

```html
bg-mix-in-srgb--ff0000-50--0000ff
```

↓

```css
background-color: color-mix(
  in srgb,
  #ff0000 50%,
  #0000ff
);
```

---

## Using RGB

```html
text-mix-in-srgb--rgb-255-0-0-40--rgb-0-0-255
```

↓

```css
color: color-mix(
  in srgb,
  rgb(255,0,0) 40%,
  rgb(0,0,255)
);
```

---

## Using HSL

```html
bg-mix-in-oklch--hsl-220-100-50-35--hsl-120-100-50
```

↓

```css
background-color: color-mix(
  in oklch,
  hsl(220,100%,50%) 35%,
  hsl(120,100%,50%)
);
```

---

## Mixing Different Formats

```html
text-mix-in-oklch--rgb-255-0-0-40--ff00ff
```

↓

```css
color: color-mix(
  in oklch,
  rgb(255,0,0) 40%,
  #ff00ff
);
```

---

## Default Color Space

If no color space is specified, the plugin automatically uses **srgb**.

```html
bg-mix--red-50--blue
```

↓

```css
background-color: color-mix(
  in srgb,
  red 50%,
  blue
);
```

---

# 🧰 Supported Utility Prefixes

The plugin currently supports **16 Tailwind color utilities**.

| Utility | CSS Property |
|----------|--------------|
| `bg-*` | `background-color` |
| `text-*` | `color` |
| `border-*` | `border-color` |
| `outline-*` | `outline-color` |
| `ring-*` | `--tw-ring-color` |
| `shadow-*` | `--tw-shadow-color` |
| `fill-*` | `fill` |
| `stroke-*` | `stroke` |
| `accent-*` | `accent-color` |
| `caret-*` | `caret-color` |
| `decoration-*` | `text-decoration-color` |
| `placeholder-*` | `::placeholder` |
| `divide-*` | Border color between siblings |
| `from-*` | Gradient start |
| `via-*` | Gradient middle |
| `to-*` | Gradient end |

---

## Complete Example

```html
<div
  class="
    bg-6366f1
    text-ffffff
    border-e5e7eb
    outline-ff9800
    ring-8b5cf6
    shadow-00000033
    fill-ef4444
    stroke-3b82f6
    accent-22c55e
    caret-f97316
    decoration-eab308
    placeholder-9ca3af
    divide-d1d5db
    from-6366f1
    via-8b5cf6
    to-ec4899
  "
></div>
```

---

# ⚙️ Configuration

`tailwindcss-hexcolor` works out of the box with zero configuration. However, you can customize how the plugin scans your project and stores its cache.

---

## Available Options

| Option | Type | Default | Description |
|---------|------|---------|-------------|
| `srcDir` | `string` | `./src` | Root directory to scan recursively |
| `cachePath` | `string` | `./colors-cache.json` | Location of the generated cache file |
| `inputCssPath` | `string` | `./src/input.css` | Input CSS file used to trigger Tailwind rebuilds |

All options are optional.

---

## Default Configuration

### Tailwind CSS v4

```css
@import "tailwindcss";

@plugin "tailwindcss-hexcolor";
```

---

### Tailwind CSS v3

```js
plugins: [
    require("tailwindcss-hexcolor")(),
],
```

---

## Custom Configuration

### Tailwind CSS v4

```css
@import "tailwindcss";

@plugin "tailwindcss-hexcolor" {
    srcDir: "./app";
    cachePath: "./cache/colors.json";
    inputCssPath: "./resources/css/app.css";
}
```

---

### Tailwind CSS v3

```js
plugins: [
    require("tailwindcss-hexcolor")({
        srcDir: "./app",
        cachePath: "./cache/colors.json",
        inputCssPath: "./resources/css/app.css",
    }),
],
```

---

# 📂 Supported File Types

The plugin recursively scans your project and automatically detects color utility classes inside supported files.

| Extension | Supported |
|------------|-----------|
| html | ✅ |
| js | ✅ |
| jsx | ✅ |
| ts | ✅ |
| tsx | ✅ |
| vue | ✅ |
| svelte | ✅ |
| astro | ✅ |
| php | ✅ |
| blade.php | ✅ |
| twig | ✅ |
| erb | ✅ |
| liquid | ✅ |
| md | ✅ |
| mdx | ✅ |
| hbs | ✅ |
| njk | ✅ |

And many other template formats.

---

## Example Project Structure

```
project/

├── src/
│   ├── pages/
│   ├── components/
│   ├── layouts/
│   └── app.jsx
│
├── input.css
│
└── colors-cache.json
```

Every supported file inside `srcDir` is scanned automatically.

---

# ⚡ How It Works

The plugin integrates directly into Tailwind's build pipeline.

Whenever Tailwind runs, the plugin performs the following steps:

```text
Scan Project
      │
      ▼
Find Color Classes
      │
      ▼
Parse Color Values
      │
      ▼
Generate Tailwind Utilities
      │
      ▼
Save Cache
      │
      ▼
Trigger CSS Rebuild
```

---

## Step 1 — Scan

The plugin recursively scans every supported file inside your project.

Example:

```html
<div class="bg-6366f1 text-ffffff border-e5e7eb"></div>
```

---

## Step 2 — Detect

It automatically finds supported utility prefixes.

```
bg-
text-
border-
ring-
shadow-
fill-
stroke-
...
```

---

## Step 3 — Parse

Each utility is parsed into a valid CSS color.

Example

```
bg-6366f1

↓

#6366f1
```

---

```
text-rgb-255-255-255

↓

rgb(255,255,255)
```

---

```
bg-hsl-220-100-50

↓

hsl(220,100%,50%)
```

---

## Step 4 — Generate

The plugin dynamically generates utilities using Tailwind's `matchUtilities()` API.

Example

```css
.bg-6366f1 {
    background-color: #6366f1;
}
```

---

## Step 5 — Cache

Detected colors are stored in a lightweight cache file.

Benefits:

- Faster rebuilds
- Reduced parsing
- Better development performance

Example

```json
[
    "6366f1",
    "ffffff",
    "e5e7eb",
    "rgb-255-0-0",
    "hsl-220-100-50"
]
```

---

## Step 6 — Watch Mode

Whenever you add a new color class, the plugin automatically:

- detects it
- updates the cache
- regenerates utilities
- triggers Tailwind rebuild

No manual restart required.

---

# 🚀 Performance

Designed for large projects.

### Smart Caching

Previously scanned colors are skipped automatically.

---

### Recursive Scanning

Only supported template files are scanned.

---

### Incremental Rebuilds

Only newly discovered colors are generated.

---

### Zero Runtime

The plugin runs **only during build time**.

No JavaScript is shipped to the browser.

No client-side overhead.

---

# 💡 Why Use This Plugin?

Instead of:

```html
<div class="bg-[#6366f1]"></div>
```

Write:

```html
<div class="bg-6366f1"></div>
```

---

Instead of:

```html
<div class="text-[rgb(255,255,255)]"></div>
```

Write:

```html
<div class="text-rgb-255-255-255"></div>
```

---

Instead of:

```html
<div class="bg-[hsl(220,100%,50%)]"></div>
```

Write:

```html
<div class="bg-hsl-220-100-50"></div>
```

---

Cleaner.

Readable.

Git-friendly.

Easy to search.

Easy to maintain.

---

# ❓ Frequently Asked Questions

## Does this replace Tailwind's arbitrary values?

No.

Tailwind's arbitrary values continue to work exactly as before.

This plugin simply provides a cleaner syntax for common color utilities.

---

## Does it work with Tailwind CSS v4?

✅ Yes.

Fully supported.

---

## Does it work with Tailwind CSS v3?

✅ Yes.

Fully supported.

---

## Is any runtime JavaScript added?

No.

Everything happens during the build process.

Zero runtime cost.

---

## Does it support watch mode?

Yes.

The plugin automatically detects new colors and rebuilds your CSS during development.

---

## Is configuration required?

No.

The default configuration works for most projects.

Customize it only if needed.

---

## Can I use HEX, RGB, RGBA, HSL, HSLA, and color-mix together?

Absolutely.

You can freely mix all supported color formats in the same project.

---

## Does it affect Tailwind performance?

No.

Thanks to its smart caching mechanism, rebuilds remain fast even in large projects.

---

# 🗺️ Roadmap

We're actively improving **tailwindcss-hexcolor**. Here are some planned features and enhancements.

## Completed

- [x] Tailwind CSS v3 support
- [x] Tailwind CSS v4 support
- [x] HEX color utilities
- [x] RGB color utilities
- [x] RGBA color utilities
- [x] HSL color utilities
- [x] HSLA color utilities
- [x] CSS `color-mix()` support
- [x] Recursive file scanning
- [x] Smart cache system
- [x] Automatic rebuild detection
- [x] Multiple template file support
- [x] Zero configuration setup

---

## Coming Soon

- [ ] CSS Variables support
- [ ] OKLCH color utilities
- [ ] OKLAB color utilities
- [ ] Named color aliases
- [ ] Custom utility registration
- [ ] Color validation with better error messages
- [ ] Playground website
- [ ] VS Code extension
- [ ] CLI utility
- [ ] Documentation website

---

# 🤝 Contributing

Contributions are always welcome!

Whether you've found a bug, have an idea for a new feature, or want to improve the documentation, we'd love your help.

## Getting Started

### 1. Fork the repository

Click the **Fork** button on GitHub.

---

### 2. Clone your fork

```bash
git clone https://github.com/your-username/tailwindcss-hexcolor.git
```

---

### 3. Install dependencies

```bash
npm install
```

or

```bash
pnpm install
```

---

### 4. Create a feature branch

```bash
git checkout -b feature/amazing-feature
```

---

### 5. Make your changes

Write your code.

Run tests.

Update documentation if needed.

---

### 6. Commit

```bash
git commit -m "feat: add amazing feature"
```

Follow the Conventional Commits specification whenever possible.

Examples:

```text
feat:
fix:
docs:
refactor:
perf:
test:
build:
ci:
```

---

### 7. Push

```bash
git push origin feature/amazing-feature
```

---

### 8. Open a Pull Request

Describe:

- What changed
- Why it changed
- Screenshots (if applicable)

---

# 🐛 Reporting Bugs

Found a bug?

Please include:

- Tailwind version
- Plugin version
- Node version
- Operating system
- Reproduction steps
- Expected behavior
- Actual behavior

The more information you provide, the easier it is to fix.

---

# 💡 Feature Requests

Have an idea?

Open an Issue and include:

- Problem you're trying to solve
- Proposed solution
- Alternative approaches
- Example usage

Great ideas often become the next release!

---

# ❤️ Show Your Support

If this project has helped you, consider supporting it by:

- ⭐ Starring the repository
- 🍴 Forking the project
- 🐛 Reporting bugs
- 💬 Sharing feedback
- 📢 Sharing it with other developers

Every star helps the project reach more developers.

---

# 📈 Project Status

| Status | Value |
|----------|--------|
| Development | ✅ Active |
| Maintenance | ✅ Actively Maintained |
| Tailwind v3 | ✅ Supported |
| Tailwind v4 | ✅ Supported |
| Open Source | ✅ Yes |
| License | MIT |

---

# 📜 Changelog

All notable changes are documented in the release history.

Follow the GitHub Releases page to stay updated with new features and improvements.

---

# 📄 License

Distributed under the **MIT License**.

See the [LICENSE](LICENSE) file for more information.

---

# 🙌 Acknowledgements

Special thanks to:

- The **Tailwind CSS** team for creating an incredible CSS framework.
- The open-source community for inspiration and feedback.
- Every contributor who helps improve this project.

---

# 🌟 Star History

If you like this project, don't forget to leave a ⭐ on GitHub!

Stars help the project grow and motivate future development.

---

<div align="center">

## 🚀 Built for the Tailwind CSS Community

**tailwindcss-hexcolor** makes working with arbitrary color utilities simpler, cleaner, and more maintainable.

No square brackets.

No clutter.

Just clean utility classes.

---

Made with ❤️ by **Sneh Moradia**

### ⭐ If you found this project useful, please consider giving it a star!

<a href="https://github.com/SnehMoradia/tailwindcss-hexcolor">
<img src="https://img.shields.io/github/stars/SnehMoradia/tailwindcss-hexcolor?style=for-the-badge&logo=github" alt="GitHub Stars">
</a>

<a href="https://www.npmjs.com/package/tailwindcss-hexcolor">
<img src="https://img.shields.io/npm/v/tailwindcss-hexcolor?style=for-the-badge&logo=npm" alt="NPM Version">
</a>

<br><br>

**Happy Coding! 🎉**

</div>
