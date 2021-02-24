# 下载远程代码到本地，需要输入登陆名和密码，其中密码是github-setting->Developer settings->Personal access tokens
>git clone https://github.com/SmileWalkMan/itdoc.git
# 创建新的分支
>git branch testbranch
# 切换到新的分支
>git checkout testbranch
# 将新的分支提交到远程（如果没有会在远程创建）
>git push origin testbranch
echo "aaa" >f1.txt
# git add . 表示当前目录全部添加到暂存库
>git add f1.txt
# 将暂存库的代码提交到本地仓库
>git commit -m "commit的说明" f1.txt
# 将代码提交到远程
>git push origin testbranch
# 删除远程分支(需要先切换到其他分支才能删除)
>git checkout main
>git branch -D testbranch
# 同步远程代码到本地branch
>git pull

创建Pull Request需要在git网页或者git desktop操作

