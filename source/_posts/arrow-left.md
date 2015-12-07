title: arrow-left
date: 2015-11-23 20:29:38
categories:
- less图标库
---

左箭头

```less
.arrow-left(@width, @height, @border)
```

## 参数

| 参数名 | 含义 |
|:-----:|:----:|
| @width |箭头的宽度|
| @height |箭头的高度|
| @border |箭头线条的宽度|


## demo

### 代码

```less
.add-btn {
    margin-top: -15px;
    top: 50%;
    right: 45px;
    .ico-add(30px, gray, white);
    position: absolute;
}
```

### 效果


<i class="demo"></i>


<style type="text/css">
.demo {
  margin: 10px 0;
  width: 0.88888889rem;
  height: 1.77777778rem;
  position: relative;
  display: inline-block;
  -webkit-transform-origin: 50% 0%;
  -webkit-transform: scaleY(1.25);
  transform-origin: 50% 0%;
  transform: scaleY(1.25);
  position: relative;
  top: 50%;
  left: 2.5rem;
}
.demo:after {
  content: '';
  display: block;
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
  width: 1.25707872rem;
  height: 1.25707872rem;
  border-left: 2px solid #999999;
  border-bottom: 2px solid #999999;
  position: absolute;
  top: 0.26034953rem;
  left: 0.26034953rem;
  -webkit-transform: rotate(45deg);
  -webkit-transform-origin: 50% 50%;
  transform: rotate(45deg);
  transform-origin: 50% 50%;
}
</style>


## 源代码
```less
.arrow-left(@width, @height, @border) {
    width: @width;
    height: 2*@width;
    position: relative;
    display: inline-block;
    &:after {
        content: '';
        display: block;
        box-sizing: border-box;
        -webkit-box-sizing: border-box;
        width: @width*sqrt(2);
        height: @width*sqrt(2);
        border-left: @border;
        border-bottom: @border;
        position: absolute;
        top: (@width*2 - @width*sqrt(2))/2;
        left: (@width*2 - @width*sqrt(2))/2;
        
        -webkit-transform: rotate(45deg);
        -webkit-transform-origin: 50% 50%;
        transform: rotate(45deg);
        transform-origin: 50% 50%;
        // border-top-left-radius: 3px;
        // border-bottom-right-radius: 3px;
    }
    -webkit-transform-origin:50% 0%;
    -webkit-transform:scaleY(unit(@height/(2*@width)));
    transform-origin:50% 0%;
    transform:scaleY(unit(@height/(2*@width)));
}
```