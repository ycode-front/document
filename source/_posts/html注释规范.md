title: html注释规范
date: 2015-12-04 11:20:08
categories:
- 前端规范
- 前端代码规范
---

## 内容的注释

显然不必给每个html模块都加上注释，给一些大的比较关键的html模块加上注释

由于现在编辑器都有代码自动对齐和折叠的功能，注释不必结束，这样反而更加清晰

每一行注释之前加一个空行


```html

<!-- 主体内容 -->
<div class="content">

    <!-- 页面导航 -->
    <nav>
        <ul>
            <li></li>
            <li></li>
        </ul>
    </nav>
</div>

<!-- 页面页脚信息 -->
<div class="footer">

</div>

```


## 脚本注释

在脚本引入的时候用注释，来说明一段脚本的作用非常重要

在引入一段新的脚本的时候，别人需要了解之前脚本的功能，判断新脚本的引入位置

```html

<!-- 库脚本 -->
<script type="text/javascript" src="jQuery.js"></script>

<!-- 统计代码 -->
<script type="text/javascript" src="ga-google.js"></script>

```