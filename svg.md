# SVG

> Scalar Vector Graphics

## Code

`preserveAspectRatio` to slice or adjust the svg inside the viewport.

### Using media queries

> hiding parts of the svg sprite with media queries

```
var shape = document.getElementById(‘sag’)

// media query event handler

if (matchMedia) {
  var mq = window.matchMedia(‘(min-width: 500px)’);
  mq.addListener(WidthChange);
  WidthChange(mq);
}
// media query change
function WidthChange(mq) {
  if (mq.matches) {
    shape.setAttribyte(‘viewBox’, ‘0 0 490 474’);
  } else {
    shape.setAttribyte(‘viewBox’, ‘0 0 500 500’);
  }
}
```

## Books

- [designing-interface-animation](http://rosenfeldmedia.com/books/designing-interface-animation/)

### SVG Essentials, 2nd Edition
Producing Scalable Vector Graphics with XML
By J. Eisenberg, Amelia Bellamy-Royds



## Reference

* [SVG Pocket Guide](http://svgpocketguide.com/book/) - tips and tricks


## Tools

* [Milanote](www.milanote.com) - Mood board
* [SVGO](https://github.com/svg/svgo)- Nodejs-based tool for optimizing SVG vector graphics files
* [svgomg](https://jakearchibald.github.io/svgomg/) - SVG optimizer by Jake Archibald


## Best practices

- set svg width and height in CSS instead of inline because otherwise its difficult to override

## Courses

- [FrontendMasters SVG Animation](https://frontendmasters.com/courses/svg-animation)

## Examples & Inspiration

- [Sarah Drasner](https://sarahdrasnerdesign.com/)
- [Sarah Drasner - codepen](https://codepen.io/sdras/)
- [Sarah Drasner - github](https://github.com/sdras)
- [Sarah Drasner - AMA](https://github.com/WebAnimationWorkshops/ama)
- [cssdesignawards](https://www.cssdesignawards.com)