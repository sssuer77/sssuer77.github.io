## 1. VMware 的安装(建议安装稳定版本)

首先检查虚拟化技术是否启用

<img width="958" height="677" alt="Image" src="https://github.com/user-attachments/assets/207cfdef-4cb5-46b2-9fa2-37d3a8662069" />

官网下载链接
https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion

vmware workstation 16 pro密匙2026最新
```
ZF3R0-FHED2-M80TY-8QYGC-NPKYF
```
```
YF390-0HF8P-M81RQ-2DXQE-M2UT6
```
```
ZF71R-DMX85-08DQY-8YMNC-PPHV8
```

vmware workstation 17 pro密匙2026最新
```
4A4RR-813DK-M81A9-4U35H-06KND
```
```
NZ4RR-FTK5H-H81C1-Q30QH-1V2LA
```
```
JU090-6039P-08409-8J0QH-2YR7F
```
```
4Y09U-AJK97-089Z0-A3054-83KLA
```
```
4C21U-2KK9Q-M8130-4V2QH-CF810   
```
```
MC60H-DWHD5-H80U9-6V85M-8280D
```

安装激活完成

<img width="1440" height="741" alt="Image" src="https://github.com/user-attachments/assets/626a7c55-1633-4b76-8b7d-ea46d2f5eae2" />

## 2. 创建新虚拟机
### 自定义安装

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/75e1faeb-3d73-490b-b6bf-65f9c5a4ca38" />

### 默认

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/5186153c-deaa-448a-bcf7-7f61d1fa8337" />

### 稍后安装操作系统

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/719160c4-eaeb-4cff-bbfa-2de25215ecd3" />

### Linux -> CentOS_7

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/82afaa69-cef8-4bae-bd7c-928a8f8cac42" />

### 名称和安装位置

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/8f5238c8-845b-42e2-83c2-3b3f176ede32" />

### 内核数量配置

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/8bef0378-5223-4ea3-8b33-81587f20c908" />

### 内存给到 2GB

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/b25d2b5b-5676-478f-acfe-f3837daa098b" />

### 网络设置建议使用 NAT 方式

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/c31eac83-df87-406d-8141-0f23c6f9dfb5" />

### IO 控制器使用推荐设置即可

<img width="499" height="433" alt="Image" src="https://github.com/user-attachments/assets/33526ef6-4859-4962-9b5f-b78b7f3d0c46" />

### 磁盘类型默认推荐即可

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/a2581ffd-1f54-4ef2-934e-5e295ea97f3e" />

### 创建新的虚拟磁盘

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/9f72f187-ef4e-4005-ad9e-50915ab13ce4" />

### 磁盘容量最大给到 50GB ,拆分成多个文件

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/cd96af13-4df7-453e-bdaf-12e23e69fda8" />

### 检查磁盘文件名,默认即可

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/60620d1f-7bf9-4add-9d0d-0748ca3a7da3" />

### 检查设置信息,然后点击完成

<img width="497" height="401" alt="Image" src="https://github.com/user-attachments/assets/7b9da01c-95e1-4a0d-8335-9b8dd356e6ae" />

### 安装完成

<img width="1440" height="741" alt="Image" src="https://github.com/user-attachments/assets/5209a483-c95a-4287-9aab-d0020dd96532" />

## 3. 安装 Linux
### 镜像文件下载
CentOS_7下载链接,熟练使用可直接下载极简版
https://mirrors.tuna.tsinghua.edu.cn/centos-vault/7.5.1804/isos/x86_64/
记得下载到一个比较稳妥的目录下
### 虚拟机配置
点进设置
<img width="355" height="463" alt="Image" src="https://github.com/user-attachments/assets/8fdb9cd2-682e-4e93-b450-90a6904429dc" />

使用 ISO 镜像文件
<img width="731" height="798" alt="Image" src="https://github.com/user-attachments/assets/6020daf4-b2da-4161-b193-02ccaba3cae8" />

<img width="946" height="533" alt="Image" src="https://github.com/user-attachments/assets/02fc4164-8e28-4fd1-a5d2-b633386f85e7" />

### 开启虚拟机设置
此处本人在操作时,在主机上重新安装VMware Workstation 17 PRO 时,遇到了兼容性问题,只要点击虚拟机开机,宿主机就会关机/重启/卡死,查看Windows日志,发现硬件错误(甚至发现了腾讯ACE反作弊的残留服务项报错),试遍网上的各种方法都没有效果,想到之前使用15版本正常,于是降级到16版本,成功运行

<img width="792" height="649" alt="Image" src="https://github.com/user-attachments/assets/1b8f100d-d880-4c88-b17e-6b6ffb1b8d52" />

<img width="800" height="600" alt="Image" src="https://github.com/user-attachments/assets/589ea0b4-d3ae-4f3b-a135-a6ebb4fdb6e4" />

<img width="800" height="600" alt="Image" src="https://github.com/user-attachments/assets/d00a5567-1c95-45f3-a8d8-1015c8e13699" />

<img width="997" height="733" alt="Image" src="https://github.com/user-attachments/assets/9cc13416-0b9a-4f7f-a568-3227846a9109" />

<img width="800" height="600" alt="Image" src="https://github.com/user-attachments/assets/f48584b0-e9b5-4df8-80ba-af8eb81d232a" />

### 配置镜像源
重启后输入用户密码登录
尝试
``` code
ping www.baidu.com
```

成功后备份并下载阿里源
``` code
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```
```
curl -o /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo
```
修改文件里的失效地址
因为阿里源的文件里可能还保留了一些指向官方旧域名的引用，我们需要执行下面这一行“大杀器”命令，把里面所有的 mirror.centos.org 强行替换成阿里的地址：
``` code
sed -i 's/mirror.centos.org/mirrors.aliyun.com/g' /etc/yum.repos.d/CentOS-Base.repo
```
清理并安装工具
``` code
yum clean all
```
```
yum makecache
```
```
yum install -y vim net-tools wget curl bash-completion 
```





