#svg 文本

## 目录
1. `<text>`和`<tspan>`创建文本  
2. 
3. 
4. 


## `<text>`标签
在svg中用使用`<text>`标签去定义一段文字。如 Example 1

在svg中写下

> 在平坦的路上曲折前行

[Example 1 Dome](http://codepen.io/Yunkou/full/ZYGaqg/)
``` xml
<svg height="30" width="200">
    <text x="0" y="15" fill="red">在平坦的路上曲折前行</text>
</svg>
```
在例子1中 `x="0" y="15"` 是文字定位坐标
可能你会有疑问，为什么文字没有距离上边是15呢？这里首先你需要了解个概念`baseline` 熟悉css的同学会眼熟 会用到 `vertical-align: baseline;` 但是什么是 `baseline`呢？

![baseline](http://media.mediatemple.netdna-cdn.com/wp-content/uploads/2012/10/baseline.jpg)

这不是我们的重点了解移步到《[CSS Baseline: The Good, The Bad And The Ugly](http://www.smashingmagazine.com/2012/12/17/css-baseline-the-good-the-bad-and-the-ugly/)》 译文：《[CSS基线之道](http://www.qianduan.net/css-baseline-road.html)》
在svg中xy 的坐标就是 基于`baseline` 如图：

![baseline](http://kydome.qiniudn.com/baseline.png)

所以就看不到预想的文字没有距上边15px

看似简单，其实不然——“大有可为”！～
比如让文字旋转下Example 2

[Example 2 Dome](http://codepen.io/Yunkou/full/PwqOLe/)
``` xml
<svg height="60" width="200">
    <text x="0" y="15" fill="red" 
            transform="rotate(30 20,40)">在平坦的路上曲折前行</text>
</svg>
```
`transform="rotate(30 20,40)"` 表示在 （20.40）位置顺时针旋转30度

你也可以把`<text>`标签 设定为文本组，其中可以包含`<tspan>`，而且每个`<tspan>`都可以有不同的定位和文本格式。

[Example 3 Dome](http://codepen.io/Yunkou/full/wBaEVv)

``` xml
<svg height="90" width="200">
    <text x="10" y="20" style="fill:red;">Several lines:
        <tspan x="10" y="45">First line.</tspan>
        <tspan x="10" y="70">Second line.</tspan>
    </text>
</svg>
```
如果没有设置tspan 的 x y 那么文本会类似 css 中行内展示

你可以把文字设置成链接
[Example 4 Dome](http://codepen.io/Yunkou/full/WbvgVQ)
``` xml
<svg height="30" width="200" xmlns:xlink="http://www.w3.org/1999/xlink">
    <a xlink:href="http://www.w3schools.com/svg/" target="_blank">
        <text x="0" y="15" fill="red">I love SVG!</text>
    </a>
</svg>
```
这里注意下，按照html的习惯直接在a 标签里写文字是不可以的，文字不会显示，这里文字是个文本对象，你要设置这个对象的链接。



