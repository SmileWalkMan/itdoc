### 安装<br>
从终端使用<br>
# apt-get update<br>
# apt-get install ssh<br>
启用和开始使用 SSH<br>
为了确保安全 shell 能够使用，在重启系统后使用<br>
<br>
### systemctl<br>
命令来启用它：<br>
<br>
# systemctl enable ssh<br>
在当前对话执行中使用 SSH:<br>
<br>
# service ssh start<br>
<br>
### 允许 SSH Root 访问<br>
默认情况下 SSH 不允许以 root 用户登录，因此将会出现下面的错误提示信息：<br>
Permission denied, please try again.<br>
为了通过 SSH 进入你的 Kali Linux 系统，你可以有两个不同的选择。第一个选择是创建一个新的非特权用户然后使用它的身份来登录。第二个选择，你可以以 root 用户访问 SSH 。为了实现这件事，需要在SSH 配置文件 /etc/ssh/sshd_config 中插入下面这些行内容或对其进行编辑：<br>
将<br>
#PermitRootLogin prohibit-password<br>
改为：<br>
<br>
PermitRootLogin yes<br>
<br>
对/etc/ssh/sshd_config 进行更改以后，需在以 root 用户登录 SSH 前重启 SSH 服务：<br>
# service ssh restart<br>
<br>
<br>
