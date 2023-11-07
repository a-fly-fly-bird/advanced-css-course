我的笔记。

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


# css 函数
许多 CSS 属性 将 URL 作为属性值，例如 background-image、cursor、@font-face、list-style 等。
[url()](https://developer.mozilla.org/zh-CN/docs/Web/CSS/url)

[linear-gradient()](https://developer.mozilla.org/zh-CN/docs/Web/CSS/gradient/linear-gradient)

# px 和 vh
[绝对大小和相对大小单位](https://www.w3schools.com/cssref/css_units.php)

