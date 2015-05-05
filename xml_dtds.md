# XML 文档类型定义（DTDs）

XML 文档类型定义，俗称 DTD，它是一种准确描述 XML 语言的方式。DTDs 根据适当 XML 语言的语法规则检查 XML 文档的词汇和结构的有效性。

XML DTD 可以指定在文档内部，也可以保存在单独的文档中然后单独链接。

## 语法

DTD 的基本语法如下所示：

```xml
<!DOCTYPE element DTD identifier
[
	declaration1
	declaration2
	........
]>
```

上述语法解释：

- __DTD__ 以 <!DOCTYPE 定界符开始。
- __element__ 用于告诉解析器从制定的根元素开始解析文档。
- __DTD identifier__ 是一个用于文档类型定义的标示符，它可以是一个指向系统中某个文件的路径或者连接到互联网上某个文件的 URL。如果 DTD 指向外部路径，则被成为__外部子集__。
_ __[]__ 内是一个可选的实体声明列表，被称作_内部子集_。

## 内部 DTD

如果元素生命在 XML 文档的内部则 DTD 被称为内部 DTD。为了指示它为内部 DTD，XML 声明中的 _standalone_ 属性必须设置为 __yes__。这意味着，声明的工作独立于外部源。

### 语法

内部 DTD 语法如下所示：

```xml
<!DOCTYPE root-element [element-declarations]>
```

这里 _root-element_ 是根元素的名称，_element-declarations_ 表示在哪里声明元素。

### 示例

下面是一个内部 DTD 的简单示例：

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
<!DOCTYPE address [
<!ELEMENT address (name,company,phone)>
	<!ELEMENT name (#PCDATA)>
	<!ELEMENT company (#PCDATA)>
	<!ELEMENT phone (#PCDATA)>
]>
<address>
	<name>Tanmay Patil</name>
	<company>TutorialsPoint</company>
	<phone>(011) 123-4567</phone>
</address>
```

我们来看一下上面的代码：

__开始声明__ - 使用如下语句开始 XML 声明：

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
```

__DTD__ - 紧跟在 XML 头后面，_文档类型声明_如下，通常被称为 DOCTYPE：

```xml
<!DOCTYPE address [
```

DOCTYPE 声明在元素名称的开头包含一个感叹号(!)。DOCTYPE 会通知与该 DTD 关联的 XML 文档的解析器。

__DTD Body__ - DOCTYPE 声明后面紧跟 DTD 体，这里我们声明元素，属性，实体和符号：

```xml
<!ELEMENT address (name,company,phone)>
<!ELEMENT name (#PCDATA)>
<!ELEMENT company (#PCDATA)>
<!ELEMENT phone_no (#PCDATA)>
```

许多元素都在这里通过 `<name>` 文档词汇声明。`<!ELEMENT name (#PCDATA)>` 定义元素_名称_为 "#PCDATA" 类型。这里 #PCDATA 意味着可解析的文本数据。

__结束声明__ - 最后，DTD 的声明部分使用方括号和尖括号（]>）声明。这是一个有效的定义，后面紧跟的就是 XML 文档内容。

### 规则

- 文档类型声明必须出现在文档的开头部分（只先与 XML 头)，不允许出现在文档的任意其他位置。
- 类似于 DOCTYPE 声明，元素声明必须以感叹号开始。
- 文档类型声明中的 Name 必须与根元素的类型匹配。

## 外部 DTD

在外部 DTD 中元素声明在 XML 文档的外部。通过指定 system 属性来访问，这个属性值可以是合法的 _.dtd_ 文件或者有效的 URL。为了指示它是外部 DTD，XML 声明的 _standalone_ 属性比如设置为 __no__。这就意味着，声明包含来自外部源码的。

### 语法

下面是外部 DTD 的语法：

```xml
<!DOCTYPE root-element SYSTEM "file-name">
```

这里 _file-name_ 就是 _.dtd_ 扩展的文件。

### 示例

下面的示例展示了外部 DTD 的用法：

```xml
<?xml version="1.0" encoding="UTF-8" standalone="no" ?>
<!DOCTYPE address SYSTEM "address.dtd">
<address>
	<name>Tanmay Patil</name>
	<company>TutorialsPoint</company>
	<phone>(011) 123-4567</phone>
</address>
```

DTD 文件 __address.dtd__ 的内容如下所示：

```xml
<!ELEMENT address (name,company,phone)>
<!ELEMENT name (#PCDATA)>
<!ELEMENT company (#PCDATA)>
<!ELEMENT phone (#PCDATA)>
```

### 类型

我们可以通过使用__系统标示符__或者__公共标示符__引用一个外部DTD。

__系统标示符__

系统标示符允许我们指定包含 DTD 声明的外部文件的位置。语法如下：

```xml
<!DOCTYPE name SYSTEM "address.dtd" [...]>
```

正如我们可以看到的，它包含 SYSTEM 关键字和一个指向文档位置的 URI 引用。

__公共标示符__

公共标示符提供了一种定位 DTD 资源的机制，写法如下：

```xml
<!DOCTYPE name PUBLIC "-//Beginning XML//DTD Address Example//EN">
```

正如我们可以看到的，它以 PUBLIC 关键字开始，后面紧跟的是专门的标识符。公共标识符被用来标识目录中的条目。公共标识符可以遵循任意格式，但是常用的格式是_正式公用标识符_（或者 _FPIs_）。