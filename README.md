# 神舟战神T6-X5 黑苹果EFI
***
## 版本：mac os catalina 10.15.6
## 其他版本请自行测试，10.14的也可以使用，但是bigsur未测试
感谢 csdn [丶乳酸君](https://blog.csdn.net/weixin_43811041)的efi，csdn原帖：https://blog.csdn.net/weixin_43811041/article/details/105933304#comments_12826154
在其基础上添加
* AirportItlwm.kext（wifi驱动）
* SSDT-PNLF.aml （亮度补丁，解决最低亮度太亮的问题）

已经作为工作机使用两周，除了下面列出的其他都正常：
* 蓝牙一直打开状态，无法关闭，可以搜索，没有连接过，待测试
* 点睡眠后立刻唤醒正常，但长时间（半小时以上）就会黑屏无法唤醒，目前就只能一直不盖上盖子
* 如果开机后wifi并未正常工作，请安装clover configuration软件，挂载efi分区，将wifi驱动复制到桌面后执行下面的命令手动加载，亲测可用：
```cd ～/Desktop
sudo chown -R root:wheel AirportItlwm.kext/
sudo chmod -R 755 AirportItlwm.kext 
sudo kextload -v AirportItlwm.kext 
提示 Requesting load of /Users/jin/Desktop/AirportItlwm.kext.
/Users/jin/Desktop/AirportItlwm.kext loaded successfully (or already loaded).即加载成功
```
* 如果开机后跑完代码黑屏，但是按按键有声音（已经进入系统），可能是亮度在最低状态，按ctrl+F1组合键即可亮屏，开机后调整亮度

最后，希望大家折腾愉快
对动不动声称完美黑苹果，百分之99完美黑苹果的表示强烈谴责！！！
