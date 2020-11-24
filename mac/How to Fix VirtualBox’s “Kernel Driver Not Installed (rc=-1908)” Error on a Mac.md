If you’re receiving this error, you’ve likely already tried to install VirtualBox on the latest version of macOS. During the course of installation or during the setup of your first VM, you’ll possibly come across this error message。
Whether you’re trying to set up a Windows, Linux, or Mac VM, the error is appearing because this is your Mac’s first time installing any Oracle products (like VirtualBox). You’ll need to give the piece of software explicit permission to access the computer. Unfortunately, you have to go look for the prompt.
![image](https://user-images.githubusercontent.com/43125286/100072320-0f714700-2e77-11eb-83e9-28a7833e7579.png)

First, navigate to System Preferences by clicking the Apple icon on the top menu bar and then selecting the “System Preferences” button. From there, click the “Security and Privacy” option.
Under the “General” tab, there should be text near the bottom that says, “System Software from Developer ‘Oracle America, Inc.’ Was Blocked from Loading.” Click the “Allow” button
![image](https://user-images.githubusercontent.com/43125286/100072438-36c81400-2e77-11eb-8fce-fb7337247992.png)

### Note: This option is available only for roughly 30 minutes after a fresh install of VirtualBox. If this message does not appear, uninstall VirtualBox by opening your “Applications” folder and then dragging the VirtualBox app to the Trash. Remove any leftover files, reinstall a fresh copy of VirtualBox, and immediately open the Security & Privacy menu to see this option.

The installation will now complete successfully. Congratulations on your fresh and functional installation of VirtualBox!
