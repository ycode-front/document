title: html代码规范
date: 2015-12-04 09:47:03
categories:
- 前端规范
- 前端代码规范
---

## 文档类型声明

采用html5的文档类型声明。

文档类型声明放在html文档的开头

```html

<!DOCTYPE html>
<html>
<head>
    <title></title>
</head>
<body>

</body>
</html>

```

必须添加 doctype ，否在在IE浏览器老版本浏览器下不会用正确的模式进行解析

## 指定字符编码

```html
<head>
    <meta charset="UTF-8">
</head>
```

## 正确指定文档的标题

```html
<head>
    <title>Title</title>
</head>
```

## 脚本引入

### 脚本的引入位置

脚本的下载和解析会阻塞DOM的解析。所以不要再文档的开头引入脚本。

脚本放在 body 结束标签之前。

并且按照脚本的执行顺序，添加 ``script`` 标签。

```html

<!DOCTYPE html>
<html>
<head>
    <title></title>
</head>
<body>

<!-- 文档内容 -->

<script type="text/javascript" src="jquery.js"></script>
<script type="text/javascript" src="main.js"></script>
</body>
</html>

```

不要在script标签中添加 asyc defer 属性，这样会打乱 js 的执行顺序，从而发送错误

### 内联脚本

只有在一种情况下使用内联脚本，就是在需要对页面进行用户配置的时候

且尽可能只暴露一个入口用于配置

```html

<!DOCTYPE html>
<html>
<head>
    <title></title>
</head>
<body>

<!-- 文档内容 -->

<script type="text/javascript" src="jquery.js"></script>
<script type="text/javascript" src="main.js"></script>
<script type="text/javascript">
    Main.init({
        name:'1234'
    });
</script>
</body>
</html>

```

## 样式的引入

### 内联样式

不要使用内联样式

```html

<!-- 不要这样使用 -->
<style type="text/css">
    .footer {
        color:red;
    }
</style>

```

### 嵌入式样式

不要使用嵌入式样式

```html

<!-- 不要这样使用 -->
<div class="footer" style="color:red">
    
</div>

```

## id的使用

尽量不要使用 id 作为css选择器

只将 id 作为锚点使用

## 引号

在html中使用双引号，在js中使用单引号

## 标签的闭合

单标签不需要闭合

```html

<br>

<hr>

```