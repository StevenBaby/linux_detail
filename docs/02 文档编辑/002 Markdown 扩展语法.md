# 2.2 Markdown 扩展语法

旧版本：

> https://www.bilibili.com/video/BV17i4y1w76F/

Markdown 扩展语法可以在 [^extend-syntax] 找到，可以得到更多详细信息,其中包括很多非标准语法。

## 删除线

~~我被删除线包围了~~，VSCode 中，你可以按下 ALT + S 来切换删除线的状态。

## 自动链接

Markdown 中可以使用 `<>` 尖括号来将URL包起来，就可以自动将其转换为链接，如下所示：

<http://www.example.com>

不过，VSCode 或大多数 Markdown 编辑器中甚至不需要 `<>` 就会自动识别链接，如下所示：

http://www.example.com

## 转义字符

反斜杠用于转义 Markdown 控制字符，例如：如果你想要用星号加在文字旁边的方式来做出强调效果（但又不想变成斜体），你可以在星号的前面加上反斜杠：

\*literal asterisks\*

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

```
\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
#   井字号
+   加号
-   减号
.   英文句点
!   惊叹号
```

## TODO 列表

如果想要 TODO 列表，可以使用如下定义，在列表前显示复选框状态：

- [ ] todo list
- [ ] Desktop 发布新版
    - [x] Markdown编辑器添加Todo list
    - [x] 修复白屏问题
    - [ ] 修复issue3
- [ ] Leanote 维护
    - [ ] 修复issue4

## 表格

我们知道默认情况下，Markdown 插入的表格，单元格中的内容默认左对齐；表头单元格中的内容会一直居中对齐（不同的实现可能会有不同表现）。

| 一个普通标题     | 一个普通标题 | 一个普通标题     |
| ---------------- | ------------ | ---------------- |
| 短文本           | 中等文本     | 稍微长一点的文本 |
| 稍微长一点的文本 | 短文本       | 中等文本         |

> VSCode中，可以按下 CTRL + SHIFT + F 来格式化 Markdown 文档。

或者需要对齐方式的话，需要加入 : 表示对齐的状态。

---

| 左对齐标题       | 右对齐标题 |   居中对齐标题   |
| :--------------- | ---------: | :--------------: |
| 短文本           |   中等文本 | 稍微长一点的文本 |
| 稍微长一点的文本 |     短文本 |     中等文本     |


语法说明：

- |、-、:之间的多余空格会被忽略，不影响布局；
- 默认标题栏居中对齐，内容居左对齐；
- -: 表示内容和标题栏居右对齐；
- :- 表示内容和标题栏居左对齐；
- :-: 表示内容和标题栏居中对齐；
- 内容和 | 之间的多余空格会被忽略，
- 每行第一个|和最后一个|可以省略，- 的数量至少有一个；

## 多行代码

在行开始添加四个空格可以表示代码

    这是一段代码
    而且多行也可以

可以使用 三个反引号` 表示多行代码，并且可以标注代码类型，如下所示，

这是一段 C 语言代码；

```C
#include <stdio.h>

int main()
{
    printf("hello world!!!\n");
    return 0;
}
```

这是一段 Python 代码；

```python
print('hello world!!!')
```

这是一段 Json

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

## 脚注

脚注需要插件 Markdown Footnotes [^footnotes]，可以为文本标记引用。

## 标题ID

你可以点击 [这里](#标题id) 进行页内跳转，点击 [这里](#表格) 可以跳转到表格。 [脚注](#脚注)

## HTML 标记

Markdown 兼容 HTML 标记，例如：

修改图片大小

<img src="./images/markdown.png" width="200" height="100">

---

显示图注

<figure>
    <img src="./images/markdown.png"
         alt="这是 Markdown 原理的流程图">
    <figcaption><center>这是 Markdown 原理的流程图</center></figcaption>
</figure>

---

外部链接

<a href="https://www.example.org" target="_blank">example.org</a>

## Markdown 目录

VSCode 中可以使用 Markdown All in One 来创建或更新目录。

- [2.2 Markdown 扩展语法](#22-markdown-扩展语法)
  - [删除线](#删除线)
  - [自动链接](#自动链接)
  - [转义字符](#转义字符)
  - [TODO 列表](#todo-列表)
  - [表格](#表格)
  - [多行代码](#多行代码)
  - [脚注](#脚注)
  - [标题ID](#标题id)
  - [HTML 标记](#html-标记)
  - [Markdown 目录](#markdown-目录)
  - [工具](#工具)
  - [References](#references)

## 工具

可以在 <https://www.markdownguide.org/tools/> 找到很多编辑和渲染 Markdown 的工具。

## References

[^extend-syntax]: https://www.markdownguide.org/extended-syntax/
[^footnotes]: https://marketplace.visualstudio.com/items?itemName=bierner.markdown-footnotes