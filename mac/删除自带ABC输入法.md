# 首先需要关闭 mac 系统的 SIP ，不然删不掉，不会关的可以查看我的另一篇文章：mac 关闭系统完整性保护 SIP（System Integrity Protection）的方法 。

# 关闭 SIP 重启完成后，先将输入法切换为系统自带的 ABC 输入法，然后打开终端输入以下命令。

>sudo open ~/Library/Preferences/com.apple.HIToolbox.plist
# 接着输入密码即可打开 com.apple.HIToolbox.plist 文件。（打开 .plist 文件需要安装有 Xcode 或者 PlistEdit Pro 也行）

# 依次点开 Root - AppleEnabledInputSources ，会看到一列 item ，找到其中 KeyboardLayout Name 为 ABC 的那一列，将整列 item 删掉，然后 command + S 保存。

# 可以添加英语-美国来替代ABC,通过 capslock切换中英文
