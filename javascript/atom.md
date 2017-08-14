# Atom

## Themes

- monokai

## Plugins

- editorconfig
- emmet
- language-babel
- language-ethereum
- nuclide
- pigments (CSS color preview)
- prettier-atom
- vim-mode-plus


### Emmet keymap

```smd
# Stop emmet from hijacking basic tabbing
'atom-text-editor[data-grammar="text html basic"]:not([mini]),
 atom-text-editor[data-grammar~="jade"]:not([mini]),
 atom-text-editor[data-grammar~="css"]:not([mini]),
 atom-text-editor[data-grammar~="sass"]:not([mini])':
  'tab': 'snippets:next-tab-stop'

# Emmet for JSX
'atom-text-editor[data-grammar~="jsx"]:not([mini])':
  'tab': 'emmet:expand-abbreviation-with-tab'

# Stop emmet from hijacking tab from snippets and autocomplete
'atom-text-editor.autocomplete-active:not([mini])':
  'tab': 'autocomplete-plus:confirm'
```

### Plugin Development

- [Tutorial build first plugin](https://github.com/blog/2231-building-your-first-atom-plugin)
- [Atom API Docs](https://atom.io/docs/api/v1.9.4/)