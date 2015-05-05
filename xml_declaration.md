# XML 声明

本章详细介绍了 XML _声明_。XML 声明包含准备 XML 处理程序解析 XML 文档的详细信息。它是可选的，但是在使用时它必须出现在 XML 文档的第一行。

## 语法

下面展示了 XML 声明的语法：

```
<?xml
	version="version_number"
	encoding="encoding_declaration"
	standalone="standalone_status"
?>
```

其中每个参数都由参数名，等号（=）以及用引号包裹的参数值组成。下面的表格展示了上述语法的详细信息：

<table>
	<thead>
		<tr>
			<th>参数</th>
			<td>参数值</td>
			<th>参数说明</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>版本（Version）</td>
			<td>1.0</td>
			<td>指定所用 XML 标准的版本。</td>
		</tr>
		<tr>
			<td>编码（Encoding）</td>
			<td>UTF-8, UTF-16, ISO-10646-UCS-2, ISO-10646-UCS-4, ISO-8859-1 to ISO-8859-9,ISO-2022-JP,Shift_JIS, EUC-JP</td>
			<td>定义文档中使用的字符编码。默认使用 UTF-8 编码。</td>
		</tr>
		<tr>
			<td>Standalone</td>
			<td>yes 或 no</td>
			<td>通知解析器文档是否以来外部源信息，比如外部文档类型定义（DTD）的内容。默认值为 no。设置为 yes 会告诉处理成西解析文档时不需要外部声明。</td>
		</tr>
	</tbody>
</table>

## 规则

XML 声明应该遵守下列规则：

- 如果 XML 声明出现在 XML 中，必须把它放在这个 XML 文档的第一行。
- 如果包含 XML 声明，就必须包含版本号属性。
- 参数名和值区分大小写。
- 放置参数的顺序很重要。正确的顺序是：_version_，_encoding_ 和 _standalone_。
- 可以使用单引号或双引号。
- XML 声明没有闭合标签，比如`</?xml>`。

### XML 声明示例

下面是一些关于 XML 声明的示例。

不带参数的 XML 声明：

```
<?xml >
```

带版本定义的 XML 声明：

```
<?xml version="1.0">
```

带所有参数定义的 XML 声明：

```
<?xml version="1.0" encoding="UTF-8" standalone="no" >
```

所有参数定义使用单引号包裹值的 XML 声明：

```
<?xml version='1.0' encoding='iso-8859-1' standalone='no' >
```