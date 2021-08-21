# Markdown For Typora手册

***

## 概述

**Markdown**诞生自[Daring Fireball](https://daringfireball.net/)之手，[点击这里](https://docs.github.com/en/github/writing-on-github)可以找到最早版本的语法标准。然而，它的语法标准因解析器和编辑器而异，**Typora**使用的是[GitHub Flavored Markdown](https://docs.github.com/en/github/writing-on-github)标准。

目录
[toc]

## 块元件

### 段落和行间隔

段落，顾名思义就是由一行或多行文本组成的，以段为形式的结构。在Markdown语法中，段落间以一行以上的空行作分隔。在Typora中，你只需要按一下``Enter``就可以插入一个新的段落。

按``Shift``+``Enter``可以创建一个比段落间距更小的行间距。然而，大多数的Markdown解析器会忽略这个方式创建的行间距，但是你可以通过在这一行的最后插入两个空格``Space``或者插入``<br/>``令解析器强制识别。

### 标题

可以通过在一行的开头使用1-6个``#``符号来创建标题，对应1-6个级别的标题。例如：
```
# 这是一个一级标题
## 这是一个二级标题
###### 这是一个六级标题
```
在Typora中，在标题文本前输入``#``，然后按下``Enter``可以创建一个标题。

### 引用块

Markdown使用邮件风格的``>``符号来创建引用块。例如：

> 这是一个由两个段落组成的引用块。这是第一个段落。
> 
> 这是第二段。


> 这是一个由一个段落组成的引用块。这里由三个空行来分割两个引用块。

在Typora里，只需要输入``>``之后输入需要的引用内容就可以生成引用块格式。Typora在随后的输入过程中会自动为你添加``>``和行间隔。引用块内的引用也是被允许的，只需要在引用块内同样使用``>``即可。

### 列表

输入``*列表元素``将创建一个无序列表。（这里的``*``可以用``+``或``-``代替。）

输入``1. 列表元素``将创建一个有序列表。

例子：
```
## 无序列表
* 红色
* 绿色
* 蓝色

## 有序列表
1. 红色
2. 绿色
3. 蓝色
```

### 任务清单

任务清单是一种被``[ ]``或``[x]``标记的列表（未完成或完成）。
例如：
```
- 「 」一个任务列表事项
- 「 」可以有如下格式
- 「 」正常 **加粗** @提及 #1234 等
- 「 」未完成
- 「x」已完成
```
你可以点击事件前的任务框，从而切换任务清单事项中的状态。

### 代码块

Typora仅支持[GitHub Flavored Markdown](https://docs.github.com/en/github/writing-on-github)的代码块，而不是原始代码块的风格。

使用代码块非常简单，只需要输入\`\`\`并按下``Enter``就可以。另外还可以自定义代码块的语言，只需要在 \`\`\`后追加输入所需要的语法名称后，我们就会通过语法高亮来实现它。

这是一个例子：

```
function test() {
  console.log("notice the blank line before this function?")
}
```

语法高亮：
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

### 数学公式

你可以通过使用**MathJax**来实现<u>Latex</u>的数学符号的表达。

输入$$，然后按下``Enter``键就会弹出一个支持TeX/LaTeX语法的输入框，下面是一个例子：

$$
\mathbf{V}_1 \times \mathbf{V}_2 = \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} & \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} & \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$

在Markdown源文件中，数学的公式块是通过利用$$标记借用LaTeX语言来实现的：

```
$$
\mathbf{V}_1 \times \mathbf{V}_2 = \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} & \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} & \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$
```

更多细节可以[点击这里](https://support.typora.io/Math/)。

### 表格

输入``|标题一|标题二|``然后按下``Enter``将会创建一个有两个列的表格。

表格创建之后，你会看到一个顶部工具栏也会随之出现，通过工具栏你可以实现调整大小，增添和删除表格的功能，你也可以使用

下面的描述可以跳过，因为表格的源码语法是Typora自动生成的。

在markdown语法中，它们如下所示：
```
| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
```
效果如下：

| First Header | Second Header |
| ------------ | ------------- |
| Content Cell | Content Cell |
| Content Cell | Content Cell |

你也可以修饰内部的文本格式，比如链接、粗体、斜体、删除线等。

最后，通过使用冒号：你可以实现标题栏文字的对齐功能，比如向左对齐、向右对齐和居中对齐：
```
| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
```
效果如下：

| Left-Aligned | Center Aligned | Right Aligned |
| :------------ | :-------------: | ------------: |
| col 3 is | some wordy text | $1600 |
| col 2 is | centered | $12 |
| zebra stripes | are neat | $1 |

最左侧的：是向左对齐；最右侧的：是向右对齐；两侧各一个：是居中对齐。

### 脚注

你可以创建一个脚注，如下所示：
```
脚注示范[^这是一个脚注]
```
上面的语法会编译成：

脚注示范[^这是一个脚注]

鼠标移动到这是一个脚注超链接可以看到脚注的文本内容。

### 分割线

在一个空行输入``***``或``---``并按下``Enter``将会创建一条分割线。

***

### YAML Front Matter

Typora现在支持[YAML Front Matter](https://jekyllrb.com/docs/front-matter/)了，在文章的顶部输入```---```然后按下```Enter```就会创建。或者从菜单插入一个元数据块。

### 目录

输入```[toc]```然后按下```Enter```就会产生一个自动根据标题和标题等级自动创建的目录框。

### 实时元件

实时元件将会在你输入完成后立即解码和编译完成。通过鼠标移动到这些语法元件上会显示出这些元件的源码内容，下面就将逐一介绍这些实时元件。

### 链接

Markdown 支持两种类型的链接：直连链接和间接链接。
在上面两种链接类型中，链接文本都用```[方括号]```分隔。

#### 内联链接

将```()```中的链接换成文档的标题，这样可以通过点击这个链接就能实现文档间的跳转。
例如：

```
这是一个[内联链接](Markdown For Typora)。
```
语法效果如下：

这是一个[内联链接](Markdown For Typora)。

#### 内部链接

创建一个内部链接即创建一个书签，使用标题作为链接允许你在点击之后跳转到该部分。
例如：
```
这是一个[内部链接](#概述)
```
效果如下：

这是一个[内部链接](#概述)

#### 参考链接

参考链接使用第二个方括号放置一个标签来标识链接。
```
这是一个[示例][标签]参考链接。
```
然后，在文档中任意位置定义你的链接：
```
[标签]: http://example.com/ “可选链接标题”
```
在Typora中，它们将这样呈现：

这是一个[示例][标签]参考链接。

[标签]: http://example.com/ “示例网”

链接名称可以被省略，在这种情况下，链接文本本身用作名称。只需要使用一组空的方括号——例如，要将Google一词链接到google.com网站，可以简单地编写：
```
[Google][]
然后定义链接：
[Goole]: http://google.com/
```
在Typora中，单击链接将展开它以进行编辑，``ctrl``+单击将在Web浏览器中打开超链接。

### 网址

Typora允许将URL作为链接插入，并用<括号括起来>。例如``<i@typora.io>``变成<i@typora.io>。

Typora还会自动链接标准URL（例如：www.google.com ） 而无需这些括号。

### 图像

图像的语法与链接相似，但它们需要在链接开始前输入一个额外的字符``！``。插入图像的语法如下所示：
```
![图片名称]（图片路径）

![图片名称]（图片路径 "可选标题"）
```
你可以使用拖拽操作从图像文件或Web浏览器实现插入图片的操作。随后可以通过点击图片来编辑语法的源码达到进一步修饰图片的效果。如果图片文件和所编辑的markdown文档在相同目录或亚目录则拖拽操作会自动生成对应的相对路径。

如果要使用markdown构建网站，则可以在YAML Front Matter中使用typora-root-url属性为本地计算机上的图像预览指定URL前缀。例如：在YAML Front Matter输入``typora-root-url:/User/Abner/Website/typora.io/``，然后Typora中的``![图片名称](/blog/img/test.png)``将被处理为``![图片名称](file:///User/Abner/Website/typora.io/blog/img/test.png)``。

### 斜体

Markdown识别``*``和``_``作为斜体的标识，用一个``*``或``_``修饰的文本会用HTML的标签``<em>``标记文本，例如：
```
*一个星号*

_一个下划线_
```
效果如下：

*一个星号*

_一个下划线_

GFM会忽视掉单词中的下划线，这是代码和名称中常用的，如下所示：

> wow_great_stuff
> 
> do_this_and_do_that_and_another_thing

要在原本用作斜体标识符的位置显示星号或下划线，可以使用反斜杠字符将其转义：

```
\*这个文本是被乘号修饰的，但是但不会变成斜体\*
```
效果如下：

\*这个文本是被乘号修饰的，但是但不会变成斜体\*

注：Typora推荐使用``*``符号

### 加粗

两个``*``或``_``连用将会产生一个HTML标签``<strong>``实现加粗的效果。
```
**两个星号连用**
__两个下划线连用__
```
效果如下：

**两个星号连用**
__两个下划线连用__

注：Typora推荐使用``*``符号

### 代码

用两个反引号\`修饰表示正常段落中的代码。例如：
``
使用`printf()`功能。
``
效果如下：

使用`printf()`功能。

### 删除线

GFM添加了创建删除线文本的语法，这是标准Markdown所缺少的。

`~~错误的文本~~`显示为~~错误的文本~~。

### 表情符号:happy:

输出表情需要用``:``符号修饰。为方便起见，在输入``:``表情符号名称开头后将自动触发表情建议补全功能。也支持从菜单栏``编辑``->``表情与符号``插入UTF8表情符号。

### 内嵌数学符号

要使用此功能，需要在偏好设置中启用它。然后，用``$``包装LaTeX命令。
例如：$\lim_{x \to \infty} \exp(-x) = 0$。

要触发内嵌数学的内嵌预览：输入``$``，然后按``ESC``键，然后输入TeX命令。

### 下标

要使用此功能，需要在偏好设置中启用它。然后，用``~``修饰下标内容。
例如：``H~2~O``显示为H~2~O，``X~long\ text~``显示为X~long\ text~。

### 上标

要使用此功能，需要在偏好设置中启用它。然后，用``^``修饰上标内容。
例如：``X^2^``显示为X^2^。

### 高亮

要使用此功能，需要在偏好设置中启用它。然后，用``==``修饰高亮内容。
例如：``==高亮==``显示为==高亮==。

## HTML

Typora补充了Markdown所不支持的HTML内容设置样式。
例如，``<span style="color:red">这是红色。</span>``显示为<span style="color:red">这是红色。</span>。

### 下划线

GRM的Markdown中没有指定下划线，但可以使用下划线HTML标签生成：
<u>下划线></u>变成下划线。

### 嵌入内容

一些网站提供基于iframe的嵌入代码，可以将其粘贴到Typora中。
例如：
```
<iframe height='265' scrolling='no' title='Fancy Animated SVG Menu' src='http://codepen.io/jeangontijo/embed/OxVywj/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>
```
语法效果如下：
<iframe height='265' scrolling='no' title='Fancy Animated SVG Menu' src='http://codepen.io/jeangontijo/embed/OxVywj/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>

### 视频

可以使用<video>HTML标签来嵌入视频。
例如：
```
<video> src="xxx.mp4" />
```

### 其他HTML支持

了解详情请[点击这里](https://support.typora.io/HTML/)。