#### Git原理以及使用详解
> **Git详解**
>>[*Git Principles*](Git%20Principles.md)

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

