## Markdown 语法介绍
### 1.1 标题
**格式：**

&emsp;&emsp;# 一级标题<br>
&emsp;&emsp;## 二级标题<br>
&emsp;&emsp;### 三级标题<br>
&emsp;&emsp;#### 四级标题<br>
&emsp;&emsp;##### 五级标题<br>
&emsp;&emsp;###### 六级标题<br>

**效果：**

# 一级标题  
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

**快捷键：**<br>
&emsp;&emsp;通过左右中括号[]来控制标题级别`ctrl + shift + ]`<br>

### 1.2 字体效果
**格式：**

&emsp;&emsp;用一个 `*` 包含一段文本就是斜体的语法<br>
&emsp;&emsp;用 `**` 包含一段文本就是粗体的语法<br>
&emsp;&emsp;用 `***` 包含一段文本就是加粗斜体的语法<br>
&emsp;&emsp;用 `~~` 包含一段文本就是删除线的语法<br>

**效果：**

&emsp;&emsp;我是 **粗体**  &emsp;`ctrl + B`<br>
&emsp;&emsp;我是 *斜体*  &emsp;`ctrl + I`<br>
&emsp;&emsp;我是 ***加粗斜体***  &emsp; `ctrl + I B`<br>
&emsp;&emsp;我是 ~~删除线~~  &emsp; ` `<br>

### 1.3 排版格式
&emsp;&emsp;**空格** `&emsp;&npsb;`<br>
&emsp;&emsp;**换行** `<br>`<br>

### 1.4 列表
**有序列表：**
1. 有序列表1
1. 有序列表2
1. 有序列表3

**无序列表：**
* 无序列表文字前加'*'
* 无序列表文字前加'*'
* 无序列表文字前加'*'

+ 无序列表文字前加'+'
+ 无序列表文字前加'+'
+ 无序列表文字前加'+'

- 无序列表文字前加'-'
- 无序列表文字前加'-'
- 无序列表文字前加'-'

### 1.4 引用
>这是一句引用

### 1.5 代码
&emsp;&emsp;单行代码 `printf()`<br>

&emsp;&emsp;代码块:
```
int main(){
    printf("hello world!");
}
```

1.6 强调

### 1.7 链接

**格式：**<br>
&emsp;&emsp;`[我的博客](https://smilestal.github.io/)`

**效果：**<br>
&emsp;&emsp;[我的博客](https://smilestal.github.io/)

### 1.8 表格
1. 不管是哪种方式，第一行为表头，第二行分隔表头和主体部分，第三行开始每一行为一个表格行。
1. 列于列之间用管道符|隔开。原生方式的表格每一行的两边也要有管道符。
1. 第二行还可以为不同的列指定对齐方向。默认为左对齐，在-右边加上:就右对齐。

**格式：**
```
|姓名|性别|分数|
|-|-|-|
|小明|男|75|
|小红|女|79|
|小陆|男|92|

|左对齐|右对齐|居中对齐|
|:-|-:|:-:|
|小明|男|75|
|小红|女|79|
|小陆|男|92|
```

**效果：**

|姓名|性别|分数|
|-|-|-|
|小明|男|75|
|小红|女|79|
|小陆|男|92|

|左对齐|右对齐|居中对齐|
|:-|-:|:-:|
|小明|男|75|
|小红|女|79|
|小陆|男|92|

### 1.9 分割线
**格式：**

&emsp;&emsp;***<br>
&emsp;&emsp;---<br>
&emsp;&emsp;___<br>

**效果：**
***
---
___

### 1.10 图片
**格式：**<br>
&emsp;&emsp;`![图片Alt](图片地址 “图片Title”)`

**效果：**<br>
![我的公众号](http://data.imchenchao.com/blog/images/xiaobaicode.jpg "扫码关注")

**参考链接：**<br>
&emsp;&emsp;[VSCode使用Markdown](https://imchenchao.com/blog/MarkdownVSCode/)<br>
&emsp;&emsp;[Markdown语法](https://imchenchao.com/blog/markdownDemo/)