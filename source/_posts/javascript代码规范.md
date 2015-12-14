title: javascript 代码规范
date: 2015-11-18 09:26:36
tags:
categories:
- 前端规范
- 前端代码规范
---


## 使用严格模式

使用严格模式会对代码进行更严格的检测，避免一些意想不到错误，同时也是为将来的js版本做兼容。严格模式的规则可以参考[Javascript 严格模式详解](http://www.ruanyifeng.com/blog/2013/01/javascript_strict_mode.html).

```javascript
(function($){
    'use strict';

    //do some thing

}(jQuery))
```

注意：前外不要在全局使用严格模式，这样会对第三方插件产生影响，产生错误

## 变量的声明

变量的声明请提前到模块或者函数的开头，并且使用下面的格式。

```javascript
function fun(){
    var a = 1,
        b = 3,
        c = 5;

    // do some thing
}
```

## 使用字面量创建对象

```javascript
// 这样做是对的
var person = {name:'xjc', age:12};

// 这样做是不好的
var person = new Object();
person.name = 'xjc';
person.age = 12;
```

## 判断相等

判断相等的时候，请使用严格相等符号 ``===`` 而不是 ``==``

使用``!==``而不是``!=``

## 分号的使用

在每一个表达式结束的时候加上分号
并不是所有的语句都是表达式，下面举例说明

```javascript

function fun(){

} //函数声明，不是表达式，无需分号


var getName = function(){

}; //函数表达式，请加上分号


if(true){

} //这也不是表达式，当然不用加分号

```

## 循环

### for-in循环

在使用for-in循环的时候，请注意两点

1. 不要使用for-in循环遍历数组元素
2. 在使用for-in遍历对象的时候，请判断属性是否来自继承

```javascript

var obj = {x:1,y:2,z:3}

for(var e in obj){
    if(!obj.hasOwnProperty(e)) continue;

    // do something to e

}

```

### 数组的遍历

如果要对数组进行遍历，可以使用传统的 for 循环，或者es5提供的数组遍历方法。

```javascript

// 传统的 for 方法

var arr = [1,2,3,4,5];

for(var i = 0, e = arr[i]; i < arr.length; i++){

    // do something to e

}

```

es5的数组操作方法

- forEach
- every
- map
- filter
- some
- reduce

使用这些方法的时候请注意[兼容性](http://caniuse.com/#search=forEach)

## 引号的使用

在javascript中使用单引号，而在html标签中使用双引号

```javascript
var str = 'this is string';
```

```html
<div class="footer"> </div>
```

## 模块化

目前使用的模块化的方式是两种，一种是模板模式，一种是 browserify.

既然做了模块化，需要做到一个文件放一个模块。

### 模板模式

使用一个立即执行函数对每一段代码进行封装，避免变量暴露在全局

```javascript

/**
 * [description]
 * 
 * @module [modulename]
 * @author sumight
 */

(function($){
    'use strict';

    var Main = window.Main = {};
        
    /**
     * 模块的默认配置
     */
    Main.defaultCfg = {

    };

    /**
     * 模块初始化
     * 
     * @param  {Object} cfg 用户配置
     */
    Main.init = function(cfg){
        var self = this,
            cfg = this._cfg = $.extend({}, self.defaultCfg, cfg);

        // do something
        
    };

    /**
     * 初始化事件
     */
    Main.initEvent = function(){

    };
}(jQuery));

```

### browserify

采用nodejs的模块化方式写前端代码。

```javascript

/**
 * [description]
 * 
 * @module [modulename]
 * @author sumight
 */

'use strict';

/**
 * 模块依赖
 */
var $ = require("jQuery"),
    util = require("util");

/**
 * 导出模块
 * 如果模块需要暴露给html
 * 就这样写
 *  var Main = window.Main = exports;
 */
var Main = exports;

/**
 * 模块的默认配置
 */
Main.defaultCfg = {

}

/**
 * 模块初始化
 * 
 * @param  {Object} cfg 用户配置
 */
Main.init = function(cfg){
    var self = this,
        cfg = this._cfg = $.extend({}, self.defaultCfg, cfg);

    // do something
    
};

/**
 * 初始化事件
 */
Main.initEvent = function(){

};


```
