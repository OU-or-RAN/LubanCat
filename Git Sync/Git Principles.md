
**Git工作流程图**：
![](../attachments/QQ_1766994740362.png)

DAG由每个commit对象组成，一个对象代表一个节点，Head指向当前分支，当前分支指向当前（新）commit，那创建不同的分支其实就是创建不同的commit指针？

![](../attachments/QQ_1766999530778.png)
git checkout 命令的操作对象不仅仅可以是name of branch，也可以是commit对象本身？如果是，那commit为什么会有名字，他不就是只有一个commit ID吗？