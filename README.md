# vscode通过ssh远程编辑文件 2018-9-27
## 步骤
   1. 在远程linux机器上安装rmate；
      - 在远程终端键入：wget -O /usr/local/bin/rmate https://raw.github.com/aurora/rmate/master/rmate && chmod a+x /usr/local/bin/rmate 。可能会提醒权限不够，最好在前面加sudo，提高权限。
   2. 在vscode中安装扩展remote vscode。
      - 搜索remote vscode插件， 并安装。
      - ctrl+shift+p 调出命令窗口, 搜索Remote Start Server并点击
   3. 在本地windows上安装openssh；
      - [参考文档](https://blog.csdn.net/qq_25673113/article/details/64131516)
      - [下载openssh for Winodws](http://linux.linuxidc.com/index.php?folder=MjAxNMTq18rBzy8y1MIvMTTI1S9XaW5kb3dzIDfD/MHu0NDPwsq508NTU0jNqLn9w9jUv7XHwrxMaW51eA==)
      - 注意要设置环境变量，编辑Path，在行尾追加 ;{openssh的下载路径}\bin (替代地址)
      - cmd命令行，尝试ssh -V，产生版本信息，说明安装成功
   4. 在本地终端；
      - 键入：ssh -R 52698:localhost:52698 -p22 root@example.com， 连接远程设备。
      - 键入：rmate -p 52698 文件名 。 就会在本机的vscode上打开远程的文件，进行编辑即可。
