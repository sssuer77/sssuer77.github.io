## 前言
今天想重装一下MySQL，担心自己之前乱装可能导致莫名错误，结果重装后服务启动不太正常，发现是上一个版本的MySQL没有卸载干净，遂参考其他博客完成了彻底的卸载，自己也写一个博客记录一下。
参考博客：https://developer.aliyun.com/article/1336936

---

## 步骤
### 1. 停止mysql服务
在**计算机管理\服务和应用程序\服务**中，找到你对应的MySQLxx，停止服务。

<img width="164" height="68" alt="Image" src="https://github.com/user-attachments/assets/f88a583a-3cd4-4581-80b9-13e8ebe29346" />

<img width="844" height="20" alt="Image" src="https://github.com/user-attachments/assets/f115e2ef-ebe5-4bd3-8202-e6dae12f1187" />

### 2. 删除mysql服务
**以管理员身份运行**cmd控制台（一定要以管理员身份运行！！），输入   **sc delete MySQLxx**    ，xx对应自己的MySQL版本，命令行显示删除成功。

<img width="335" height="38" alt="Image" src="https://github.com/user-attachments/assets/fa08088c-bbe4-45ac-8c67-65366011b0a1" />

### 3. 卸载mysql程序
在系统已安装应用中找到安装的MySQL软件，选择卸载。

<img width="676" height="69" alt="Image" src="https://github.com/user-attachments/assets/6077deb2-75e2-4dbf-afab-00c4b5d0e7fe" />

### 4. 清理残余文件
#### 4.1 删除mysql安装目录
一般为   **C:\Program Files\MySQL**   或   **C:\Program Files(x86)\MySQL**   ，建议两个都看一下删干净。

<img width="525" height="59" alt="Image" src="https://github.com/user-attachments/assets/5fc9d673-60c6-4a48-82d4-db0a75aec113" />

#### 4.2 删除mysql数据存放目录
默认在   **C:\ProgramData\MySQL**   ，选择删除，记得勾选“显示隐藏的目录”。

<img width="598" height="24" alt="Image" src="https://github.com/user-attachments/assets/f24c11d8-2816-49c1-aeb7-39cac95f7b18" />

#### 4.3 删除自定义安装目录
如果自定义安装目录就去检查目录下还有没有残余文件，有就删掉。

<img width="598" height="24" alt="Image" src="https://github.com/user-attachments/assets/4a5742e7-9146-4ad9-b38b-41be8ca0ab0d" />

### 5. 清理注册表
命令框中输入regedit打开注册表，在*HKEY_LOCAL_MACHINE\SYSTEM\ControlSet002\Services\Eventlog\Application*目录下找到**MySQLD Service**以及**MYSQL**删除。如果有多个或者不同的ControlSet00x，都检查一遍删掉。

<img width="397" height="198" alt="Image" src="https://github.com/user-attachments/assets/0b19f25a-1fe5-4478-8b1d-e84e89eb27b0" />

<img width="241" height="265" alt="Image" src="https://github.com/user-attachments/assets/04f681cd-6480-404c-8e64-503c0eb4a8b6" />

### 6. 删除环境变量
高级系统设置里删除环境变量。