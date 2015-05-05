# XML 元素

XML 元素可以被定义为 XML 的构建块。元素可以标签为承载文本，元素，属性，媒体对象或这有这些的容器。

每个 XML 文档都包含一个或多个元素，其范围由开始和结束标签界定，或者用一个空元素标签表示空元素。

## 语法

下面是编写 XML 元素的语法：

```
<element-name attribute1 attribute2>
....content
</element-name>
```

这里

- __element-name：__ 表示元素的名称。开始和结束标签之间的_名称_必须匹配。
- __attribute1, attribute2：__ 就是由空格分隔的元素属性。属性（attribute）定义了元素的属性（property）。它关联一个名称和字符串值。属性被写作如下形式：

```
alue"
```

属性_名称_后紧跟一个 = 号以及使用双引号（" "）或者单引号（" "）包裹的字符串_值_。

## 空元素

空元素（没有内容的元素）语法如下所示：

```
<name attribute1 attribute2.../>
```

下面是一个使用各种不同 XML 元素的 XML 文档：

```
<?xml version="1.0"?>
<contact-info>
	<address category="residence">
		<name>Tanmay Patil</name>
		<company>TutorialsPoint</company>
		<phone>(011) 123-4567</phone>
	<address/>
</contact-info>
```

## XML 元素规则

XML 元素需要遵循以下规则：

- 元素_名称_可以包含任意字母数字字符。在名称中唯一允许使用的标签符号是连字符（-），下划线（_）和句点（.）。
- 元素名称区分大小写。例如，Address，address 和 ADDRESS 是不同的元素名。
- 元素的开始和结束标签必须相同。
- 一个元素就是一个容器，它可以包含文本或者元素，正如上面的例子中可以看到。