# windows命令大全

运行命令即DOS命令，主要是面向DOS操作系统的。DOS命令指DOS操作系统的命令，因DOS实际上是磁盘操作系统，所以DOS命令是一种面向磁盘管理的操作命令，与Windows操作系统最大的区别在于，它以命令行的形式，靠输入命令来进行人机对话，并通过命令的形式把指令传给计算机，以实现对计算机的操作。

虽然随着计算机产业的发展，Windows操作系统的应用越来越广泛，DOS面临着被淘汰的命运，但是因为它运行安全、稳定，有的用户还在使用，所以一般Windows的各种版本都与其兼容，用户可以在Windows系统下运行DOS。命令主要包括目录操作类命令、磁盘操作类命令、文件操作类命令和其它命令。

## 主机管理类指令

1. hostname：显示或临时设置计算机的主机名
2. whoami：显示当前用户的详细信息
3. systeminfo：显示关于计算机及其操作系统的详细配置信息
4. msconfig：系统配置实用程序
5. bcdedit：修改启动配置数据
6. shutdown：关机指令
7. shutdown -s -t 60：表示60秒后自动关机
8. shutdown -a ：可取消定时关机
9. shutdown -r -t 60：表示60秒后自动重启
10. winver：图形化查看Windows系统版本信息
11. ver：命令行显示Windows系统版本信息
12. sfc：扫描Windows系统文件的完整性
13. mmc：图形化控制台
14. mstsc：远程桌面连接
15. sysprep：操作系统准备工具
16. logoff：注销指令
17. reg：注册表管理指令

## 文件系统/环境变量类指令

1. cd/chdir：切换当前工作目录
2. tree：打印该指定目录的文件树状结构图
3. mkdir/md：创建目录
4. fsutil：用于执行多种与FAT和NTFS文件系统相关的任务（例如管理重解析点、管理稀疏文件、卸载卷或扩展卷）的命令行实用程序。
5. rename/ren：修改文件/目录的名称
6. more/type：查看文件的内容
7. attrib：查看文件/目录的常规属性值（如：S、H、R）
8. cacls：查看/修改文件/目录的安全属性值
9. copy/xcopy：复制文件/目录
10. move/replace：剪切文件/目录
11. del/rmdir/rd：删除文件/目录（含空、子目录）
12. find：查看文件/目录的文件名、内容等
13. findstr：查找指定的一个或多个文件中包含（或通过参数/V来控制不包含）某些特定字符串的行，并将该行完整的信息打印出来，或者打印查询字符串所在的文件名。
14. where：通过当前系统的环境变量显示所查找指令的绝对路径
15. explorer：打开Windows图形化界面的资源管理器
16. path/echo %PATH%：显示系统的环境变量路径
17. set/setx：

执行set命令设置，只对当前的session有效，cmd退出，环境变量自动清除。
在Windows 7以后的操作系统版本还可以通过setx命令来设置环境变量，其语法是：

### 用户级环境变量

setx key value

### 系统级环境变量

setx key value -m

## 账户/群组、服务管理相关指令（net user/net local group）

- net localgroup groupname /comment:"comment" /add：创建群组（含群组的备注）
- net localgroup groupname：查看群组信息
- net localgroup groupname /del：删除群组
- net user username userpass /comment:"comment" /add：创建账户（含账户的注释）
- net user username /del：删除账户
- net user username：查看账户信息
- net user username /active:{yes|no}：启用账户或者是禁用账户
- net localgroup groupname username /add：将账户加入至指定的群组

实例举例1：

net user test1 123 /comment:"proadmin" /fullname:"Administratr" /usercomment:"usercomment" /add

- /comment：注释
- /fullname：全名
- /usercomment：用户注释
- sc：添加、删除系统服务
- net {start|stop|pause|...} servicename：管理服务

## 相关磁盘管理类指令

1. diskpart：对硬盘的分区管理，包括创建分区、删除分区、合并（扩展）分区
2. format：文件系统格式化
3. convert：文件系统转换指令（PS：低版本可无损升级高版本文件系统，相反不可）
4. label：分区卷标管理指令
5. defrag：磁盘碎片整理管理指令

## 相关网络类指令

1. nslookup：监测网络中DNS 服务器是否能正确实现域名解析的命令行工具
2. netstat：监测网络状态、网卡、端口、路由及其他有用的网络的信息
3. ipconfig：显示网卡配置信息
4. ping：测试网络互通指令
5. route：管理本机的路由表信息
6. arp：管理本机的ARP表信息
7. netsh：网络配置shell外壳的命令行实用指令

## 相关任务管理类指令

1. tasklist：显示运行在本地或远程计算机上的所有进程的指令
2. taskkill：结束进程指令
3. schtasks：Windows 7以后的计划管理任务
4. at：Windows 7以前的计划管理任务（Windows 7以后兼容但不建议使用）
5. netstat -o：查看网络、端口、进程之间的PID

## 常用有用的图形化工具类指令

1. calc：计算器
2. devmgmt.msc：设备管理器
3. lusrmgr.msc：本地用户和组
4. diskmgmt.msc：磁盘管理
5. compmgmt.msc/compmgmtlauncher：计算机管理
6. fsmgmt.msc：共享文件夹管理器
7. gpedit.msc：组策略
8. secpol.msc：本地安全策略
9. certmgr.msc：证书管理实用程序
10. services.msc：本地服务设置
11. eventvwr：事件查看器
12. perfmon.msc：计算机性能监测器
13. printmanagement.msc：打印管理
14. taskmgr：任务管理器
15. cleanmgr：打开磁盘清理工具
16. mspaint：画图
17. notepad：打开记事本
18. write：写字板
19. shrpubw：创建共享文件夹
20. regedit/regedt32：注册表编辑器
21. appwiz.cpl：程序和功能
22. firewall.cpl：Windows防火墙
23. hdwwiz.cpl：设备管理器
24. desk.cpl：屏幕分辨率
25. ncpa.cpl：网络连接
26. sysdm.cpl：系统属性
27. taskschd.msc：任务计划程序
28. timedate.cpl：日期和时间
29. useraccountcontrolsettings：用户账户控制设置
30. dfrg.msc：磁盘碎片整理程序
31. snippingtool：截图工具，支持无规则截图
32. ain.cpl：鼠标属性
33. mmsys.cpl：声音
34. wf.msc：高级安全Windows防火墙
35. rsop.msc：组策略结果集
36. chkdsk：磁盘检查（管理员身份运行命令提示符）
37. cleanmgr：垃圾整理
38. powercfg.cpl：电源选项
39. inetcpl.cpl：Internet属性
40. intl.cpl：区域
41. control：控制面版
42. dcomcnfg：打开系统组件服务
43. joy.cpl：游戏控制器
44. dfrgui/dfrg.msc：磁盘碎片整理程序
45. lpksetup：语言包安装/删除向导，安装向导会提示下载语言包
46. OptionalFeatures：打开“打开或关闭Windows功能”对话框
47. osk：打开屏幕键
48. eudcedit：造字程序
49. wscui.cpl：操作中心
50. dxdiag：检查DirectX信息
51. slui：Windows激活，查看系统激活信息
52. slmgr.vbs -dlv：显示详细的许可证信息
53. slmgr.vbs -dli：显示许可证信息
54. slmgr.vbs -xpr：当前许可证截止日期
55. slmgr.vbs -dti：显示安装ID 以进行脱机激
56. slmgr.vbs -ipk：(Product Key)安装产品密钥
57. slmgr.vbs -ato：激活Windows
58. slmgr.vbs -cpky：从注册表中清除产品密钥（防止泄露引起的攻击）
59. slmgr.vbs -ilc：(License fle)安装许可证
60. slmgr.vbs -upk：卸载产品钥
61. slmgr.vbs -skms：(name[ort] )批量授权
62. Netplwiz：高级用户帐户控制面板，设置登陆安全相关的选项
63. credwiz：备份或还原储存的用户名和密码
64. msra：Windows远程协助
65. wiaacmgr：扫描仪和照相机向导
66. odbcad32：ODBC数据源管理器
67. psr：问题步骤记录器
68. mobsync：同步命令
69. charmap：启动字符映射表
70. narrator：屏幕“讲述人”
71. recdisc：创建系统修复光盘
72. rasphone：网络连接
73. resmon：资源监视器
74. rstrui：系统还原
75. sigverif：文件签名验证程序
76. sdclt：备份状态与配置，就是查看系统是否已备份
77. utilman：辅助工具管理器
78. wscript：Windows脚本宿主设置
79. powershell：提供强大远程处理能力
80. cliconfg：SQL SERVER客户端网络实用程序
81. magnify：放大镜实用程序
82. regsvr32：扩展名为DLL、OCX、CPL的文件的注册和反注册工具

>未完待续…………
