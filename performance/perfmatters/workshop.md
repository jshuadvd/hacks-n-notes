# Workshop: Getting up to speed

[Wiki google doc](https://docs.google.com/document/d/1ok9lyjhOfWf12jH_cPFh-ctMJm695HNJM67747kxJ5M/edit?usp=sharing)

shell command `traceroute` to see the network llayers

set http connection to KeepAlive: On

## HTTP hints

Can be in headers, html attributes, or dynamic JS

ex `<link rel="preload" href="http://cdn.com">`

> These are more useful for dynamically injected assets or assets below the fold of the page.

* `preload` DNS, TCP, SSL & HTTP Request. (perfect for fonts) (current page)
* `prefetch` DNS, TCP, SSL & HTTP Request. (to prefetch the next page) (next page)
* `dns-prefetch` DNS only (current page)
* `preconnect` DNS, TCP, SSL (can be combined with `dns-prefetch`)(current page)


## CSS

CSS is render-blocking to avoid FOUC.
It is possible to add a media attribute (print, media queries) to the `<link>`.

### Critical Path CSS Render

* load critical css inlined and minimized in the <head> (determine it programatically [critical-path-css-tools by Addy Osmani](https://github.com/addyosmani/critical-path-css-tools)) aim for < 14kb so it transfers on the first trip in the HTTP request.
* load the rest of the css dynamically with JS [loadCSS](https://github.com/filamentgroup/loadCSS). Set a cookie to flag that the css is already loaded.


## JS

JS is parsing blocking.
`<script>` has the attribute `async` (downloads JS without parting) and `defer` (the same as async but waits to execute until DOM is ready).

[Hidden Chrome dev tools experiment](https://hackernoon.com/hidden-experimental-features-in-chrome-devtools-2ae93b11b628)


### requestIdleCallback

[requestIdleCallback](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestIdleCallback#Browser_compatibility)

* Fires that piece of code when the browser is idle.
* perfect for analytics events like Mixpanel

## Fonts

`font-display` to tell the browser how to treat your font loading.
* auto
* fallback
* block
* swap
* optional

Use `rel="preload"` and `crossorigin` + https://fontfaceobserver.com

### Variable fonts

- has all the weights baked into one file

### Subsetting

You can select the subset of the font that you need. Discard glyphs that you dont use like accents for other languages.

Subsetting can be done in the href as a query string param for example `&text=Hello`

Prefer woff2.
Load: local(), woff2, or woff (in that order)


You can use `unicode-range` in `@font-face` to load specific subset of unicode ranges.

## Audit tools

- [cloudinary web speed test](https://webspeedtest.cloudinary.com)
- webpagetest
