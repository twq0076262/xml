# XML 命名空间

命名空间就是一组唯一名称。命名空间是确定哪个元素和属性名可以被分配到某个组的一种机制。命名空间通过 URI（统一资源标示符）识别。

## 命名空间声明

命名空间使用保留属性声明。这种属性名必须是 __xmlns__ 或者以 __xmlns:__ 开头。如下所示：

```
<element xmlns:name="URL">
```

## 语法

- 命名空间以关键字 __xmlns__ 开头。
- __name__ 就是命名空间前缀。
- __URL__ 就是命名空间标识符。

## 示例

命名空间只影响文档中有限的区域。包含这个声明的元素以及其所有子元素都在命名空间范围之内。下面是一个 XML 命名空间的简单示例：

```
<?xml version="1.0" encoding="UTF-8"?>
<cont:contact xmlns:cont="www.tutorialspoint.com/profile">
	<cont:name>Tanmay Patil</cont:name>
	<cont:company>TutorialsPoint</cont:company>
	<cont:phone>(011) 123-4567</cont:phone>
</cont:contact>
```

这里，命名空间前缀是 __cont__，标示符（URI）是 _www.tutorialspoint.com/profile_。这意味着，带有 __cont__ 前缀元素名和属性名都（包括 contact 元素）属于 _www.tutorialspoint.com/profile_ 这个命名空间。