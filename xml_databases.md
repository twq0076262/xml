# XML 数据库

XML 数据库被用来以 XML 格式存储大量的信息。正如 XML 的使用在各个领域都在增长，因此需要有一个安全的地方存储 XML 文档。而存储在数据库中的数据可以使用 __XQuery__查询，序列化以及导出为需要的格式。

## XML 数据库类型

XML 数据库有两大类：

- 支持 XML 的数据库
- 原生 XML 数据库（NXD）

### 支持 XML 的数据库

支持 XML 的数据库不足为奇，但是它还提供了转转 XML 文档的扩展。它是关系型数据库，数据存储在由行和列组成的数据表中。这个表包含一组记录，由字段组成。

### 原生 XML 数据库

原生 XML 数据库基于容器而不是表格式。它可以存储大量的 XML 文档和数据。原生 XML 数据库可以使用 __XPath__ 表达式查询。

原生 XML 数据库具有支持 XML 的数据所有的优势。存储，查询和维护 XML 文档的能力比支持 XML 的数据库更强。

## 示例

下面的例子演示了 XML 数据库：

```xml
<?xml version="1.0"?>
<contact-info>
	<contact1>
		<name>Tanmay Patil</name>
		<company>TutorialsPoint</company>
		<phone>(011) 123-4567</phone>
	</contact1>
	<contact2>
		<name>Manisha Patil</name>
		<company>TutorialsPoint</company>
		<phone>(011) 789-4567</phone>
	</contact2>
</contact-info>
```

这里，我们创建了一个存储联系方式的表，保存了一些联系人记录（contact1 和 contact2），由三个实体 - _name_，_company_ 和 _phone_ 组成。