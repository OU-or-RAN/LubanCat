# SSH 到底按什么规则查找 `.ssh`？（权威标准流程）

OpenSSH 解析顺序如下：

### 1️⃣ 用户级 SSH 配置

`$HOME/.ssh/`

包含：

|文件|作用|
|---|---|
|id_ed25519|默认私钥|
|id_rsa|旧算法|
|known_hosts|主机指纹|
|config|自定义配置|

---

### 2️⃣ 系统级 SSH 配置（很少改）

`/etc/ssh/`

---

### 3️⃣ Key 发现顺序

1. config 中明确声明
    
2. ssh-agent 中加载的 key
    
3. 默认 key：
    
    - id_ed25519
        
    - id_rsa
        

---

### 4️⃣ HOME 未定义时

Git for Windows 的行为：

`HOME = %USERPROFILE%`

---

### 5️⃣ 如果路径失败

则：

`Host key verification failed`

与你遇到的情形完全一致。

---

# 四、结合你的经历，总结为一条「根因链路」

1️⃣ 早期某次环境异常  
Git Bash 解析 HOME → 乱码目录

↓

2️⃣ `.ssh` 无法创建  
known_hosts 写入失败

↓

3️⃣ SSH 认证失败

↓

4️⃣ 你修改环境变量  
→ 触发 Shell 环境重建

↓

5️⃣ Git Bash 重新正确解析 HOME  
→ `%USERPROFILE%\.ssh` 生效

↓

6️⃣ `.ssh` 被正常创建

↓

7️⃣ 后续 Obsidian 也工作正常

---

# 五、如果你希望彻底掌控 SSH 行为

推荐最佳实践：

### 显式写入 SSH config

文件：

`C:\Users\你的用户名\.ssh\config`

内容：

`Host github.com   HostName github.com   User git   IdentityFile C:/Users/你的用户名/.ssh/id_ed25519   UserKnownHostsFile C:/Users/你的用户名/.ssh/known_hosts`

优点：

✔ 所有程序统一  
✔ 不依赖 HOME 推测  
✔ 避免将来环境变化  
✔ 清晰可控

---

# 六、给你一句本质总结（希望能帮你建立清晰模型）

> **“环境刷新”是 Shell 重新解析环境变量并重新定位 HOME 的过程；  
> 而“SSH 实际使用的路径”可以通过 `ssh -vvv` 精确确认，通常默认绑定 `%USERPROFILE%\.ssh`。**

你经历的问题，本质上是：

> 路径解析异常 → 环境重建恢复正常

而不是：

> 单纯设置 HOME 改变了行为