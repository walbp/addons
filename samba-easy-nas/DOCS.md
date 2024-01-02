# 轻量化Samba NAS

> 轻量化的本地网络存储，轻松共享文件。
>

## 配置说明


### 用户名:
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;默认'homeassistant'，可根据个人需求更改。

### 密码:
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;默认'123'，可根据个人需求更改。

### 工作组:
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;默认'WORKGROUP'，根据你建立的工作而填写，默认为“WORKGROUP”，非特殊需求可不做修改。

### 兼容模式：
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;默认关闭，非特殊需求可不做修改。

### 隐藏文件：
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;自定义隐藏文件，非特殊需求可不做修改。

### 允许访问：
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;允许那些IP地址或IP段可以访问本服务。非特殊需求可不做修改。

### 网络适配器：
​      这里填写samba使用的网络适配器，x86一般为enp2s1，其他的end0，最好net info命令查看一下。

### 本地存储器：
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;挂载的本地存储器(填写sda1或sdb1)，查看host主机中挂载的盘位于/dev。 支持文件系统”FAT32、FAT16、EXT3、EXT4“等。

