title: javascript注释规范
date: 2015-12-03 21:26:45
categories:
- 前端规范
- 前端代码规范
---

## 模块的注释

在模块的注释中还可以添加更多的信息，比如日期等等。

在模块的描述可以不止一行，根据需要填写，写完描述空一行。

```javascript

/**
 * [description]
 * 
 * @module [modulename]
 * @author sumight
 */

```

## 函数注释

如果函数没有参数，也没有返回值，那么注释可以只有描述信息

例子紧跟在描述的下面，最后空一行。

将例子和描述放在一起是因为描述和例子都可能很长，而参数和返回值等重要信息需要和函数实体紧靠在一起。

```javascript

/**
 * [fun description]
 * Example:
 *      var name = fun('小明'');
 *      var hello = name + ' 你好';
 * 
 * @param  {[type]} name [description]
 * @return {[type]}      [description]
 */
function fun(name){

    return name;

}

```

## 关键变量注释

```javascript

/**
 * [cfg description]
 * 
 * @type {Object}
 */
var cfg = {};

```

## 语句注释

```javascript

// 计算 a 和 b 的和
x = a + b;

```

## TODO注释

TODO 用来标记下次需要做的工作，相当于一个标签，在一段代码没有完成的时候可以使用doto来标记未完成的代码位置

```javascript

// TODO 计算多个数的和
x = a + b + ;

```
