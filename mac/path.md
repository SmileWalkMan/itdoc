Mac系统的环境变量，加载顺序为：<br>
<br>
/etc/profile<br>
/etc/paths<br>
~/.bash_profile<br>
~/.bash_login<br>
~/.profile<br>
~/.bashrc<br>
/etc/profile和/etc/paths是系统级别的，系统启动就会加载，后面几个是当前用户级的环境变量。<br>
后面3个按照从前往后的顺序读取，如果/.bash_profile文件存在，则后面的几个文件就会被忽略不读了，如果/.bash_profile文件不存在，才会以此类推读取后面的文件。<br>
~/.bashrc没有上述规则，它是bash shell打开的时候载入的。<br>
<br>
在PATH中永久添加路径：<br>
修改/etc/paths文件，直接把路径插入在文件末尾，保存，重启s<br>
