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
1. *内部链接*
	1. 没有alias：[[tasks you gonna do tomorrow]]
	2. [[tasks you gonna do tomorrow|link to inner note]]
	3. [[tasks you gonna do tomorrow#^315a19|link to inner note to certain line]]
	4. directly display the content linked to：![[tasks you gonna do tomorrow#^9ae893]]
	
2. *外部链接*
	[ChatGPT](https://chatgpt.com/)
	[Google](https://www.google.com/)
	……
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
![[Android_test0 1.png]]
2. **外部链接**
![](attachments/Android_test0.png)

# 11.Math Formular

$$
a^2 + b^2 = c^2(TeX 格式)
$$


























