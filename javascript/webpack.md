# Webpack

- [Webpack validator](https://github.com/js-dxtools/webpack-validator) - like eslint but for webpack

## Tree-shaking

- **babel preset 2016-webpack** will transpile the ES Modules instead of being transpiled in babel. By delegating the ES Modules transpilation to webpack, webpack is able to run static analysis to see which modules are being used, hence optimize the bundle with tree-shaking. CommonJS modules are not staticly analyzable.

## Code splitting

- Load modules using `Sistem.import()` and webpack will split that code and lazy load it.