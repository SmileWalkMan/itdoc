1.安装：
>apt-get install gvm
2.配合
>gvm-setup
>gvm-check-setup
3.更新admin的密码
runuser -u _gvm -- gvmb --user=admin --new-password=admin
4.启动服务
gvm-start
5.访问(admin/admin登陆)
https://localhost:9392
