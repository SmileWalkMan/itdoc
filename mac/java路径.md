# MAC查找JDK的路径<br>
>/usr/libexec/java_home -V<br>
Matching Java Virtual Machines (3):<br>
1.8.251.08 (x86_64) "Oracle Corporation" - "Java" /Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home<br>
1.8.0_251 (x86_64) "Oracle Corporation" - "Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_251.jdk/Contents/Home<br>
1.7.0_80 (x86_64) "Oracle Corporation" - "Java SE 7" /Library/Java/JavaVirtualMachines/jdk1.7.0_80.jdk/Contents/Home<br>
/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home<br>
<br>
# 设置JAVA_HOME<br>
记得切换成root用户(sudo -i)或者给指令添加sudo<br>
<br>
临时有效（重启后失效）<br>
编辑.bash_profile文件：vim ~/.bash_profile<br>
添加以下内容：<br>
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_162.jdk/Contents/Home<br>
export PATH=$JAVA_HOME/bin:$PATH<br>
使修改的文件生效：source ~/.bash_profile<br>
<br>
永久有效<br>
修改文件操作权限：chmod 773 /etc/profile<br>
编辑/ect/profile文件：vim /etc/profile<br>
添加以下内容：<br>
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_162.jdk/Contents/Home<br>
export PATH=$JAVA_HOME/bin:$PATH<br>
使修改的文件生效：source /etc/profile<br>
