# 下载远程代码到本地，需要输入登陆名和密码，其中密码是github-setting->Developer settings->Personal access tokens<br>
>git clone https://github.com/SmileWalkMan/itdoc.git<br>
# 创建新的分支<br>
>git branch testbranch<br>
# 切换到新的分支<br>
>git checkout testbranch<br>
# 将新的分支提交到远程（如果没有会在远程创建）<br>
>git push origin testbranch<br>
echo "aaa" >f1.txt<br>
# git add . 表示当前目录全部添加到暂存库<br>
>git add f1.txt<br>
# 将暂存库的代码提交到本地仓库<br>
>git commit -m "commit的说明" f1.txt<br>
# 将代码提交到远程<br>
>git push origin testbranch<br>
# 删除远程分支(需要先切换到其他分支才能删除)<br>
>git checkout main<br>
>git branch -D testbranch<br>
# 同步远程代码到本地branch<br>
>git pull<br>
<br>
创建Pull Request需要在git网页或者git desktop操作<br>
<br>
