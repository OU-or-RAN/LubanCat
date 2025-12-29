
**Git工作流程图**：
![](../attachments/QQ_1766994740362.png)

>[!question] branch本质上是指向commit的指针？
>DAG由每个commit对象组成，一个对象代表一个节点，Head指向当前分支，当前分支指向当前（新）commit，那创建不同的分支其实就是创建不同的commit指针？
>该DAG中的节点只能是commit对象吗，还是tree对象也可以？如果是的话tree为什么可以？

![](../attachments/QQ_1766999530778.png)

>[!questoion] 
>git checkout 命令的操作对象不仅仅可以是name of branch，也可以是commit对象本身？如果是，那commit为什么会有名字，他不就是只有一个commit ID吗？
>为什么每一个commit都要保存tree
>HEAD指向对象的变化全过程，什么叫当前commit对象？

想找到某commit有两种方式：
1. 创建指向该commit的branch
2. 创建该commit的Tag

![](../attachments/QQ_1767004957825.png)

>[!question]
>这里的A、B、C、D仅仅是节点名吗，还是branch名、Tag又或者是commit ID？
>`git reset --hard B`
>这里为什么直接用B这个节点名
