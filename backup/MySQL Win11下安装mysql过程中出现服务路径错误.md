## 前言
重装mysql过程中，在执行    **net start mysql**   启动mysql服务时，出现错误

<img width="556" height="124" alt="Image" src="https://github.com/user-attachments/assets/569bdfca-818a-4a92-9640-0127aba374aa" />

---

## 前提
* 已彻底卸载旧版本mysql
* 安装路径不是默认位置
* 已经配置环境变量

---

## 解决思路
报出找不到文件的错误，首先检查路径问题，结合论坛中其他博客，在mysql服务中发现mysql的执行路径错误。

<img width="472" height="598" alt="Image" src="https://github.com/user-attachments/assets/d45a6a7e-fabf-41dd-99cb-e2607c1b479b" />

明显这个路径并不是我的安装目录，依据其他大佬的博客，导致问题的原因应该是我提早设置了环境变量而没有修改cmd工作目录，导致mysql使用了错误的cmd路径

---

## 解决办法
### 移除错误的MySQL服务并把cmd的工作目录设置到mysqld的文件路径上
执行以下命令
```cmd
mysqld --remove MySQL
cd /d "D:\dev\MySQL\bin"
```

<img width="541" height="52" alt="Image" src="https://github.com/user-attachments/assets/f9f46b3f-1354-42d3-add6-2a97701c9e78" />

<img width="606" height="90" alt="Image" src="https://github.com/user-attachments/assets/b2b3e4b5-012a-41ad-9ea0-4a3bb445a41c" />

### 重新安装并测试能否正常启动服务
```cmd
mysqld --install
net start MySQL
```

<img width="552" height="172" alt="Image" src="https://github.com/user-attachments/assets/5e60d43d-342a-499e-bb0a-53c240d886b7" />

启动成功！
### 到服务中检查服务路径是否正确

<img width="472" height="598" alt="Image" src="https://github.com/user-attachments/assets/ae94ab0f-55df-4853-804e-59fce5a2c44e" />

服务路径正确！
问题解决！


