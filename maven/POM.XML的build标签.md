1.maven的地址
mvn --version
查看里边的地址就是maven的地址
2.maven 默认本地仓库
~/.m2/repository
3.maven settings.xml 配置
全局配置: ${MAVEN_HOME}/conf/settings.xml
用户配置: 𝑢𝑠𝑒𝑟.ℎ𝑜𝑚𝑒/.𝑚2/𝑠𝑒𝑡𝑡𝑖𝑛𝑔𝑠.𝑥𝑚𝑙𝑛𝑜𝑡𝑒：用户配置优先于全局配置。{user.home} 和和所有其他系统属性只能在3.0+版本上使用。请注意windows和Linux使用变量的区别。
4. settings.xml: 配置下载jar包镜像
	 <!-- 阿里云的镜像站（首推，新站，速度暴快）。-->
	 <mirror>
		<id>nexus-aliyun</id>
		<name>Nexus aliyun</name>
		<url>http://maven.aliyun.com/nexus/content/groups/public/</url> 
	 </mirror>
5.配置jdk版本
方法一：在maven文件夹下的settings.xml中添加
<profile>
    <id>jdk-1.8</id>
    <activation>
        <activeByDefault>true</activeByDefault>
        <jdk>1.8</jdk>
    </activation>
    <properties>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
        <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>
    </properties>
</profile>
方法二：在maven项目的pom.xml中添加
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <version>2.3.2</version>
    <configuration>
        <source>1.8</source>
        <target>1.8</target>
        <encoding>utf-8</encoding>
    </configuration>
</plugin>