# XML 处理程序

当软件程序读取 XML 文档并采取相应的处理时，被称作 XML _处理_。任何可以读取和处理 XML 文档的程序都被视为 _XML 解析器_。XML 解析器会读取 XML 文件并把它转换成内存结构，以便程序的其余部分可以访问它。

大多数 XML 处理程序的基本原理就是读取 XML 文档并转换为内部表示便于其他程序或者子程序使用。也被称作_解析器_，它是每个 XML 处理程序的重要组成部分。

处理程序包括处理指令，我们会在[处理指令](xml_processing.md)章节进行研究。

## 类型

XML 解析器被分为__有验证__和__无验证__两种类型，取决于它们是否检查 XML 文档的有效性。一个处理程序发现有效性错误时必须能够发送报告，但也可以继续进行正常的处理。

__一些带验证的解析器：__ xml4c(IBM，基于 C++)，xml4j(IBM，基于 Java)，MSXML(Microsoft，基于 Java)，TclXML(TCL)，xmlproc(Python)，XML::Parser(Perl)，Java Project X(Sub，基于 Java)。

__一些无验证功能的解析器：__ OpenXML(Java)，Lark(Java)，xp(Java)，AElfred(Java)，expat(C)，XParse(JavaScript)，xmllib(Python)。