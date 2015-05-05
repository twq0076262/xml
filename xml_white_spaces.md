# XML 空白

本章讨论了 XML 文档中的空白处理。空白就是空格，制表符和换行符集合。它们通常被用来让文档内容更可读。

XML 文档包含两个类型的空白 __(a)__ 有效空白和 __(b)__ 无效的空白。下面的例子解释了这两中类型的空白。

## 有效空白

有效空白在元素同时包含文本和标记时发生。例如：

```xml
<name>TanmayPatil</name>
```

和

```xml
<name>Tanmay Patil</name>
```

上面的两个元素是不同的，因为 __Tanmay__ 和 __Patil__ 之间的空白不一样。任何程序读取 XML 文件中的这种元素时都必须保持它们的区别。

## 无效空白

无效空白意味着只允许在元素内容中出现。例如：

```xml
<address.category="residence">
```

或者

```xml
<address....category="..residence">
```

上面两个例子是一样的。这里，我们通过点号(.)表示空白。在上面的例子中，_address_ 和 _category_ 之间的空白是无效的。

我们还给元素附加一个特殊的属性 __xml:space__。这表示元素的空白不应该由应用程序移除。我们可以设置这个属性为 __default__ 或者 __preserve__。正如下面的例子所示：

```xml
<!ATTLIST address xml:space (default|preserve) 'preserve'>
```

这里：

- 值 __default__ 表示这个元素可以接受应用程序的默认空白处理模式。
- 值 __preserve__ 表示应用程序会保护所有的空白。