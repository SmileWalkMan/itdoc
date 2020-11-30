将U盘重命名为Install macOS High Sierra 13602

双击打开10.13.6macOS.High.Sierra.dmg，将Install macOS High Sierra.app 拖动到Applications

sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/[Name of U 盘]

例如：

sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/Install\ macOS\ High\ Sierra\ 13602


注意：
1.如果是10.12 或10.11 系统，命令行需要添加 --application 参数，也就是Install macOS*.app的位置
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/[Name of U 盘] --application /Applications/Install macOS*.app

2. 如果安装过程中出现OS X应用程序无法验证，需要修改系统时间到Install macOS*.app 的创建时间，

将时间设置为2014年6月18日14点16分30秒（MMDDhhmmYYYY.ss）

>date 0618141614.30
