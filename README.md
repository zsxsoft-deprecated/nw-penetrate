nw-penetrate
======

**Windows Only**

**NodeJS 0.12.0+**

**Tested under nwjs 0.12.0**

It used Win32 API to make your nwjs window penetrable.

![Snapshot](http://zsxsoft.github.io/nw-penetrate/snapshot.gif)

### Installion
```bash 
$ npm install nw-penetrate
```

### Usage
First, you should open ``transparent`` in ``package.json``
```json
  "window": {
    "transparent": true,
    "frame": false,
  },
```

Then, set a unique ``document.title`` dynamically (like ``Math.random()``). 
```javascript
var tranResult = require("nw-penetrate").penetrate(window.document.title);
console.log(tranResult);
```


## 中文

它调用了Win32API来让你的nwjs窗口可被鼠标穿过。

首先你要设置package.json，打开它的transparent选项。

其次，你需要设置一个独一无二的窗口标题。我觉得``Math.random()``是个不错的选择呢。

技术原理没啥复杂的，就是发现``nan``不能在nwjs下使用，``bindings``也出现了API的不兼容，于是特意独立出来这什么鬼。
