
代码：

```
function createElementFromHTML(htmlString) {
  var div = document.createElement('div');
  div.innerHTML = htmlString.trim();

  // Change this to div.childNodes to support multiple top-level nodes.
  return div.firstChild;
}
```

来源：[Creating a new DOM element from an HTML string using built-in DOM methods or Prototype](https://stackoverflow.com/a/494348/3054511)


实际使用下来，似乎 ELEMENT.appendChild(div.firstChild) 并不成功，因此改为：

    ELEMENT.appendChild(div)


