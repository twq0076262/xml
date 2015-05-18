# XML 注释

本章解释了 XML 文档中的注释是如何工作的。XML 注释与 HTML 注释类似。注释被用来添加说明或者理解某行 XML 代码。

注释可以用来包含相关链接，信息和术语。它们只在源代码中可见，而不是 XML 代码中。注释可以出现在 XML 代码的任何地方。

## 语法

XML 注释语法如下所示：

```
<!-------Your comment ----->
```

注释以 <!-- 开始，以 --> 结尾。我们可以在这两个字符之间添加文本说明。但是注释不能嵌套。

## 示例

下面是在 XML 文档中使用注释的一个演示示例：

```
<?xml version="1.0" encoding="UTF-8" ?>
<!---Students grades are uploaded by months---->
<class_list>
	<student>
		<name>Tanmay</name>
		<grade>A</grade>
	</student>
</class_list>
```

<!-- 和 --> 字符之间的文本都被视为注释。

## XML 注释规则

下面是 XML 注释需要遵循的规则：

- 注释不能出现在 XML 声明之前。
- 注释可以出现在文档的任何位置。
- 注释不能出现在属性值中。
- 注释不能嵌套在其他注释中。
