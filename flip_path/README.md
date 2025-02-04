我的[Udemy排名第一的高级CSS课程 Advanced CSS and Sass - 高级 CSS 和 Sass：Flexbox、网格、动画（中英文字幕）](https://www.bilibili.com/video/BV1n94y1o7yS/?p=6&share_source=copy_web&vd_source=3bfb0ec751c895fd26607d3661a4598c)笔记。

想要系统学习CSS，[mdn web docs](https://developer.mozilla.org/zh-CN/docs/Learn/Getting_started_with_the_web/CSS_basics)会是不错的文档。

# font-family
可以通过在html的header中引入字体然后
```css
body {
    font-family: 'Long Cang', cursive, Georgia, 'Times New Roman', Times, serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.7;
    color: #777;
}
```
这样使用。

注意font-family这行的语法，是**优先级从高到低的字体列表**。每一个css字段似乎都有这样的规则，我这样写也是不会抱错的：
```css
font-size: 16px, 18px, 20px;
```
因为是优先级从高到低的列表，那我就可以：

```css
background-image: linear-gradient(to right bottom, rgba(128, 214, 113, 0.8), rgba(39, 180, 133, 0.8)), url(../img/hero.jpg);
```
有点像图层，上层是渐变色，下层是图片。

# css 函数
许多 CSS 属性 将 URL 作为属性值，例如 background-image、cursor、@font-face、list-style 等。
[url()](https://developer.mozilla.org/zh-CN/docs/Web/CSS/url)

[linear-gradient()](https://developer.mozilla.org/zh-CN/docs/Web/CSS/gradient/linear-gradient)

# px 和 vh
[绝对大小和相对大小单位](https://www.w3schools.com/cssref/css_units.php)

# div 和 行内元素
div 可以看作一个容器，把行内元素包在容器里。算是一个小的tips吧。

# position

[position](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position)有`static`， `relative`, `absolute`, `fixed`，`sticky`...默认position为`static`，也就是该关键字指定元素使用正常的布局行为，即元素在文档常规流中当前的布局位置。此时 top, right, bottom, left 和 z-index 属性无效。

## absolute 和 relative

课程中，老师在`<div class="logo-box">`设置为`absolute`定位时，特意跑回父元素`<header class="header">`设置为`relative`定位，很好奇是为什么，然后就搜到了以下知识点：

[CSS 中，为什么绝对定位（absolute）的父级元素必须是相对定位（relative）？ - 丁小倪的回答 - 知乎](https://www.zhihu.com/question/19926700/answer/13483404)

> 首先，我想告诉你的是，如果父级元素是绝对定位（absolute）或者没有设置，里面的绝对定位（absolute）自动以body定位。这句话是错的。正确的是：只要父级元素设了position并且不是static（默认既是static），那么设定了absolute的子元素即以此为包含块（最近的）。绝对定位（Absolute positioning）元素定位的参照物是其包含块，既相对于其包含块进行定位，不一定是其父元素。建议去详细通读一下定位体系和包含块。

# \<img> height
参考自：[HTML <img> 标签的 height 和 width 属性](https://www.w3school.com.cn/tags/att_img_height-width.asp)

## 图像预留空间
> 为图像指定 height 和 width 属性是一个好习惯。如果设置了这些属性，就可以在页面加载时为图像预留空间。如果没有这些属性，浏览器就无法了解图像的尺寸，也就无法为图像保留合适的空间，因此当图像加载时，页面的布局就会发生变化。（下面的篇幅详细解释了这个观点）。

## 改变图像大小 - 制作填充图像

> height 和 width 属性有一种隐藏的特性，就是人们无需指定图像的实际大小，也就是说，这两个值可以比实际的尺寸大一些或小一些。浏览器会自动调整图像，使其适应这个预留空间的大小。使用这种方法就可以很容易地为大图像创建其缩略图，以及放大很小的图像。但需要注意的是：浏览器还是必须要下载整个文件，不管它最终显示的尺寸到底是多大，而且，如果没有保持其原来的宽度和高度比例，图像会发生扭曲。

# <span> and <div>
> HTML \<span> 元素是短语内容的通用行内容器，并没有任何特殊语义。可以使用它来编组元素以达到某种样式意图（通过使用类或者 Id 属性），或者这些元素有着共同的属性，比如lang。应该在没有其他合适的语义元素时才使用它。\<span> 与 \<div> 元素很相似，但 \<div> 是一个 块元素 而 \<span> 则是 行内元素 (en-US).

## 区别
Stack Overflow 上有人提出了类似的问题：[whats-the-different-between-div-and-span-if-i-set-display-block-or-inline](https://stackoverflow.com/questions/23455926/whats-the-different-between-div-and-span-if-i-set-display-block-or-inline)

答案是：`<div>`里可以放`<span>`,但是`<span>`里不可以放`<div>`。

# display
[CSS display](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display) 属性设置元素是否被视为块或者内联元素以及用于子元素的布局，例如流式布局、网格布局或弹性布局。

形式上，display 属性设置元素的**内部**和**外部**的显示类型。外部类型设置元素参与流式布局；内部类型设置子元素的布局。一些 `display` 值在它们自己的单独规范中完整定义；例如，在 CSS 弹性盒模型的规范中，定义了声明 `display: flex `时会发生的细节。

## 注意
形式上，display 属性设置元素的**内部**和**外部**的显示类型。（这是我之前漏掉的很重要的一部分，所以着重强调一下）

## 外部表现
这些关键字规定元素的外部显示类型，实际上就是其在流式布局中的角色：

### block
该元素生成一个块级元素盒，在正常的流中，该元素之前和之后产生换行。

### inline
该元素生成一个或多个内联元素盒，它们之前或者之后并不会产生换行。在正常的流中，如果有空间，下一个元素将会在同一行上。

## 内部表现
这些关键字规定了元素的内部显示类型，其定义了该内容布局时的格式上下文的类型（假设它是一个非替换元素）：

### flow 实验性
该元素使用流式布局（块和内联布局）来排布它的内容。

如果它的外部显示类型是 inline 或 run-in，并且它参与一个块或者内联格式上下文，那么它将生成一个内联盒子。否则它将生成一个块容器盒。

根据其他属性的值（例如 position、float 或 overflow）以及它自身是否参与到块或者内联格式化上下文，它要么为它的内容建立新的块级格式化上下文（BFC），要么将其内容集成到其父元素的格式化上下文中。

### flow-root
该元素生成一个块级元素盒，其会建立一个新的块级格式化上下文，定义格式化上下文的根元素。

### table
该元素的行为类似于 HTML 中的 <table> 元素。它定义了一个块级别的盒子。

### flex
该元素的行为类似块级元素并且根据弹性盒模型布局它的内容。

### grid
该元素的行为类似块级元素并且根据网格模型布局它的内容。

# text-transform
> text-transform CSS 属性指定如何将元素的文本大写。它可以用于使文本显示为全大写或全小写，也可单独对每一个单词进行操作。

也就是说，除了通过JS来设置显示内容的大小写之外，通过CSS也能实现。

# transform
> CSS transform 属性允许你旋转，缩放，倾斜或平移给定元素。这是通过修改 CSS 视觉格式化模型的坐标空间来实现的。

在教程中的用法非常具有参考性，不借助`flex`等`display`要将某一子元素相对父元素中心居中，应该怎么办呢？

```css
.text-box{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```
重点是：`transform: translate(-50%, -50%);`。

阅读[transform-function](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform-function)发现，元素左上角是坐标原点，`translate(-50%, -50%)`相当于向左和向上平移一般，那原来的
```css
.text-box{
  position: absolute;
  top: 50%;
  left: 50%;
}
```
是将父元素的左上角固定在距视图`top: 50%; left: 50%;`的位置，是父元素的左上角居中。使用`translate(-50%, -50%)`平移子元素后，子元素的中心居中。

# @keyframes

才知道有[@keyframes](https://developer.mozilla.org/zh-CN/docs/Web/CSS/@keyframes)这么强大的功能！

> 关键帧 @keyframes at-rule 规则通过在动画序列中定义关键帧（或 waypoints）的样式来控制 CSS 动画序列中的中间步骤。和 转换 transition 相比，关键帧 keyframes 可以控制动画序列的中间步骤。


首先在css中定义关键帧，
```css
@keyframes moveInLeft{
  0% {
    opacity: 0;
    transform: translateX(-100px) rotate(0deg);
  }

  60%{
    transform: rotate(60deg);
  }

  80%{
    transform: translateX(10px);
  }

  100%{
    opacity: 1;
    transform: translateX(0);
  }
}
```
然后使用关键帧，类似这样：
```css
.heading-primary-main{
  display: block;
  font-size: 80px;
  font-weight: 400;
  letter-spacing: 35px;

  animation-name: moveInLeft;
  animation-duration: 1s;
  animation-timing-function: ease-in;
}
```
或者缩写为:
```css
animation: moveInRight 1s ease-out;
```
这里是关于[animation-timing-function](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-timing-function)的介绍，简而言之就是决定是平滑过渡还是怎么过渡。

# 伪类(Pseudo-classes)
> CSS 伪类是添加到选择器的关键字，用于指定所选元素的特殊状态。例如，伪类 :hover 可以用于选择一个按钮，当用户的指针悬停在按钮上时，设置此按钮的样式。

比如指针悬浮效果：
```css
button:hover {
  color: blue;
}
```

又非常多的伪类，非常有用。

# display: inline-block

尽管刚熟悉了`inline`和`block`，但是看到这里还是有点迷惑。重点学习一下。

> 与 display: inline 相比，主要区别在于 display: inline-block 允许在元素上设置宽度和高度。
> 
> 同样，如果设置了 display: inline-block，将保留上下外边距/内边距，而 display: inline 则不会。
> 
> 与 display: block 相比，主要区别在于 display：inline-block 在元素之后不添加换行符，因此该元素可以位于其他元素旁边。

# text-align
除了之前的`transform`让元素居中外，还有什么更简单的方法吗？**text-align CSS 属性设置块元素或者单元格框的行内内容的水平对齐。**

> text-align属性是用来描述一个行内元素是如何在身为父元素的块级元素中对齐。
> 
> 通过定义可以看出text-align属性并不能控制块级元素的对齐方式，它只对块级元素内的行内元素生效。

所以
```html
 <div class="text-box">
    <h1 class="heading-primary">
        <span class="heading-primary-main">Outdoors</span>
        <span class="heading-primary-sub">is where life happens</span>
    </h1>

    <a href="#" class="btn btn-white">Discover Our Tours</a>
</div>
```
中，要想`<a href="#" class="btn btn-white">Discover Our Tours</a>`水平居中很简单，只要在它或者它的父元素上声明`text-align: center`即可。

# box-shadow
> CSS box-shadow 属性用于在元素的框架上添加阴影效果。你可以在同一个元素上设置多个阴影效果，并用逗号将他们分隔开。该属性可设置的值包括阴影的 X 轴偏移量、Y 轴偏移量、模糊半径、扩散半径和颜色。

这个相对好理解。

# 伪元素(Pseudo-elements)

注意区分 `伪类` 和 `伪元素`！一个是一个冒号，一个是两个冒号。

[伪元素](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-elements)是一个附加至选择器末的关键词，允许你对被选择元素的特定部分修改样式。

比如伪类中的`:hover`是指当前元素在鼠标悬浮时的状态，而伪元素是选中被选择元素的特定部分。

## ::after (:after)
CSS伪元素[::after](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::after)用来创建一个伪元素，作为已选中元素的最后一个子元素。通常会配合content属性来为该元素添加装饰内容。这个虚拟元素默认是行内元素。

不太好理解，还是需要结合教程中的代码理解。

# z-index
> CSS z-index 属性设置定位元素及其后代元素或 flex 项目的 Z 轴顺序。z-index 较大的重叠元素会覆盖较小的元素。

这个MDN的示例非常清晰，就是控制图层的覆盖的。当Z-index的值设置为一个整数时,该整数是当前堆叠上下文中生成的div的堆栈级别。数字越小，越靠前。

## 注意
只有position的值为relative/absolute/fixed中的一个,Z-index才会生效。

# animation-fill-mode

> CSS 属性 animation-fill-mode 设置 CSS 动画在执行之前和之后如何将样式应用于其目标。

[animation-fill-mode](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation-fill-mode)也是一个非常有用的属性，也就是确定动画播放前和播放后的状态。

