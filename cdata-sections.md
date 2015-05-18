# XML 之 CDATA 片段

本章讨论了 XML 中的 CDATA 片段。术语 CDATA 就是字符数据。CDATA 被定义为不由解析器解析的文本块，但它被公认为标记。

标记中预定义的实体比如 &amp;lt;，&amp;gt;
和 &amp;amp; 需要手动输入并且通常难以阅读。这种情况下就可以使用 CDATA 片段。通过使用 CDATA 片段，我们可以告诉解析器文档的特定部分不包含标记，应该被当做普通文本对待。

## 语法

下面是 CDATA 片段的语法：

```
<![CDATA[
characters with markup
]]>
```

上面的语法由三个部分组成：

- __CDATA 开始部分__ - CDATA 以9个字符的分隔符__<![CDATA[__开头。
- __CDATA 结束部分__ - CDATA 以 __]]>__ 分隔符结尾。
- __CData 部分__ - 上面这两个标记之间的字符被解释为字符而不是标记。这个部分可以包含标记字符（<，> 和 &），但是它们会被 XML 处理程序忽略。

### 示例

下面的标记代码展示了 CDATA。其中写在 CDATA 片段中的字符都会被解析器忽略。

```
<script>
<![CDATA[
<message> Welcome to TutorialsPoint </message>
]] >
</script>
```

在上述的语法中，&lt;message&gt; 和 &lt;/message&gt; 之间的所有内容都会被当做字符数据而不是标记。

## CDATA 规则

XML CDATA 需要遵循以下规则：

- XML 文档任何位置的 CDATA 都不能包含 "]]>" 字符。
- CDATA 片段不可以嵌套。