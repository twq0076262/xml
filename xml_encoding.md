# XML 编码

__编码__就是转换 Unicode 字符为等价二进制表示的过程。XML 处理程序读取一个 XML 文档时，它依赖于编码类型来编码文档。因此，我们需要在 XML 声明中制定编码类型。

## 编码类型

主要有两种类型的编码：

- UTF-8
- UTF-16

UTF 表示 _UCS 转换格式_，而 UCS 本身的意义是通用字符集。编号 8 或者 16 表示呈现字符的比特数。它们是 8（一个字节）或者 16（两个字节）。对于没有编码信息的文档，默认使用 UTF-8。

## 语法

编码信息包含在 XML 文档的序言部分。UTF-8 编码的语法如下：

```
<?xml version="1.0" encoding="UTF-8" standalone="no" ?>
```

UTF-16 编码语法如下：

```
<?xml version="1.0" encoding="UTF-16" standalone="no" ?>
```

### 示例

下面的例子展示了编码声明：

```
<?xml version="1.0" encoding="UTF-8" standalone="no" ?>
<contact-info>
	<name>Tanmay Patil</name>
	<company>TutorialsPoint</company>
	<phone>(011) 123-4567</phone>
</contact-info>
```

在上面的 __encoding="UTF-8"__ 示例中，指定使用 8 位表示字符。要使用 16 为表示字符，可以使用 __UTF-8__ 编码。

使用 UTF-8 编码的 XML 文件尺寸比 UTF-16 格式的文件更小。