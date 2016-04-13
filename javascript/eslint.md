# ESLint

> Recommended ESLint rules

## Accessibility

`npm i --save-dev eslint-plugin-jsx-a11y`

description | rule
-- | --
Prevent use of [`accessKey`](https://github.com/evcohen/eslint-plugin-jsx-a11y/blob/master/docs/rules/no-access-key.md)  | `'jsx-a11y/no-access-key': 2`
Require `<img>` to have a non-empty `alt` prop, or `role="presentation"` | `'jsx-a11y/img-uses-alt': 2`
Prevent `img` alt text from containing redundant words like "image", "picture", or "photo" | `'jsx-a11y/redundant-alt': 2`
Require ARIA roles to be valid and non-abstract | `'jsx-a11y/valid-aria-role': 2`


- 