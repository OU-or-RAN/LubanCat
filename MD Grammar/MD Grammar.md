# 1.标题

Markdown支持**六级**标题，使用#符号来表示，#的数量决定了标题的级别（1到6级）。

> [!example] 示例
>	#  一级标题										
>	##  二级标题
>	###  三级标题                            
>	####  四级标题                             
>	#####  五级标题                              
>	######  六级标题 				


[[tasks you gonna do tomorrow#^087ff4| 实际效果display]]


# 2.段落与换行


- 段落之间需要空一行 ^88f626
- 若要强制换行，可以在行尾添加两个空格，然后按下回车键


> [!example] 示例
> 第一行
> 同一段中的第二行
> 
> 第二段中的第一行
> 123
> 456
  
Markdown 换行主要有几种方式，其效果和兼容性各不相同。为了方便你理解，我将这几种方式整理成表格：

|方法|在Markdown源码中的输入方式|渲染后的效果与说明|
|---|---|---|
|**段落换行**|连续按**两次回车**，在两个段落间插入一个空行[](https://cloud.tencent.cn/developer/article/2181229?from=15425)[](https://zhuanlan.zhihu.com/p/536442037)。|效果等同于HTML的 `<p>` 标签，会开始一个**新的段落**，段落之间有明显间距。|
|**行内换行 (硬换行)**|在行尾先输入**两个空格**，再按一次回车[](http://t.zoukankan.com/mimifeng-p-3360881.html)[](https://gitee.com/pylog/blog-src/blob/master/markdown/4.md)[](https://juejin.cn/post/7174404825013026853)。|实现**单一行内换行**，新行仍属于同一段落，间距较小[](https://gitee.com/pylog/blog-src/blob/master/markdown/4.md)。|
|**使用HTML标签**|在需要换行处直接输入 **`<br>`** 或 **`<br/>`** 标签[](https://cloud.tencent.cn/developer/article/2181229?from=15425)[](https://gitee.com/pylog/blog-src/blob/master/markdown/4.md)。|**最可靠的强制换行**方法，所有兼容Markdown的环境都支持。|
|**编辑器快捷键** (部分编辑器支持)|在编辑时按 **`Shift` + `Enter`** (或 `Option`+`Return`)。|实质上是编辑器在行尾自动插入了两个空格或 `<br>` 标签来实现换行。|
# 3.序列

## 1.无序序列

- 123
- 456
- 789
	- 123
		- 456
			- 789
- 123

## 2.有序序列

1. 123
2. 456
	1. 789
		1. 123
			1. 456
			2. 789
		2. 456
	2. 123
3. 456
4. 123

# 4.CheckBox

- [ ] 1
- [ ] 2
- [ ] 3
	- [x] 1 ✅ 2025-12-27
	- [ ] 2
	- [ ] 3
		- [ ] 4
		- [x] 5 ✅ 2025-12-27
		- [ ] 6
	- [x] 1 ✅ 2025-12-27
	- [ ] 2
	- [ ] 3
- [ ] 1
- [ ] 2
- [ ] 3

# 5.Footnotes

>[!attention] 
>注意这里两种用法的区别
> 
1. 123456^[666]
2. 123456[^3]

[^3]:132456

# 6.Call Out

>common one（也叫引用）
>>son node
>>>grandson node
>>
>>son node 2
>
>common one

>[!note] 
>**note** 类型callout

>[!abstract]
>**abstract**类型callout

等等……

# 7.链接
1. *内部链接（Obsidian内部的WikiLink语法）*
	1. 没有alias：[[tasks you gonna do tomorrow]]
	2. [[tasks you gonna do tomorrow|link to inner note]]
	3. [[tasks you gonna do tomorrow#^315a19|link to inner note to certain line]]
	4. directly display the content linked to：![[tasks you gonna do tomorrow#^9ae893]]
2. *外部链接（标准MD链接语法）*
	[ChatGPT](https://chatgpt.com/)
	[Google](https://www.google.com/)
	…… ^1510c4
# 8.表
| item 1 | item 2 | item 3 |
|:------:|:------:|:------:|
|   1    |   2    |   3    |
|   4    |   5    |   6    |
|   7    |   8    |   9    |

# 9.code

1. code in line
`cout<<"to or not to be, that is the question."<<endl;`
2. code block
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;
using ll = long long;

// 判断在时间 s 内是否能让所有无人机保持电量 > 0
bool feasible(long long s, const vector<int>& a, long long k) {
    int n = a.size();

```

# 10.图片
>[!attention] 
>注意两者区别
>可通过GitHub查看
1. **内部链接**
`**这种属于Wikilink语法，是Obsidian生态下的语法，其他平台不一定兼容**`
![[Android_test0 1.png]]
2. **外部链接**
`**这是markdown标准链接语法，全球通用**`
![](attachments/Android_test0.png)

# 11.Math Formular

$$
a^2 + b^2 = c^2(TeX 格式)
$$

# 12.转义符“\”的用法

在特定符号前添加“\”符可以使其转变为普通符号如：
**\#** 此时该符号不**#**再表示标题
**\-** / **\+** 此时这两个符号不再表示无序列表
······
# 13.Tab健的用法

渲染结果：

1. 第一项  
    1.1 子项 1  
    1.2 子项 2
2. 第二项  
    2.1 子项 1
    1. 123  
    2.2 子项 2
    - 123
    - 123
    2.3 %% 123 %%
    

有序无序交叉形式具体形成过程：
**在形成第一个有序/无序列表项并填充内容后，点击回车，这是会自动补全第二项，为了交叉使用另外一种列表，先按回车（自动补全列表项消失，接着按tab，然后再按格式写无序/有序列表或者1.1，1.2之类的子项）**
在n级子项后想使用交叉列表程序：
**shift+enter** 直接换行而不会自动递增同级子项（为增加子项的子项）
**shift+tab** 取消缩进
在无序子项内容完成后，想连续之前的有序项操作方法：
- **shift+enter**
- 键入有序子项的序号如1.，2. ，3. 等等都可以，MD会自动改变数字序号，但不能通过无序列表的符号- 来代替，否则无法自动切换
- **shift+tab**直至与前一个有序项对齐
	- 如：
	  1. 123
	     - 123
	       1. 123
	       2. 465
	          - 123
	          - 456
	       3. 123
	  - 132
	    
	    
按tab还可能形成代码块


|场景|描述|示例|
|---|---|---|
|**列表项中的缩进**|在列表项内按 **Tab** 键会生成嵌套的代码块。|`- 第一项`  <br>`console.log('Hello')`|
|**空行后的缩进**|在空行后按 **Tab** 键会将该行文本识别为代码块。|`普通文本`  <br>`代码块文本`|
|**没有上下文的地方**|在普通文本行前按 **Tab** 键会让其成为代码块。|`普通文本`  <br>`代码块文本`|
|**增加代码块内的缩进**|在已经存在的代码块内，按 **Tab** 键来增加代码块的缩进。|`` `代码块内容` ``  <br>`console.log("Indented code")`|

	132
1. 123
2. 123
	1. 132
		1. 123
		   123
			1. 123
			   
					   123
					   123
