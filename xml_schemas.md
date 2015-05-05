# XML 模式

XML 模式通常也被称做 XML 模式定义（XSD）。它被用来描述和验证 XML 数据的结构和内容。XML 模式定义元素，属性和数据类型。模式元素也支持命名空间。类似数据库中描述数据的数据库模式。

## 语法

我们需要在 XML 文档中声明模式，如下所示：

```
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
```

### 示例

下面的示例展示了如何使用模式：

```
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<xs:element name="contact">
	<xs:complexType>
		<xs:sequence>
			<xs:element name="name" type="xs:string" />
			<xs:element name="company" type="xs:string" />
			<xs:element name="phone" type="xs:int" />
		</xs:sequence>
	</xs:complexType>
</xs:element>
</xs:schema>
```

XML 模式背后的基本思想就是描述 XML 文档可以接受的合法格式。

## 元素

正如我们在 [XML 元素](xml_elements.md) 一章中所看到的，元素就是 XML 文档构建快。在 XSD 内可以像下面这样定义元素：

```
<xs:element name="x" type="y"/>
```

## 定义类型

我们可以按照以下方式定义 XML 模式元素：

__简单类型：__简单类型的元素只能用于文本上下文中。一些预定义的简单类型有：xs:integer，xs:boolean，xs:string，xs:data。例如：

```
<xs:element name="phone_number" type="xs:int" />
```

__复杂类型：__复杂类型就是其他元素定义的容器。允许我们指定哪些子元素可以包含元素以及为 XML 文档提供一些结构。例如：

```
<xs:element name="Address">
	<xs:complexType>
		<xs:sequence>
			<xs:element name="name" type="xs:string" />
			<xs:element name="company" type="xs:string" />
			<xs:element name="phone" type="xs:int" />
		</xs:sequence>
	</xs:complexType>
</xs:element>
```

上面的例子中，__Address__ 元素由子元素组成。它是其他 `<xs:element>` 定义的容器，允许我们在 XML 文档中构建一个简单的层级元素。

__全局类型：__对于全局类型，我们可以在文档中定义独立的类型，它还可以使用所有其他引用。例如，假设我们想针对不同的公司地址概括 _person_ 和 _company_。这种情况下，我们可以定义一个如下所示的通用类型：

```
<xs:element name="AddressType">
	<xs:complexType>
		<xs:sequence>
			<xs:element name="name" type="xs:string" />
			<xs:element name="company" type="xs:string" />
		</xs:sequence>
	</xs:complexType>
</xs:element>
```

然后在下面的示例中使用这个类型：

```
<xs:element name="Address1">
	<xs:complexType>
		<xs:sequence>
			<xs:element name="address" type="AddressType" />
			<xs:element name="phone1" type="xs:int" />
		</xs:sequence>
	</xs:complexType>
</xs:element>
<xs:element name="Address2">
	<xs:complexType>
		<xs:sequence>
			<xs:element name="address" type="AddressType" />
			<xs:element name="phone2" type="xs:int" />
		</xs:sequence>
	</xs:complexType>
</xs:element>
```

不再需要定义 name 和 compacny 两次（一次是给 _Address1_，一次给 _Address2_），现在我们拥有一个独立的定义。这让维护变得更简单，例如，如果我们决定给地址添加一个 "Postcode" 元素，只需要在一个地方添加即可。

## 属性

XSD 中的属性提供了额外的元素信息。带 _name_ 和 _type_ 属性（property）的属性（attribute）如下所示：

```
<xs:attribute name="x" type="y"/>
```