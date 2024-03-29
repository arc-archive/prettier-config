# Linting Prettier

Use [Prettier](https://prettier.io) to format your JS, CSS and HTML code.

Based on [@open-wc/prettier-config](https://github.com/open-wc/open-wc/tree/master/packages/prettier-config).


-   Install `@advanced-rest-client/prettier-config`.

```bash
npm i --save-dev @advanced-rest-client/prettier-config
```

-   Create `prettier.config.js` in the root directory of your project.

```js
module.exports = require('@advanced-rest-client/prettier-config');
```

-   Add the following scripts to your package.json

```js
"scripts": {
  "lint:prettier": "prettier \"**/*.js\" --list-different || (echo '↑↑ these files are not prettier formatted ↑↑' && exit 1)",
  "format:prettier": "prettier \"**/*.js\" --write",
},
```

- Update your `.eslintrc.js` to look like this:

```js
module.exports = {
  extends: [
    '@advanced-rest-client/eslint-config',
    'eslint-config-prettier'
  ].map(require.resolve),
};
```

## What you get

-   Apply formatting to JS files
-   Apply formatting to HTML inside of `html` tagged template literals used by [lit-html](https://github.com/Polymer/lit-html)
-   Apply formatting to CSS inside of `css` tagged template literals used by [lit-css](https://github.com/lit-styles/lit-styles/tree/master/packages/lit-css)
-   Integration with ESLint to prevent potentially conflicting rules

## Usage

Run:
-   `npm run lint:prettier` to check if your files are correctly formatted
-   `npm run format:prettier` to auto format your files

## Linting Error Examples

```bash
$ npm run lint:prettier

test/set-card.test.js
test/set-game.test.js
↑↑ these files are not prettier formatted ↑↑
```

Simply run `npm run format:prettier` to format your files automatically.
