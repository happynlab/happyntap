# happyntap
a modern tap driver for macos


# 项目背景

在MacOS上运行相当一部分VPN软件，依赖于TunTap驱动；目前的TunTap驱动还是一个非常老的项目: [tuntaposx](http://tuntaposx.sourceforge.net/)；这个项目早已不再维护，而目前它的替代是Tunnelblick在其基础上维护的 [Tunnelblick System Extensions](https://tunnelblick.net/cTunTapConnections.html)； 自从MacOS 10.15 版本之后，其安全审核机制越来越严格，因此这种kexts驱动的载入越来越不方便;

在2020年发布的Apple M1芯片的系统中，这种不方便进一步加剧，必须在开机的时候打开[降低系统安全性选项](https://tunnelblick.net/cKextsInstallation.html#m1-big-sur)，才能正常启用kexts；苹果已在文档中明确表示会逐步废弃这种驱动载入方式；

# 项目愿景

happyntap 希望能开发一款新的驱动来代替 tuntaposx，这个驱动希望能满足如下需求:

1. 能无缝替代tuntaposx，如在其之上的openvpn、n2n等软件能方便的迁移
2. 采用苹果推荐的方式技术方式来构建，并能长久兼容M1和Intel芯片；
3. 尽可能将部署方式做的简单易用


# 技术路线

* zerotier早在几年前就探讨了[采用feth实现Tap驱动的方法](https://www.zerotier.com/2019/08/21/how-zerotier-eliminated-kernel-extensions-on-macos/)，并且好像已经做成了，目前可以参考它们的实现

* 更多资料和想法可以移步我们的[论坛](https://github.com/happynlab/happyntap/discussions/categories/ideas) 来讨论实现；
