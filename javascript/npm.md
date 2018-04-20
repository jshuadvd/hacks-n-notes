# npm

* [npms](https://npms.io/) to search npm

## npm modules

| npm package | description |
| :--- | :--- |
| accounting | accounting |
| [async sema](https://github.com/zeit/async-sema/blob/master/examples/rate-limiting.js) | rate limiting |
| [babel-plugin-module-resolver](https://github.com/tleunen/babel-plugin-module-resolver) | resolves imports |
| [common-tags](https://github.com/declandewet/common-tags) | string templates tags |
| [dataloader](https://github.com/facebook/dataloader) | caching for HTTP requests |
| date-fns | like momentJS but modern |
| [dinero](https://sarahdayan.github.io/dinero.js/index.html) | currency library |
| [faker](https://github.com/Marak/Faker.js) | generates mock data |
| fast-cli | Netflix speedtest |
| fast-csv | parse CVS |
| [feather-icons](https://github.com/feathericons/feather) | svg icons |
| [flatorize](https://github.com/glathoud/flatorize) | Linear algebra library that supports intensive computations in JS |
| [frappe-charts](https://github.com/frappe/charts) | charts |
| google-libphonenumber | phoneNumber library |
| html-pdf | convert html to pdf |
| [inquirer](https://github.com/sboudrias/Inquirer.js) | CLI GUI tools |
| [jimp](https://github.com/oliver-moran/jimp) | image processor for nodejs |
| [mathJS](http://mathjs.org/) | evaluate mathematical expressions |
| node-uuid | generate UUID |
| [npm-license](https://github.com/AceMetrix/npm-license) | generates a flat list of npm modules and their licenses |
| [oy](https://github.com/revivek/oy) | E-mail templates with React |
| [progress](https://github.com/visionmedia/node-progress) | Progress bar for CLI |
| [nps](https://github.com/kentcdodds/nps) | scripts for package json |
| [react-vis](https://uber.github.io/react-vis/) | charts from Uber. In react |
| [rough](https://github.com/pshihn/rough) | Build handdrawn-like shapes |
| serve-favicon | to serve dynamic favicons |
| [strapdown](http://strapdownjs.com/) | markdown renderer |
| [tesseract](https://github.com/naptha/tesseract.js) | OCR in 62 languages |
| ua-parser | to parse UA Clients |
| [webtorrent](https://github.com/webtorrent/webtorrent) | torrents on the browser |

## How to write a UMD module

> [UMD \(Universal Module Definition\) patterns for JavaScript modules that work everywhere.](https://github.com/umdjs/umd/blob/master/templates/returnExports.js)

```js
// Uses Node, AMD or browser globals to create a module.

// If you want something that will work in other stricter CommonJS environments,
// or if you need to create a circular dependency, see commonJsStrict.js

// Defines a module "returnExports" that depends another module called "b".
// Note that the name of the module is implied by the file name. It is best
// if the file name and the exported global have matching names.

// If the 'b' module also uses this type of boilerplate, then
// in the browser, it will create a global .b that is used below.

// If you do not want to support the browser global path, then you
// can remove the `root` use and the passing `this` as the first arg to
// the top function.

(function (root, factory) {
    if (typeof define === 'function' && define.amd) {
        // AMD. Register as an anonymous module.
        define(['b'], factory);
    } else if (typeof module === 'object' && module.exports) {
        // Node. Does not work with strict CommonJS, but
        // only CommonJS-like environments that support module.exports,
        // like Node.
        module.exports = factory(require('b'));
    } else {
        // Browser globals (root is window)
        root.returnExports = factory(root.b);
    }
}(this, function (b) {
    //use b in some fashion.

    // Just return a value to define the module export.
    // This example returns an object, but the module
    // can return a function as the exported value.
    return {};
}));


// if the module has no dependencies, the above pattern can be simplified to
(function (root, factory) {
    if (typeof define === 'function' && define.amd) {
        // AMD. Register as an anonymous module.
        define([], factory);
    } else if (typeof module === 'object' && module.exports) {
        // Node. Does not work with strict CommonJS, but
        // only CommonJS-like environments that support module.exports,
        // like Node.
        module.exports = factory();
    } else {
        // Browser globals (root is window)
        root.returnExports = factory();
  }
}(this, function () {

    // Just return a value to define the module export.
    // This example returns an object, but the module
    // can return a function as the exported value.
    return {};
}));
```

## Easter Eggs

* `npm xmas`
* `npm visnup`
* `npm substack`



