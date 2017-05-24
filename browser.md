# Browser

> Browser APIs 

## Script to download images from browser

```js
function downloadURI(uri, name) {
  var link = document.createElement("a");
  link.download = name;
  link.href = uri;
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
  delete link;
}

downloadURI("/wp-content/uploads/2016/03/advisor-brian.png", "advisor-brian.png");
```