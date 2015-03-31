Phenix.js
======

A dummy pop-up box.

How to...
------
### Initiate
To initiate the pop-up box with prefered arguments, just call `Phenix.init` method. This will create the pop-up box DOM element at `Phenix.element`.
```javascript
Phenix.init({
    width: 500,
    height: 300,
    template: "info",
    data: {
        color: "#36b14a",
        face: ":)",
        title: "LOL",
        description: "HAPPY DAY"
    }
});
```
This snippet tends to create a 500x300 pop-up box using the default template _info_ with the 4 given data.

### Display the box
After the initiation the box can only be displayed. The appearance of the box is decided by the configuration and has a _fade in_ effect by default.
```javascript
Phenix.show(function() { console.log("pop-up showed"); });
```
The box will only show if `Phenix` is initiated.
`Phenix.show` method receives one argument which is a callback function, called right after the box is showed.

### Hide the box
If the pop-up box is showed in the page, use `Phenix.hide` method to hide the box.
```javascript
Phenix.hide(function() { console.log("pop-up hidden"); });
```
`Phenix.hide` method receives one argument which is a callback function, called right after the box is hidden.

### Use them together
Calling `Phenix.init` will return `Phenix` so you can call other methods right after the initiation.
```javascript
Phenix.init({
    width: 500,
    height: 300,
    template: "info",
    data: {
        color: "#36b14a",
        face: ":)",
        title: "LOL",
        description: "HAPPY DAY"
    }
}).show(function() {
    console.log("pop-up showed");
}).hide(function() {
    console.log("pop-up hidden");
});
```
### Use it with custom configurations
The argument of `Phenix.init` is an object determining the configurations of the pop-up box.

Name|Usage
---|---
width|The width of the pop-up box
height|The height of the pop-up box
template|The default template name OR the template itself
data|Data to be replaced in the template

There are some default templates already written for you, but you can also use your own template. The `template` option is now an HTML snippet, with variables like `{{variables}}` to be replaced by the variables in the `data` option.
```javascript
Phenix.init({
    width: 500,
    height: 300,
    template: "<div><code>{{democode}}</code></div>",
    data: {
        democode: "printf(a);"
    }
}).show();
```

License
------

The MIT License (MIT)

Copyright (c) 2015 James Liu \<j@jamesliu.info\>

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
