# KaTeX for Typecho

![](https://img.shields.io/badge/typecho->=0.9-467b96.svg?style=flat-square)
![](https://img.shields.io/badge/version-1.0.0-orange.svg?style=flat-square)
![](https://img.shields.io/badge/LICENSE-MIT-brightgreen.svg?style=flat-square)

原项目地址：https://github.com/vc12345679/KaTeX4Typecho

原作者已停止维护。

## Features

本项目可以为您的[Typecho](http://typecho.org)博客提供[KaTeX](https://katex.org)数学公式支持，适合博客内需要数学公式的用户使用。

### v0.2及以前

请到原项目查看

### v1.0.0

1. 更新``KaTeX``版本至``0.10.0``，更换为``jsdelivr``的cdn
2. 添加忽略样式名功能，妈妈再也不用担心我首页摘要被渲染然后在手机上显示超出屏幕了！
3. 修改了默认配置，符合``LaTeX``规范

## 安装

请先将本项目[下载](https://github.com/Llf0703/KaTeX4Typecho/archive/master.zip)或克隆到本地

```
git clone https://github.com/Llf0703/KaTeX4Typecho.git
```

将项目文件夹放到``{typecho}/usr/plugins``中，在后台设置并启用插件即可。

## 设置

### 公式标识符

默认设置为：

```js
{left: "$$", right: "$$", display: true},{left: "$", right: "$", display: false}
```

前一个花括号中的``left``和``right``代表**段落模式**两端的符号，被两个符号夹在中间的内容会被渲染成**单独成段**的公式。

后一个花括号代表**行内模式**两端的符号，中间的内容会与其他内容显示在同一行。

效果：

```tex
$$a \times b = 1$$
```

<a href="https://www.codecogs.com/eqnedit.php?latex=a&space;\times&space;b&space;=&space;1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?a&space;\times&space;b&space;=&space;1" title="a \times b = 1" /></a>

### 忽略的标签

默认设置为：

```js
"script", "noscript", "style", "textarea", "pre", "code"
```

即这些标签中的内容不会被渲染。

### 忽略的样式

默认设置为：

```js
"nokatex"
```

即这些样式中的内容不会被渲染。

您可以给不需要被渲染的元素添加``.nokatex``标签，也可以将不需要渲染的元素填在这里。

### 如果您的博客应用了pjax

您可以将``footer.php``中的

```php
<?php $this->footer(); ?>
```

放在pjax的刷新区域内。

或者参照下面的无插件说明操作。

## 推荐

1. 将手写的数学公式转化为LaTeX： https://webdemo.myscript.com/views/math/index.html
2. LaTeX在线编辑，并可转化为图片： https://www.codecogs.com/latex/eqneditor.php

## 不想用插件？

LaTeX自动渲染文档地址： https://katex.org/docs/autorender.html

在``header``中添加：

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/katex@0.10.0/dist/katex.min.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/katex@0.10.0/dist/katex.min.css" />
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/katex@0.10.0/dist/contrib/auto-render.min.js"></script>
```

在``footer``的合适位置添加：

```html
<script type="text/javascript">renderMathInElement(document.body,{delimiters:[{left: "$$", right: "$$", display: true},{left: "$", right: "$", display: false}],ignoredTags:["script", "noscript", "style", "textarea", "pre", "code"],ignoredClasses:["nokatex"]});</script>
```

即可。

## LICENSE

MIT