# MAC查找JDK的路径
>/usr/libexec/java_home -V
Matching Java Virtual Machines (3):
    1.8.251.08 (x86_64) "Oracle Corporation" - "Java" /Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home
    1.8.0_251 (x86_64) "Oracle Corporation" - "Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_251.jdk/Contents/Home
    1.7.0_80 (x86_64) "Oracle Corporation" - "Java SE 7" /Library/Java/JavaVirtualMachines/jdk1.7.0_80.jdk/Contents/Home
/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home

# 设置JAVA_HOME
记得切换成root用户(sudo -i)或者给指令添加sudo

临时有效（重启后失效）
编辑.bash_profile文件：vim ~/.bash_profile
添加以下内容：
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_162.jdk/Contents/Home
export PATH=$JAVA_HOME/bin:$PATH
使修改的文件生效：source ~/.bash_profile

永久有效
修改文件操作权限：chmod 773 /etc/profile
编辑/ect/profile文件：vim /etc/profile
添加以下内容：
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_162.jdk/Contents/Home
export PATH=$JAVA_HOME/bin:$PATH
使修改的文件生效：source /etc/profile
