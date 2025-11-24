## 前言
重装mysql服务时，启用mysql服务失败，怀疑是mysql默认端口3306被占用，遂检查端口占用情况，写一篇博客记录一下。

---

## 步骤
### 1. **以管理员身份**运行cmd命令行。

<img width="979" height="512" alt="Image" src="https://github.com/user-attachments/assets/12342932-2953-4996-94b4-56d5f952d1db" />

### 2. 查看所有运行端口
在命令行输入命令
```cmd
netstat -ano
```

<img width="979" height="512" alt="Image" src="https://github.com/user-attachments/assets/607afc99-57a5-4cec-8cb2-4f56b004199f" />

### 3. 检查端口占用情况
命令行命令
```cmd
netstat -aon|findstr "3306"
```
#### 3.1 端口被占用
命令行返回占用端口进程的PID等信息

<img width="829" height="81" alt="Image" src="https://github.com/user-attachments/assets/cf2b8c92-c9e3-4742-96b8-e15f43f23b49" />

#### 3.2 端口未被占用
命令行不返回命令

<img width="553" height="73" alt="Image" src="https://github.com/user-attachments/assets/7392cd27-32c3-4d31-8d40-affc76b97e35" />

### 4. 查看指定PID的进程
继续输入命令
```cmd
tasklist|findstr "5696"
```

<img width="961" height="71" alt="Image" src="https://github.com/user-attachments/assets/f09ebf0b-443a-47e3-a48b-661cb6e8b24d" />

### 结束进程
```cmd
taskkill /T /F /PID 5696
```
这样就能释放端口来使用了。


