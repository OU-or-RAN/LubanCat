#### Git原理以及使用详解
> **Git详解**
>>[*Git Principles*](Git%20Principles.md)


#### 1. 创建远程Repository

打开浏览器登录到GitHub网址：https://github.com/

1. 如有账号则直接创建remote repo
		1.  登录到home页面
			home页面如下：
			![](../attachments/QQ_1767167631694.png)
			找不到的话可以点击左上角的三条横杠
			![](../attachments/QQ_1767167806769.png)
			点击后可以看到菜单，在菜单中点击home跳转到home页面
			![](../attachments/QQ_1767167829980.png)
		2.  创建new repo
			点击红框的两个按钮都可以进行仓库的创建
			![](../attachments/QQ_1767168518680%201.png)进入创建页面后，创建仓库名，添加仓库描述（也可暂时不添加），点击选择是否公开仓库，公开选public，不公开选private，**注意：公开的话其他人也可以访问获取到你的仓库，不公开的话只有自己可以读写**，根据自己项目的具体需求来选择；                                        ![](../attachments/Pasted%20image%2020251231161908.png)
#### 同步操作过程log
![](../attachments/QQ_1766901259932.png)
这是**Git 2.35+的安全机制**：
当仓库位于【文件系统不记录所有者】或【当前用户与目录属主不一致】时，就会报：
>[!failure]
>`fatal: detected dubious ownership in repository at 'F:/storage~~~~~~'` 

在Windows /外置硬盘/WSL/网络盘/同步盘（如OneDrive、Obsidian Vault）种很常见

>**如何忽略上传一个文件夹内的内容？**
>**注意ignore文件中的文件名不要带有空格**

>[!example]
>Daily Notes && DailyNotes
>>- 前一个文件名写进gitignore后该文件夹还是被上传至了github
>>- 后一个成功被忽略

>[!question]
>**如何使得MD内的图片内容可以被displayed在github或其他上面而非以链接形式展现？**
>
>这里需要使用MD的标准链接语法而非WikiLink语法
>>>*[外部链接（标准MD链接语法）](../MD%20Grammar/MD%20Grammar.md#^1510c4)*
>
>**如何通过Obsidian来commit、push、pull等git操作？**
>
>这里涉及到ssh连接是否成功的问题，你出现问题的本质原因在于你**重启Git bash**后，**触发了Git环境刷新**，这使得之前找不到的.ssh文件现在可以找到了(*路径解析成功*)，因此.ssh中的key可以成功被找到，从而能够通过GitHub身份认证而成功连接。
>
>>>*[什么操作会触发 Git 环境刷新，如何查看 SSH 使用的真实路径](../study%20log/Git%20Sync/SSH查找.ssh标准流程.md)*

因为之前成功建立了ssh链接，所以一直使用的时之前的ssh权限

>**variables**：
>>- if characters in path name is invalid
>>- if the path can be found successfully 

