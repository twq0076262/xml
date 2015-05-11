# XML 处理指令

本章介绍了处理指令（PIs）。正如 [XML 1.0 推荐标准](http://www.tutorialspoint.com/) 中定义的：

> "处理指令（PIs）允许文档包含用于应用程序的指令。指令并不是文档字符数据的一部分，但是必须通过应用程序传递"。

处理指令可以用于将信息传递给应用程序。处理指令可以出现在文档任意位置的标记外部。可以出现在序言中，包括文档的类型定义（DTD），文本内容或者文档之后。

## 语法

下面是处理指令的语法：

```
<?target instructions?>
```

其中：

- __target__ - 标识指令指向哪个应用程序。
- __instruction__ - 字符，描述了应用程序要处理的信息。

处理指令以特殊的 <? 标记开始，以 ?> 结尾。处理的内容在遇到字符串 ?> 时立即结束。

## 示例

处理指令很少被使用。主要用于链接 XML 文档到样式表。下面是一个例子：

```
<?xml-stylesheet href="tutorialspointstyle.css" type="text/css"?>
```

这里，_target_ 就是 xml-stylesheet。_href="tutorialpointstyle.css"_ 和 _type="text/css"_ 就是数据或者目标应用程序用将要用来处理给定 XML 文档的_指令_。

在这种情况下，浏览器通过标示识别目标，XML 应该在显示之间被转换；第一个属性状态说明转换类型是 XSL，第二个属性指向它的位置。

## 处理指令规则

处理指令可以包含除了 ?> 组合之外的任意数据，它被解释为闭合指令。下面是两个有效的处理指令示例：

```
<?welcome to pg=10 of tutorials point?>

<?welcome?>
```