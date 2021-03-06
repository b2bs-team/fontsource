# Fontsource Kufam

[![npm (scoped)](https://img.shields.io/npm/v/@fontsource/kufam?color=brightgreen)](https://www.npmjs.com/package/@fontsource/kufam) [![Generic badge](https://img.shields.io/badge/fontsource-passing-brightgreen)](https://github.com/fontsource/fontsource) [![Monthly downloads](https://badgen.net/npm/dm/@fontsource/kufam)](https://github.com/fontsource/fontsource) [![Total downloads](https://badgen.net/npm/dt/@fontsource/kufam)](https://github.com/fontsource/fontsource) [![GitHub stars](https://img.shields.io/github/stars/fontsource/fontsource.svg?style=social&label=Star)](https://github.com/fontsource/fontsource/stargazers)

The CSS and web font files to easily self-host the “Kufam” font. Please visit the main [Fontsource monorepo](https://github.com/fontsource/fontsource) to view more details on this package.

## Installation

Fontsource assumes you are using a bundler, such as Webpack, to load in CSS. Solutions like [CRA](https://create-react-app.dev/), [Gatsby](https://www.gatsbyjs.org/) and [Next.js](https://nextjs.org/) are prebuilt examples that are compatible.

```javascript
yarn add @fontsource/kufam // npm install @fontsource/kufam
```

Then within your app entry file or site component, import it in. For example in Gatsby, you could choose to import it into a layout template (`layout.js`), page component (`index.js`), or `gatsby-browser.js`.

```javascript
import "@fontsource/kufam" // Defaults to weight 400.
```

Fontsource allows you to select weights and even individual styles, allowing you to cut down on payload sizes to the last byte! Utilizing the CSS unicode-range selector, all language subsets are accounted for.

```javascript
import "@fontsource/kufam/500.css" // Weight 500.
import "@fontsource/kufam/900-italic.css" // Italic variant.
```

Alternatively, the same solutions could be imported via SCSS!

```scss
@import "~@fontsource/kufam/index.css"; // Weight 400.
@import "~@fontsource/kufam/300-italic.css";
```

_These examples may not reflect actual compatibility. Please refer below._

Supported variables:

- Weights: `[400,500,600,700,800,900]`
- Styles: `[italic,normal]`

Finally, you can reference the font name in a CSS stylesheet, CSS Module, or CSS-in-JS.

```css
body {
  font-family: "Kufam";
}
```

## Variable Fonts

This particular typeface supports [variable fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts/Variable_Fonts_Guide).

Begin by importing both the variable and fallback font for non-compatible browsers.

```js
import "@fontsource/kufam/400.css" // Weight 400.
```

Select either a stripped down weights only variant of the font or a full feature variant that contains all the variable axes.

```js
import "@fontsource/kufam/variable.css" // Contains ONLY variable weights and no other axes.
import "@fontsource/kufam/variable-italic.css" // Italic variant.
// Or
import "@fontsource/kufam/variable-full.css" // This contains ALL variable axes. Font files are larger.
import "@fontsource/kufam/variable-full-italic.css" // Italic variant.
```

Note a `full` or `italic` variant may NOT exist if there are no additional axes other than wght and/or ital. You can check the available axes [here](https://fonts.google.com/variablefonts).

Followed by the CSS using the @supports tag, which checks whether the browser is capable of utilising variable fonts. Fallback fonts and their relevant CSS should be used outside the block, whilst all variable options should be used within the @supports block and utilising the font-variation-settings tag.

```css
h1 {
  font-family: Kufam;
  font-weight: 400;
}

@supports (font-variation-settings: normal) {
  h1 {
    font-family: KufamVariable;
    font-variation-settings: "wght" 400;
  }
}
```

_To view the available variable axes that may be included in the font, click [here](https://fonts.google.com/variablefonts). The meanings of all axes and the restrictions associated with them are explained there._

## Additional Options

In the rare case you need to individually select a language subset and not utilize the CSS unicode-range selector, you may specify the import as follows. This is especially not recommended for languages, such as Japanese, with a large amount of characters.

```javascript
import "@fontsource/kufam/latin-ext.css" // All weights with normal style included.
import "@fontsource/kufam/cyrillic-ext-500.css" // Weight 500 with normal style.
import "@fontsource/kufam/greek-900-italic.css" // Italic variant.
```

- Supported subsets: `[arabic,latin,latin-ext,vietnamese]`

## Licensing

It is important to always read the license for every font that you use.
Most of the fonts in the collection use the SIL Open Font License, v1.1. Some fonts use the Apache 2 license. The Ubuntu fonts use the Ubuntu Font License v1.0.

[Google Fonts License Attributions](https://fonts.google.com/attribution)

## Other Notes

Font version (provided by source): `v2`.

Feel free to star and contribute new ideas to this repository that aim to improve the performance of font loading, as well as expanding the existing library we already have. Any suggestions or ideas can be voiced via an [issue](https://github.com/fontsource/fontsource/issues).
