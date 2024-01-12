---
title: HTML要点
tags: [前端,HTML]
categories: 前端
abbrlink: 375ae22a
date: 2024-01-12 14:01:24
cover: 
---
# html要点

## 元素间关系

### 父元素

直接包裹某个元素的元素，就是该元素的父元素。

### 子元素

被父元素直接包含的元素。

### 祖先元素

父元素的父元素的……，这些都是祖先元素。

父元素也算是祖先元素的一种。

### 后代元素

子元素的子元素……，这些都是后代元素。

同理子元素也算后代元素的一种。

### 兄弟元素

具有相同父元素的元素互为兄弟元素。

## 元素显示方式

|              | 块级元素                                                     | 行内元素（内联）            | 行内块元素（内联块元素）                          |
| ------------ | ------------------------------------------------------------ | --------------------------- | ------------------------------------------------- |
| 是否独占一行 | 是，从上到下排列                                             | 否，从左到右排列，会换行    | 否，从左到右排列，会换行                          |
| 默认宽度     | 撑满父元素                                                   | 由内容撑开                  | 由内容撑开                                        |
| 默认高度     | 由内容撑开                                                   | 由内容撑开                  | 由内容撑开                                        |
| css设置宽高  | 可以                                                         | 不可以                      | 可以                                              |
| 举例         | html,body, h1,hr,p,div, ul,ol,li, table,tbody,thead, tr,caption, form,option | br, em,strong,span, a,label | img, td,th, input,textarea, select,button, iframe |

## 常用标签

### 排版布局标签

包括h1-h6（标题）、p标签（段落）。

h1-h6不能相互嵌套。

p标签内部不能嵌套标题标签或者是div，不能嵌套块元素。

H5新增：

| 标签    | 语义                                                       |
| ------- | ---------------------------------------------------------- |
| header  | 整个页面或者部分区域的头部                                 |
| footer  | 整个页面或者部分区域的底部                                 |
| nav     | 导航                                                       |
| article | 文章、帖子、杂志、评论等                                   |
| section | 页面中的某段文字，或文章中的某段文字（文字中通常包含标题） |
| aside   | 侧边栏                                                     |
| main    | 文档的主要内容，不过没有被赋予语义，不如直接div。          |

atricle里面可以有多个section；section强调分段，article比section更强调独立性。

**语义化标签**

标签的默认效果不重要，语义最重要。有利于SEO（搜索引擎优化），方便设备解析。

### 文本标签

| 标签       | 语义                                                         |
| ---------- | ------------------------------------------------------------ |
| em         | 要着重阅读的内容                                             |
| strong     | 重要的内容（比em强）                                         |
| span       | 没有语义，通用容器                                           |
| cite       | 作品标题(书籍、歌曲、电影、电视节目、绘画、雕塑)             |
| dfn        | 特殊术语，或专属名词                                         |
| del 与ins  | 删除的文本【与】插入的文本                                   |
| sub与sup   | 下标文字【与】上标文字                                       |
| code       | 一段代码                                                     |
| samp       | 从正常的上下文中，将某些内容提取出来，例如:标识设备输出      |
| kbd        | 键盘文本，表示文本是通过键盘输入的，经常用在与计算机相关的手册中 |
| abbr       | 缩写，最好配合上title属性                                    |
| bdo        | 更改文本方向，要配合dir属性，可选值: ltr(默认值，right to left) 、rtl |
| var        | 标记变量，可以与code标签一起使用                             |
| small      | 附属细则，例如:包括版权、法律文本。——很少使用                |
| b          | 摘要中的关键字、评论中的产品名称。—―很少使用                 |
| i          | 本意是:人物的思想活动、所说的话等等。<br />现在多用于:呈现字体图标（后面要讲的内容)。 |
| u          | 与正常内容有反差文本，例如:错的单词、不合适的描述等。—-很少使用 |
| q          | 短引用—―很少使用                                             |
| blockquote | 长引用――很少使用（注意是块元素）                             |
| address    | 地址信息（注意是块元素）                                     |
| ruby       | 里面写rt标签。ruby包含span以及rt，rt里面写注音               |
| mark       | 标记出需要注意的词，例如在搜索结果里面呈现。                 |

### 图片标签

```html
<img src="path" alt="描述">
```

### 超链接

```html
<a href="目标"></a>
```

a标签可以包裹除了自身的别的标签。href中的内容也可以是浏览器可以打开的文件。锚点跳转可以写“#name”，或者是“#id”，任何一个标签都能加id属性。如果只写一个`#`是回到顶部，如果href里面什么都不写是刷新页面。

| 属性     | 效果                                                         |
| -------- | ------------------------------------------------------------ |
| target   | `_blank`，表示在新标签页中打开；<br />`_self`，表示在当前标签页中打开；默认值是self |
| download | 强制触发下载。download=“文件.doc”，改变下载的文件名称。      |
| name     | 给标签一个名字，可以用于锚点跳转                             |

超链接可以唤起指定应用，通过href中写不同的内容：

```html
<!-- 唤起设备拨号 -->
<a href="tel:10010">电话联系</a>
<!-- 唤起设备发送邮件 -->
<a href="mailto:10910@qq.com">邮件联系</a>
<!-- 唤起设备发送短信 -->
<a href="sms:10886">短信联系</a>
```

### 列表

有序列表：ordered list，所以标签是`<ol>`;

无需列表：unordered list，所以标签是`<ul>`;

里面列表项：list items，所以标签是`<li>`。

自定义列表标签是`<dl>`，里面每一项需要一个`<dt>`和数个`<dd>`。

H5新增：

`<datalist>`双标签

里面用option包含每一个选项，能够实现模糊搜索，用户输入字匹配能够option中的内容。

`<details>`双标签，`<summary>`双标签

有details就要有summary，summary要卸载details里面，下面再用别的标签写具体意义。

### 表格

```html
<table>
    <!-- 表格标题 -->
    <caption>标题</caption>
    <!-- 表格头部 -->
    <thead>
        <!-- tr表示新一行 -->
        <tr>
            <th>表头1</th>
        	<th>表头2</th>
        	<th>表头3</th>
        </tr>
    </thead>
    <!-- 表格主体 -->
    <tbody>
        <!-- tr表示新一行 -->
        <tr>
            <td>数据a1</td>
            <td>数据a2</td>
            <td>数据a3</td>
        </tr>
        <tr>
            <td>数据b1</td>
            <td>数据b2</td>
            <td>数据b3</td>
        </tr>
    </tbody>
    <!-- 表格脚注 -->
    <tfoot>
        <!-- tr表示新一行 -->
        <td></td>
        <td></td>
        <td>共计数据</td>
    </tfoot>
</table>
```

要注意在`<table>`标签中调整表格的高度的时候，会优先补偿调整`<tbody>`部分的高度。

#### 表格属性

cellspacing=”0“，调整的是单元格之间的间距。

align="left"，水平对齐方式。

valign="middle"，垂直对齐方式。

#### 跨行跨列

对于th或者td的一个属性。

跨列是colspan，赋值为几就跨几列。

跨列是rowspan，赋值为几就跨几行。

赋给跨行跨列后大概率会出现单元格行上的溢出，只需要删除多余的单元格就可以。

### 表单

#### 基本结构

| 标签   | 语义   |
| ------ | ------ |
| form   | 表单   |
| input  | 输入框 |
| button | 按钮   |

action属性可以写提交去的地址。如果不写就是提交给自己。

H5新增了一个属性novalidate，表示不做任何校验。

#### 常用控件

##### 输入框

input标签。

type属性取值：

1. text：文本输入。
2. password：密码框。
3. radio：单选框。一般多个单选框需要设置同样的name。点击后选择到的是单选框的value。
4. checkbox：多选框。同样需要写相同的name以及各自的value。
5. hidden：隐藏域，隐藏该输入框。
6. submit：提交。转变为一个按钮，其value属性表示提交按钮的文字。不能写name。
7. reset：重置，转变为一个按钮，参照submit。
8. button：转变为一个普通按钮，value表示按钮上的文字。
9. email：自动校验邮箱合法。
10. url：校验网址。
11. number：数字类型。step属性可以规定每一次点击上下后的改变步长，也可以规定max和min。
12. search：可以快速清除所有已输入的文字。但是没有校验。
13. tel：用在PE端，弹出的是数字输入框。
14. range：范围选择器。一个滑动选择器，可以调max和min，value是默认值。
15. color：颜色选择器。
16. date：日期选择。
17. month：只能选择月份。
18. week：只能选择周。
19. time：选择时间。
20. datetime-local：日期+时间。

name属性：数据的名称。

value属性：输入框的默认值。

maxlength属性：输入框最大可输入长度。

checked属性：没有值，写这个属性表示这个选择框默认被选中。

placeholder：占位字。

required：没有值，写在谁身上谁就必填，写在多选框上必选。

autofocus：没有值，写在谁身上就自动聚焦在谁身上。

autocomplete：键值对，值只有on开启和off关闭。检测输入过的历史纪录，只能写在普通text输入框上。

pattern：正则表达式。限制不了多行输入。往往需要与required配合。

##### 按钮

button标签。

type属性取值：

1. submit（默认）：提交。
2. reset：重置。
3. button：一个普通按钮。

##### 文本域

textarea标签。

属性：cols：列数；rows：行数；name：名称。

##### 下拉框

```html
<select name="name1">
    <option value="选项一">选项一</option>
    <option value="选项二" selected>选项二</option>
    <option value="选项三">选项三</option>
</select>
```

其中name是指名称，传递的值是option标签中的value值。selected属性表示默认被选中的值。

##### H5新增



#### 禁用表单控件

一个属性disabled，表示禁用。

#### 其他标签

##### label标签

label标签属性：

for="控件的id"，关联到for的内容对应的控件。

实现关联还可以在一个label标签中包住input标签和说明，这样也能实现关联。

##### fieldset和legend标签

```html
<fieldset>
    <legend>分类1</legend>
    ...其他内容...
</fieldset>
```

### 框架标签

iframe

可以用于嵌入一个普通网页

```html
<iframe src="https://www.bilibili.com" width="200" height="100"></iframe>
```

也可以嵌入其他内容，例如本地文件。

还可以和a标签的target，或者是表单的target配合。

```html
<a href="https://www.bilibili.com" target="bili"></a>
<iframe name="bili" width="200" height="100"></iframe>
```

### 字符实体

| 字符实体           | 效果           |
| ------------------ | -------------- |
| `&nbsp;`、`&#160;` | 空格           |
| `&lt;`             | 小于号<        |
| `&gt;`             | 大于号>        |
| `&amp;`            | 与符号&        |
| `&yen;`            | 人民币￥       |
| `&copy;`           | 版权所有&copy; |
| `&times;`          | 乘号&times;    |
| `&divide;`         | 除号&divide;   |

具体见官网给出的[对照表](https://html.spec.whatwg.org/multipage/named-characters.html#named-character-references)。

### 全局属性

id：唯一标识。

class：类名。

style：设置样式。

dir：对齐。取值有rtl、ltr。但是用在bdo上是文字的顺序。

title：额外说明，鼠标悬浮的时候会有提示。

lang：设置语言。

其余见[官网](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes)。

#### H5新增

| 标签            | 效果                                              |
| --------------- | ------------------------------------------------- |
| contenteditable | 取值有true和false。表示用户是否可编辑。           |
| draggable       | 取值有true和false。表示用户是否可拖动。一般配合js |
| hidden          | 隐藏元素。不占位。                                |
| spellcheck      | 取值有true和false，拼写检查。                     |
| contextmenu     | 定制鼠标右键弹出的菜单                            |
| data-*          | 对于后面的*代表的私有定制数据。                   |

### meta元信息

配置网站基本信息，例如移动端适配、网页关键字、网页描述信息等等。具体见[官网](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta)，以及[标准元数据名称 ](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta/name)。

### H5新增状态标签

`<meter>`双标签。其属性：

| 属性    | 意义       |
| ------- | ---------- |
| max     | 最大       |
| min     | 最小       |
| value   | 当前值     |
| low     | 低值分界线 |
| high    | 高值分界线 |
| optimum | 规定最适值 |

`<progress>`双标签

一般是当前进度，属性有max和value。

### H5新增视频标签

video

| 属性     | 效果                                                         |
| -------- | ------------------------------------------------------------ |
| src      | 视频源                                                       |
| controls | 没有值，添加控制。                                           |
| muted    | 静音                                                         |
| autoplay | 自动播放，但是需要静音才能有效，但是会收到媒体参与度的影响，在一段时间内重复播放后，媒体参与度提高，就可以实现不静音也能自动播放。chrome浏览器媒体参与度查询[见此](chrome://media-engagement/)。 |
| loop     | 循环播放。                                                   |
| poster   | 值是一个具体的图片地址，改变视频封面。                       |
| preload  | 预加载。值有auto：浏览器自动协调；none：不预加载；metadata：加载最基本的信息。 |

B站的播放器开源，可以引用。

### H5新增音频标签

audio

| 属性     | 效果                                                         |
| -------- | ------------------------------------------------------------ |
| src      | 音频源                                                       |
| controls | 控制                                                         |
| autoplay | 自动播放。                                                   |
| muted    | 静音                                                         |
| loop     | 循环                                                         |
| preload  | 预加载。值有auto：浏览器自动协调；none：不预加载；metadata：加载最基本的信息。 |

### 其他杂项

#### 编码方式

一般使用的是UTF-8.

可以在head标签中增加如下语句来表示用的是什么编码方式。

```html
<mata charset="UTF-8">
```

#### 语言

在根元素html中加入`lang="zh-CN"`表示简体中文。

#### 一些常用标签

换行：br；

分割线：hr；

按照原文格式显示：pre

#### H5兼容性

IE8不支持H5.

利用script标签引入大厂的H5兼容性优化js文件。

或者使用meta元信息调整兼容性。

例如`<meta name="renderer" content="webkit">`，用于给一些国产双核浏览器看，表示优先使用webkit渲染。

#### 注释宏

```html
<!--[if lt ie 9]>
<script src="..."></script>
<![endif]-->
```

表示如果版本小于ie9，就运行宏之间的内容。

宏还有lte小于等于、gt大于、gte大于等于、！非。