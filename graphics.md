# Graphics


## Art

* [Commit.io](https://commits.io/) - Turn code to art


## Free stock photos

* [Pexels](https://www.pexels.com/)
* Unsplash

## Vector editors

* Figma - realtime vector editor
* [vectr](https://vectr.com) - Funded by Guillermo Rauch
* Sketch
* Adobe Illustrator

## Image processing as a Service

- [imgix](https://www.imgix.com/)

## How to convert mov to gif

`ffmpeg -i in.mov -s 600x400 -pix_fmt rgb24 -r 10 -f gif - | gifsicle --optimize=3 --delay=3 > out.gif`

Notes on the arguments:

* `-r 10` tells ffmpeg to reduce the frame rate from 25 fps to 10
* `-s 600x400` tells ffmpeg the max-width and max-height
* `--delay=3` tells gifsicle to delay 30ms between each gif
* `--optimize=3` requests that gifsicle use the slowest/most file-size optimization 

[Reference](https://gist.github.com/dergachev/4627207)

## Photo editing

* [Filters like Van Gogh](https://primitive.lol/)

## Tools

* [CSS Gradients](https://gradients.cssgears.com/)
* [straple](https://straple.co/#/) - Sketch framework for React + CSS





