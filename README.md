# 学习报告
I wrote all my notes on git into my notebook and Word document before,so I need to retype  them.Well,It's wrong to stay in my happy comfort zone.
---
分成了两部分：MarkDown和git（待我整理一番）
* <a href="#md">MarkDown</a>
---
<a href="md">MarkDown</a>
# MarkDown
目录：<a href="md01">标题</a>//<a href="md02">列表</a>//<a href="md03">分割线</a>//<a href="md04">表格</a>//<a href="md05">引用</a>//<a href="#md">md06</a>//<a href="md07">链接</a>//<a href="md08">代码</a>
<a name="md01"></a>
## 一、标题
一到六级标题不多描述。
 ---
<a name="md02"></a>
## 二、列表
### 无序列表
符号之后的空格不能少，-+*效果一样，但不能混合使用
+ 文本一
+ 文本二

- 文本一
- 文本二

* 文本一
* 文本二
### 有序列表
1.文本一
2.文本二
3.文本三
### 嵌套列表
有序与无序，以及有序和无序列表本身都是可以自由的嵌套的。
Markdown 中的列表嵌套，通过在符号前==增加空格==来表示。
==同一级别下，前面的空格数目应该保持一致。==
每递进一级，习惯上使用 2 个空格缩进来表示。

- 一级列表 A
- 一级列表 B
  - 二级列表 A
  * 二级列表 B
    + 三级列表 A
- 一级列表 C
---
<a name="md03"></a>
## 三、分割线
三个或更多-_*，
必须单独一行，
可含空格。
例如以下形式，都可以表示为分割线。
```
---
- -    -
___
_   __
***
*  **
  *  *  *
  ```
  ---
<a name="md04"></a>
## 四、表格
**需要注意以下几点：**
> 1. 表格第一行为标题，样式会被特殊处理
>2. | 前后要留有空格
>3. 只要是三个 - 字符表示分隔线
>4. 通过 : 来区分，左对齐、居中、右对齐

例：
>| 1 | 2 | 3 |
| --- |:---:| ---:|
| aaa | bbbbbb | c |
| aaaaaa | b | ccc |

| 左对齐| 居中 | 右对齐 |
| ---   |:---: | ---:  |
| aaa   | bbbbb | c    |
| aaaaaa| b     | ccc  |
----
<a name="md05"></a>
## 五、引用 
> 一级引用
>> 二级引用
>>>三级
>>>>四级
>不另起一行的效果
>
>所以一定要多起一行
---
<a name="md06"></a>
## 六、字体和表格
| 1 | 2 |
| ----- |:---:| 
| *这是斜体*|	_这是斜体_|
|**这是粗体**|***这是粗斜体***|
|__这是粗体__|__这是粗体__|
|~~这是删除~~|~~这是删除~~|
|  |==背景高亮==|

---
<a name="md07"></a>
## 七、链接
### 超链接
图片与链接，在 Markdown 语法中表达类似，都是 [链接文字](链接地址) 这样的形式。
### 图片链接
图片需要在 [] 前增加一个 ! 以使得图片在网页上直接显示，而不仅仅是个链接形式。
![](图片链接地址)
![我喜欢的电视剧的剧照](http://i-7.vcimg.com/crop/b3c1bd63194d8e185ab83d4d6b3984f6178975%28600x%29/thumb.jpg)
### 索引链接
索引链接，本质上与前两种链接一致，只是索引链接将 [链接文字](链接地址) 分离为[链接文字][索引],  [索引]:链接地址 的形式。

例：
[Wikipedia Markdown 条目][1]
[1]:https://zh.wikipedia.org/wiki/Markdown
----
<a href="md08"></a>
## 八、代码
### 行内代码
这是一段行内代码，`System.out.println("article id: " + articleId);` 摘自 Redis 工程。
### 区块代码
如果要成块的引用代码，有两种方法，一种是用制表符缩进，另一种，则是用三个反引号 ```，将代码块包起来。
在三个反引号后，加上语言说明，例如 ```java 这样，便指定了之后的代码采用 java 的高亮。

```python
import time

currentTime = time.time() #Get current time
# Obtain the total seconds since midnight,Jan 1,1970
totalSeconds = int(currentTime)
# Get thd current second
currentSecond = totalSeconds % 60
# Get the current minutes
totalMinutes = totalSeconds // 60
# Compute the current minute in the hour
currentMinute = totalMinutes % 60
# Obtain the total hours
totalHours = totalMinutes // 60
# Compute the current hour
currentHour = totalHours % 24
# Display resultes  
print("Current time is ",currentHour,":",currentMinute,":",currentSecond,"GMT")
```
