1.maven的地址<br>
mvn --version<br>
查看里边的地址就是maven的地址<br>
2.maven 默认本地仓库<br>
~/.m2/repository<br>
3.maven settings.xml 配置<br>
全局配置: ${MAVEN_HOME}/conf/settings.xml<br>
用户配置: 𝑢𝑠𝑒𝑟.ℎ𝑜𝑚𝑒/.𝑚2/𝑠𝑒𝑡𝑡𝑖𝑛𝑔𝑠.𝑥𝑚𝑙𝑛𝑜𝑡𝑒：用户配置优先于全局配置。{user.home} 和和所有其他系统属性只能在3.0+版本上使用。请注意windows和Linux使用变量的区别。<br>
4. settings.xml: 配置下载jar包镜像<br>
<!-- 阿里云的镜像站（首推，新站，速度暴快）。--><br>
<mirror><br>
<id>nexus-aliyun</id><br>
<name>Nexus aliyun</name><br>
<url>http://maven.aliyun.com/nexus/content/groups/public/</url><br>
</mirror><br>
5.配置jdk版本<br>
方法一：在maven文件夹下的settings.xml中添加<br>
<profile><br>
<id>jdk-1.8</id><br>
<activation><br>
<activeByDefault>true</activeByDefault><br>
<jdk>1.8</jdk><br>
</activation><br>
<properties><br>
<maven.compiler.source>1.8</maven.compiler.source><br>
<maven.compiler.target>1.8</maven.compiler.target><br>
<maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion><br>
</properties><br>
</profile><br>
方法二：在maven项目的pom.xml中添加<br>
<plugin><br>
<groupId>org.apache.maven.plugins</groupId><br>
<artifactId>maven-compiler-plugin</artifactId><br>
<version>2.3.2</version><br>
<configuration><br>
<source>1.8</source><br>
<target>1.8</target><br>
<encoding>utf-8</encoding><br>
</configuration><br>
</plugin><br>
