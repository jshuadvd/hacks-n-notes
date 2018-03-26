# PerfMatters

[https://perfmattersconf.com/](https://perfmattersconf.com/)

## Workshop

[Wiki google doc](https://docs.google.com/document/d/1ok9lyjhOfWf12jH_cPFh-ctMJm695HNJM67747kxJ5M/edit?usp=sharing)

shell command `traceroute` to see the network llayers

set http connection to KeepAlive: On

### HTTP hints

Can be in headers, html attributes, or dynamic JS

ex `<link rel="preload" href="http://cdn.com">`

> These are more useful for dynamically injected assets or assets below the fold of the page.

* `preload` DNS, TCP, SSL & HTTP Request. (perfect for fonts) (current page)
* `prefetch` DNS, TCP, SSL & HTTP Request. (to prefetch the next page) (next page)
* `dns-prefetch` DNS only (current page)
* `preconnect` DNS, TCP, SSL (can be combined with `dns-prefetch`)(current page)


### CSS

CSS is render-blocking to avoid FOUC. 
It is possible to add a media attribute (print, media queries) to the `<link>`.

### JS 

JS is parsing blocking.
`<script>` has the attribute `async` (downloads JS without parting) and `defer` (the same as async but waits to execute until DOM is ready).

### Critical Render

* load critical css inlined and minimized in the <head> (determine it programatically criticalCSS)
* load the rest of the css dynamically with JS [loadCSS](https://github.com/filamentgroup/loadCSS)

