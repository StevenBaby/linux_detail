# 001 Markdown 文档编辑

## VSCode Profile

```json
{
    "security.restrictUNCAccess": false,
    "security.workspace.trust.enabled": false,
    "window.newWindowProfile": "Linux"
}
```

- 插件：git-commit-lint-vscode
- Open Preview to the Side: CTRL+SHIFT+V
- Preferences: Open User Settings (JSON): CTRL+SHIFT+,
- "editor.renderWhitespace": "all",
- "git.enableSmartCommit": true,

## 旧版本

- https://www.bilibili.com/video/BV1qz4y1r75K
- https://www.bilibili.com/video/BV17i4y1w76F
- https://www.bilibili.com/video/BV1M54y1x7BJ

## Markdown 简介

> Markdown [^markdown] 是一种轻量级的标记语言，可以用来为纯文本文档添加格式化元素。Markdown 由 John Gruber 于 2004 年创建，现在是世界上最流行的标记语言之一。
> 
> Markdown 与所见即所得的编辑器不同。在像 Microsoft Word 这样的应用程序中，你可以点击按钮来格式化单词和短语，更改立即可见。Markdown 不是这样的。当你创建一个 Markdown 格式的文件时，你需要在文本中添加 Markdown 语法来指出哪些单词和短语应该看起来不同。

Markdown 的优势是即使文件没有渲染，也依然能够很容易地通过简单的文本编辑器知道其中表达的信息。

> Markdown 格式语法的首要设计目标是使其尽可能可读。这个想法是，Markdown 格式的文档应该可以按原样以纯文本形式发布，而不是看起来像是用标签或格式说明标记的。

![John Gruber](./images/John%20Gruber.png) [^gruber]

## Markdown 的工作原理

![Markdown](./images/markdown.png)

这一过程由四部分组成的过程：

- 使用文本编辑器或专用 Markdown 应用程序创建 Markdown 文件。该文件的扩展名为 .md 或 .markdown；
- 在 Markdown 应用程序中打开 Markdown 文件；
- 使用 Markdown 应用程序将 Markdown 文件转换为 HTML 文档；
- 在 Web 浏览器中查看 HTML 文件，或使用 Markdown 应用程序将其转换为其他文件格式，如 PDF；

-----

Markdown 的基础语法可以在 [^cheat-sheet] 或者 [^basic-syntax] 找到。

## 标题

# 这里是一级标题
## 这里是二级标题
### 这里是三级标题
#### 这里是四级标题
##### 这里是五级标题
###### 这里是六级标题

这是另一种一级标题，下面有很多 =
===

这是另一种二级标题，下面有很多 -
-----

Markdown 一般要求一级标题文件中只出现一次，且在文件最开始的位置。

## 文本

这里是普通的文本，也是最常见最平凡的类型。

比较特殊的是，当你想要换行时，  
需要在行尾加上两个空格，
不然的话是不会换行的。

## 特殊字体

这里是 **加粗** 字体，字体两侧有 2 个 *，你可以在 VSCode 使用 CTRL+B 来标记或取消加粗的字体。

这里是 *斜体* 字体，字体两侧有 1 个 *，你可以在 VSCode 使用 CTRL+I 来标记或取消斜体。

这里是 ***粗斜体*** 字体，字体两侧有 3 个 *；

## 引用块

> 这里是一个引用块

---

> 这里是另一个引用块；
>> 你还可以嵌套引用块；
>>> 依次类推可以有更多的嵌套；

## 有序列表

1. 这是列表的第一个条目
2. 这是列表的第二个条目
3. 这里应该是第三个条目
4. ....  
    经过简单的缩进，可以些列表的内容
    > 你甚至可以在列表里加入引用块，其他的内容应该也可以
5. 这是另一个条目

## 无序列表

- 这是第一种无序列表
- ...

* 这是第二种无序列表
* ...

## 行内代码

- Markdown All in One: Toggle code span: ALT+D

我们在小学二年级的时候，学过 C 语言，它的第一个函数是 `main()`，但是在我刚开始学习的时候，总是写成 `mian()` 这导致了很多愚蠢的错误。

## 分割线

下面是一条华丽的分割线

---------------------

## 链接

这里是 [John Gruber](https://en.wikipedia.org/wiki/John_Gruber) 的 Wikipedia 地址。

## 图片

![Markdown](./images/markdown.png)

- "markdown.extension.print.absoluteImgPath": false

可以通过 `CTRL + SHIFT + P`, VSCode：Markdown All in One 将 Markdown 转换为 HTML

## References

[^markdown]: https://www.markdownguide.org/getting-started/
[^gruber]: https://en.wikipedia.org/wiki/John_Gruber
[^cheat-sheet]: https://www.markdownguide.org/cheat-sheet/
[^basic-syntax]: https://www.markdownguide.org/basic-syntax/