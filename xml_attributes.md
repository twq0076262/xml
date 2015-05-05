# XML 属性

本章介绍了 XML 属性。属性是 XML 元素的一部分。一个元素可以有多个唯一属性。属性提供了有关 XML 元素更多的信息。更确切的说，它们定义了元素的属性（property）。XML 属性始终是一个_名-值_对。

## 语法

XML 属性语法如下：

```
<element-name attribute1 attribute2 >
....content..
</element-name>
```

这里 _attribute1_ 和 _attribute2_ 具有以下形式：

```
name = "value"
```

_value_ 必须使用双引号（" "）或单引号（" "）包裹。合理 _attribute1_ 和 _attribute2_ 都是唯一的属性标签。

属性被用来给元素添加一个唯一标签，分类标签，添加布尔值属性或者关联一些字符串数据。下面的示例演示了如何使用属性：

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE garden [
	<!ELEMENT garden (plants)*>
	<!ELEMENT plants (#PCDATA)>
	<!ATTLIST plants category CDATA #REQUIRED>
]>
<garden>
<plants category="flowers" />
<plants category="shrubs">
</plants>
</garden>
```

属性被用来区分同名元素。当我们不希望创建新元素时。我们可以使用属性添加一些详细用于区分两个或多个类似的元素。

在上面的例子中，我们通过包含 _category_ 属性分类了植物，并且给每个元素分配了不同的值。因此我们就由了两个 _plants_ 类别，一个是 _flowers_，另一个是 _color_。这样我们都得到了带有不同属性的两个 plants 元素。

还可以看到我们在 XML 的开头定义了这个属性。

## 属性类型

下表列出了属性的类型：

<table>
	<thead>
		<tr>
			<th>属性类型</th>
			<th>描述</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>StringType</td>
			<td>接受字符串值作为值。CDATA 是一个 StringType。CDATA 也是字符数据。这也意味着任何非标记字符都是合法的属性。</td>
		</tr>
		<tr>
			<td>TokenizedType</td>
			<td>
				<p>这是一个限制类型。语法中指出的有效性约束会在属性值规范化之后应用。下面是 TokenizedType 属性：</p>
				<ul>
					<li><b>ID：</b>用来指定元素是唯一的。</li>
					<li><b>IDREF：</b>用来引用一个ID，该ID命名了另一个元素。</li>
					<li><b>IDREFS：</b>用来引用一个元素的所有 IDs。</li>
					<li><b>ENTITY：</b>指示属性将表示文档中的一个外部实体。</li>
					<li><b>ENTITYS：</b>指示属性将表示文档中的一个外部实体。</li>
					<li><b>NMTOKEN：</b>类似限制哪些数据可以是属性一部分的CDATA。</li>
					<li><b>NMTOKENS：</b>类似限制哪些数据可以是属性一部分的CDATA。</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>EnumeratedType</td>
			<td>
				<p>在它的声明中包含一个预定义的值列表。在这里，它必须分配一个值。有两种类型的枚举属性：</p>
				<ul>
					<li><b>NotationType：</b>它声明元素在 XML 文档的某些地方将被引用为一个 NOTATION 声明。</li>
					<li><b>Enumeration：</b>枚举允许我们定义一个特定值列表，属性值必须与之匹配。</li>
				</ul>
			</td>
		</tr>
	</tbody>
</table>

## 元素属性规则

下面是声明属性需要遵循的规则：

- 同一起始标签或者空元素标签中属性名只能使用一次。
- 属性必须使用 Attribute-List Declaration 声明在文档类型定义（DTD）中。
- 属性值中不能直接或者间接引用包含外部实体。
- 属性值中被直接或间接提及的任何实体替代文本都不能包含小于号（<）。