actions-openwrt-helloworld
LICENSE GitHub Stars GitHub Forks

感谢 P3TERX/Actions-OpenWrt和coolsnowwolf/lede

通过创建流程文件，在线编译helloworld服务固件；

第一代passwall源码完全停止开发(开源源码已经移除)，基于vuejs脚本语言、焕新UI设计的第二代passwall由Lienol等大神们在私有库闭源开发中，看情况和心情，只有极小可能性以后某天开源，不要过分期待。

修改流程文件REPO_URL: 不同库地址（默认lean的https://github.com/coolsnowwolf/lede.git或Lienol的https://github.com/Lienol/openwrt）；REPO_BRANCH: 不同分支 （以Lienol OpenWrt源码为例分支dev-master 激进；dev-19.07 OpenWrt官方平稳版；dev-lean-lede lean的源码）。

通过修改diy-part1.sh文件修改feeds.conf.default配置。默认添加fw876/helloworld。
有能力可以添加包含passwall的lienol-openwrt-package试试。

通过修改diy-part2.sh文件可以自定义默认IP，登陆密码等。按我的需要现在的默认IP为192.168.1.11

在 Actions 页面选择Build OpenWrt，然后点击Run Workflow按钮，即可开始编译。（如果需要 SSH 连接则把SSH connection to Actions的值改为true)

在触发工作流程后，默认SSH_ACTIONS: true在 Actions 页面等待执行到SSH connection to Actions步骤，会出现下面信息：

To connect to this session copy-n-paste the following into a terminal or browser:

ssh Y26QeagDtsPXp2mT6me5cnMRd@nyc1.tmate.io

https://tmate.io/t/Y26QeagDtsPXp2mT6me5cnMRd

复制 SSH 连接命令粘贴到终端内执行，或者复制链接在浏览器中打开使用网页终端，登陆云menuconfig。

命令：cd openwrt && make menuconfig

新手参考OpenWrt MenuConfig设置和LuCI插件选项说明

完成后按快捷键Ctrl+D或执行exit命令退出，后续编译工作将自动进行。

这样比较灵活，可以根据路由器硬件通过云menuconfig自定义配置固件，不需要再导出.config和上传

进阶玩法请看P3TERX的博客中文教程

使用同步.config多流程编译移步Actions-Lean-OpenWrt
