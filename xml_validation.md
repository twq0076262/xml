# XML 验证

__验证__ 就是对 XML 文档进行验证的过程。如果文档内容与元素，属性和关联的文档类型定义（DTD）文档编译与所表达的约束符合则该文档被认为是有效的。通过 XML 解析器处理验证的方式有两种。分别是：

- 格式良好的 XML 文档
- 有效的 XML 文档

## 格式良好的 XML 文档

如果 XML 文档遵守以下规则则被认为是__格式良好的__。

- 没有 DTD 的 XML 文档必须使用预定义的字符实体 __amp(&)，apos（单引号），g(>)，quot（双引号）__。
- 必须遵循标签的顺序，比如内部标签必须在外部标签闭合之前闭合。
- 每个开始标签必须都有一个结束标签或者必须是一个自闭合标签（`<title>...</title>` 或者 `<title />`）。
- 在开始标签中只能包含一个属性，并且需要使用引号包裹。
- 除了__amp(&)，apos（单引号），g(>)，quot（双引号）__实体之外其他的必须先声明在使用。

### 示例

下面是一个格式良好的 XML 文档示例：

```
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
<!DOCTYPE address
[
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

上面的示例被认为是格式良好的，因为：

- 它定义了文档类型。并且这里文档类型是__元素__类型。
- 包含一个名为 __address__ 的根元素。
- 每个子元素 name，company 和 phone 都是一个自解释正确闭合的标签。
- 标签的顺序正确。

## 有效的 XML 文档

如果一个 XML 文档是格式良好的并且有关联的文档类型定义（DTD），那么它被人为是一个有效的 XML 文档。我们会在 [XML DTDs](xml_dtds.md) 一章学习更多关于 DTD 的内容。