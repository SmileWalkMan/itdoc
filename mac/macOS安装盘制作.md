将U盘重命名为Install macOS High Sierra 13602<br>
<br>
双击打开10.13.6macOS.High.Sierra.dmg，将Install macOS High Sierra.app 拖动到Applications<br>
<br>
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/[Name of U 盘]<br>
<br>
例如：<br>
<br>
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/Install\ macOS\ High\ Sierra\ 13602<br>
<br>
<br>
注意：<br>
1.如果是10.12 或10.11 系统，命令行需要添加 --application 参数，也就是Install macOS*.app的位置<br>
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/[Name of U 盘] --application /Applications/Install macOS*.app<br>
<br>
2. 如果安装过程中出现OS X应用程序无法验证，需要修改系统时间到Install macOS*.app 的创建时间，<br>
<br>
将时间设置为2014年6月18日14点16分30秒（MMDDhhmmYYYY.ss）<br>
<br>
>date 0618141614.30<br>
