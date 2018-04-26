# PerfMatters

[https://perfmattersconf.com/](https://perfmattersconf.com/)

## Sponsors

* [appdepar](https://addepar.com/)
* [appdynamics](https://www.appdynamics.com/product/browser-real-user-monitoring/)
* [catchpoint](http://www.catchpoint.com/)
* [cloudinary](https://cloudinary.com/)
* [fastly](https://www.fastly.com/)
* [imagecon](http://www.imagecon.com/events/imagecon-2018/event-summary-1a9b0d3d0cbf4d979d663a202586ed1e.aspx)
* [speedcurve](https://speedcurve.com/)
* [white coat captioning](http://www.whitecoatcaptioning.com/)

## Pinterest

* 1M+ request per second
* dedicated performance team

### Regression protection

* perf environment to run automation integration tests \(100 times\)
* calculate 90th percentile of Pinner Wait Time \(PWT\)
* binary search \(git bisect\) to detect which commit introduced the regression

## React

* create a `<LazyLoader />` component 
* with http2 bundling is still optimal
* img sprite for fold images would help
* `<link as="script">`

## Perf Timings

[slides](http://jlwagner.net/talks/perf-timings/)

* RUM \(Real User Metrics\)
* Long Tasks &gt; 50ms

### Tools

* [Boomerang](https://github.com/SOASTA/boomerang)
* [Bucky](http://github.hubspot.com/BuckyClient/)

## Kimberly Munoz \(Slack\)

### semantic HTML for focus management \(tab\)

* focus on the DOM order instead of using JS
* use `<button>` & `<select>` instead of building your custom with `<div>`
* use modular CSS like [CFPB modular framework](https://cfpb.github.io/capital-framework/)
* use html tags like `nav`, `main`, `head`, and `aside`
* w3c wai-aria-practices

## MarcySutton \(Deque Systems\)

* [Deque tools for accessibility](https://www.deque.com/)
* [Axe Core](https://www.axe-core.org/) OSS tool
* [jsdom](https://github.com/jsdom/jsdom) npm package for accessibility unit testing
* eslint-plugin-jsx-a11y
* [egghead accessibility course](https://egghead.io/courses/start-building-accessible-web-applications-today)

## Jem @jemyoung \(Netflix\)

* buffer with generator + `while(true)` for paralellizing http requests but start serving them as soon as the first request is complete.

## @linclark @codecartoons \(Mozilla\)

Parallelize as much as possible to be quicker

* webworkers
* shared array buffers
* WebAssembly + React



## PWA

cost of loading

[The Web App  Manifest](https://developers.google.com/web/fundamentals/web-app-manifest/)

[The Offline Cookbook](https://jakearchibald.com/2014/offline-cookbook/)

[The PRPL Pattern](https://developers.google.com/web/fundamentals/performance/prpl-pattern/)

eliminate unused code

traced svg \(sharp\) from Gatsby

lazyload img -&gt; use mini versions of img so it looks blurry as a placeholder

uglify.js to remove unused code

webpack tree shaking

webpack bundle analyzer

npm `sw-precache` and `sw-toolbox`





