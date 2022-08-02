

## 兄弟连Linux常用命令

### 1.1命令格式

#### 	Linux命令格式

​		命令  [-选项] [参数]

​		`ctrl`+`l`清屏

### 1.2目录处理命令

#### ls----显示目录文件

```powershell
	命令名称：ls

​	命令英文原意：list

​	命令所在路径：/bin/ls

​	执行权限：所有用户

​	功能：显示目录文件
```

​	语法：ls [选项] [文件或目录]

​				-a 显示所有文件，包括隐藏文件

​				-l 详细信息显示（+h为人性化显示）

```powershell
ls -l
-------------所有者---所属组---文件大小（默认字节）--------最后一次修改时间 -----文件名
drwxr-xr-x 2 yangyubo yangyubo 4096 10月 23 01:24 公共
drwxr-xr-x 2 yangyubo yangyubo 4096 10月 23 01:24 模板
drwxr-xr-x 2 yangyubo yangyubo 4096 10月 23 01:24 视频
drwxr-xr-x 2 yangyubo yangyubo 4096 10月 23 01:24 图片
drwxr-xr-x 2 yangyubo yangyubo 4096 10月 23 01:24 文档
drwxr-xr-x 2 yangyubo yangyubo 4096 10月 23 01:24 下载
drwxr-xr-x 2 yangyubo yangyubo 4096 10月 23 01:24 音乐
drwxr-xr-x 2 yangyubo yangyubo 4096 10月 30 16:13 桌面

```

```powershell
ls -lh
-------------------------------------------
drwxr-xr-x 2 yangyubo yangyubo 4.0K 10月 23 01:24 公共
drwxr-xr-x 2 yangyubo yangyubo 4.0K 10月 23 01:24 模板
drwxr-xr-x 2 yangyubo yangyubo 4.0K 10月 23 01:24 视频
drwxr-xr-x 2 yangyubo yangyubo 4.0K 10月 23 01:24 图片
drwxr-xr-x 2 yangyubo yangyubo 4.0K 10月 23 01:24 文档
drwxr-xr-x 2 yangyubo yangyubo 4.0K 10月 23 01:24 下载
drwxr-xr-x 2 yangyubo yangyubo 4.0K 10月 23 01:24 音乐
drwxr-xr-x 2 yangyubo yangyubo 4.0K 10月 30 16:13 桌面

-rw-r--r--
    -：代表文件
	d：代表目录
	l：软链接
 rw-     		r--           r--
 u所有者		 g所属组		o其他人
 r读			   w写		   x执行者 
```

​				组里每个成员都享有这个组的权限

​				-d 查看目录属性  显示目录本身，而不显示目录下的数据

```powershell
└─$ ls -ld /etc 
---------------------
drwxr-xr-x 174 root root 12288 11月  9 19:15 /etc

```



​			-i	显示文件的索引

#### mkdir----创建新目录

```powershell
	命令名称：mkdir

​	命令英文原意：make directories

​	命令所在路径：/bin/mkdir

​	执行权限：所有用户

​	语法：mkdir -p[目录名]

​	功能描述：创建新目录

​	-p 递归创建
```

​	范例：

```powershell
# mkdir /qe
# mkdir -p /qe/qwe/yang

```

#### cd----切换目录

```powershell
命令名称：cd

​	命令英文原意：change directory

​	命令所在路径：shell内置命令

​	执行权限：所有用户

​	语法：cd /目录

​	功能描述：切换目录

​	cd ..上级目录          .代表当前目录    ..代表上级目录
```



#### pwd----显示当前目录

```powershell
	命令名称：pwd

​	命令英文原意：print working directory

​	命令所在路径：/bin/pwd

​	执行权限：所有用户

​	语法：pwd

​	功能描述：显示当前目录
```

#### rmdir----删除空目录

```powershell
	命令名称：rmdir

​	命令英文原意：remove empty directories

​	命令所在路径：/bin/rmdir

​	执行权限：所有用户

​	语法：rmdir[目录名]

​	功能描述：删除空目录
范例：rmdir /qe/yang #删除yang


```

#### cp----复制文件或目录

```powershell
命令名称：cp

命令英文原意：copy

命令所在路径：/bin/cp

执行权限：所有用户

语法：cp -rp[原文件或目录][目标目录]
		-r 复制目录    #可支持同时复制多个文件
		-p 保留文件属性  #时间等属性不变
功能描述：复制文件或目录
范例 ： cp -r /qe/qwe/yang /qe # ----复制目录yang到qe目录下
	   cp -r / qe/qwe/yang /qe/yu # ----复制目录yang到qe目录下,并改名为yu
	   cp -r /qe/qwe/yang /qe/qwe/yu /qe/qwe/bo /king  #----吧qwe下的yang、yu、bo复制到king目录下
	
		
	
```

#### mv----剪切文件、改名

```powershell
	命令名称：mv

​	命令英文原意：move

​	命令所在路径：/bin/mv

​	执行权限：所有用户

​	语法：mv[原文件或目录][目标目录]
	改名：mv 文件名 新文件名

​	功能描述：剪切文件、改名
```

#### rm----删除文件

```powershell
	命令名称：rm

​	命令英文原意：remove

​	命令所在路径：/bin/rm

​	执行权限：所有用户

​	语法：rm  [文件或目录] 
			-r删除目录
			-f 强制执行
			-rf 强制删除目录

​	功能描述：删除文件
```

### 1.3文件处理命令 

#### 	touch----创建空文件/刷新文件时间标记

```powershell
	命令名称：touch

​	命令所在路径：/bin/thoch

​	执行权限：所有用户

​	语法：touch [文件名]

​	功能描述：创建空文件

	范例：touch Japanlovestory.list
```

#### 	cat---- 显示文件内容

```powershell
	命令名称：cat

​	命令所在路径：/bin/cat

​	执行权限：所有用户

​	语法：cat [文件名]

​	功能描述：显示文件内容
			-n显示行号
	范例：cat /etc/issue
		 cat -n /etc/services
```

#### 	tac----显示文件内容（反向列示）

```powershell
	命令名称：tac

​	命令所在路径：/usr/bin/tac

​	执行权限：所有用户

​	语法：tac [文件名]

​	功能描述：显示文件内容(反向列示)
			
	范例：tac /etc/issue
		 
```

#### more----分页显示文件内容

```powershell
	命令名称：more

​	命令所在路径：/bin/more

​	执行权限：所有用户

​	语法：more [文件名]
			(空格)或f     翻页
			(Enter)		 换行
			q或Q 		退出
			上下方向键也可切换

​	功能描述：分页显示文件内容
	范例：more /etc/services
		结束自动跳出
+num 从第 num 行开始显示
```

```
显示百分比
more -s :空行的话会统一变为一行
/可以搜索，但是没有对应的回执
```



#### less----分页显示文件内容(可上下翻页，推荐使用)

```powershell
	命令名称：less

​	命令所在路径：/bin/less

​	执行权限：所有用户

​	语法：less [文件名]
	可以加 / 搜索  
	n为下一条

​	功能描述：分页显示文件内容
	范例：less /etc/services
	看完以后不会退出，支持关键词搜索 /查找内容（）
```

#### head----显示文件前面几行

```powershell
	命令名称：head /tail(文件后)

​	命令所在路径：/usr/bin/head
yin
​	执行权限：所有用户

​	语法：head [文件名]

​	功能描述：显示文件前面几行
	范例：head -n 20 /etc/services
	   	head -5 /etc/passwd
```

### 1.4链接命令

#### ln----生成链接文件

```powershell
	命令名称：ln

​	命令所在路径：/bin/ln

​	执行权限：所有用户

​	语法：ln [原文件][目标文件]
		 -s 创建软链接
​	功能描述：生成链接文件
	范例：ln -s /etc/issue /tmp/issue.soft
		 #创建文件/etc/issue的软连接/tmp/issue.soft
		 ln /etc/issue /tmp/issue.hard
		 #创建文件/etc/issue的硬链接/tmp/issue.hard
```

##### 软链接的特点

```powershell
特征：类似Windows的快捷方式
	1.lrwxrwxrwx    
	2.文件较小
	3.有箭头指向源文件
```

##### 硬链接的特点

```powershell
1.拷贝cp -p + 同步更新
2.通过i节点识别
	一个i节点不一定对应一个软件
	硬链接的i节点和原文件一样，所以可以同步更新
3.不能跨分区
4.不能针对目录使用
5.原文件被删除，新文件依旧存在
```

### 2.1权限管理命令chmod

#### 	权限数字表示

```
r------4
w------2
x------1

rwx   rw-    r---
7	  6  	4
```

#### 	chmod----改变文件或目录权限

```python
	命令名称：chmod
	
​	命令英文原意：change the permissions mode of a file

​	命令所在路径：/bin/chmod
​	执行权限：所有用户

​	语法：chmod [{ugoa}{+-=}{rwx}][文件或目录]
		[mode=421][文件或目录]
		-R 递归修改  #目录下的所有文件都同时修改
​	功能描述：改变文件或目录权限
	范例：chmod u+x /king/love.txt #给love的所有者（u）增加修改（x）的权限
    	 chmod u+x o- /king/love.txt #给love的所有者（u）增加修改（x）的权限并同时给普通用户（o）减少读（r） 
        chmod o=rwx /king/love.txt    #给love的普通用户权限设置为rwx
        chmod -R 777 /king   #给king目录下的所有文件权限设置为rwx

```

#### 权限类别

```
file    r：cat/more/head/tail/less
	    w：vim
	    x：script   command
directory		r: ls
			    w:touch/mkdir/rmdir/rm
			    x:cd
```

​	删除一个文件不是对此文件有删除权限，而是对此文件所在的目录有写权限才可以

| 代表字符 | 权限     | 对文件的含义     | 对目录的含义               |
| :------: | -------- | ---------------- | -------------------------- |
|    r     | 读权限   | 可以查看文件内容 | 可以列出目录中的内容       |
|    w     | 写权限   | 可以修改文件内容 | 可以在目录中创建、删除文件 |
|    x     | 执行权限 | 可以执行文件     | 可以进入目录               |

​                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   

### 2.2其他权限管理命令

#### 	权限管理命令----chown----改变文件或目录的所有者

```python
命令名称：chown
	
​	命令英文原意：change file ownership

​	命令所在路径：/bin/chown
​	执行权限：所有用户

​	语法：chown [用户][文件或目录]
​	功能描述：改变文件或目录的所有者
	范例：chown yangyubo /king   #改变king的所有者，改为yangyubo
```

#### 	chgrp----改变文件或目录的所属组

```python
命令名称：chgrp
	
​	命令英文原意：change file group ownership

​	命令所在路径：/bin/chgrp
​	执行权限：所有用户

​	语法：chgrp [用户组][文件或目录]
​	功能描述：改变文件或目录的所属组
	范例：chgrp yangyubo /king   #改变king的所属组，改为yangyubo
```

```python
groupadd   #添加所属组
```

#### umask----显示、设置文件的缺省权限

```python
命令名称：umask
	
​	命令英文原意：the user file-creation mask

​	命令所在路径：Shell内置命令
​	执行权限：所有用户
​	语法：umask[-S]
		-S  以rwx形式显示新建文件缺省权限
​	功能描述：显示、设置文件的缺省权限
	范例：umask — S
	------------------------
	  mkdir创建的目录默认：u=rwx,g=rx,o=rx
	  touch创建的文件默认：u=rw-，g=r--，o=r--   #统一取消x权限，因为是文件不具有可执行权限

```

```python
umask
---------------
0022
0 ： 特殊权限
022：---，-w-，-w-
---------------------
	rwx，r-x，r-x
默认权限做逻辑异或运算
```

### 3.1文件搜索命令

#### 	find----文件搜索

```python
命令名称：find
​	命令所在路径：/bin/find
​	执行权限：所有用户
​	语法：find [搜索范围][匹配条件]
​	功能描述：文件搜索
	范例：umask — S
	------------------------
	  mkdir创建的目录默认：u=rwx,g=rx,o=rx
	  touch创建的文件默认：u=rw-，g=r--，o=r--   #统一取消x权限，因为是文件不具有可执行权限
```

##### find /etc -name init  ------------在目录/etc中查找文件init

```python
 find /etc -name init		#类似精确查找
 find /etc -iname init		#-iname不区分大小写
------------------------------------
/etc/apparmor/init

```

 	使用通配符

```python
└─# find /etc -name *init*
-------------------------------------
/etc/darkstat/init.cfg
/etc/systemd/system/sysinit.target.wants
/etc/kernel/postrm.d/initramfs-tools
/etc/kernel/postinst.d/initramfs-tools
/etc/initramfs-tools
/etc/initramfs-tools/initramfs.conf
/etc/initramfs-tools/update-initramfs.conf
/etc/initramfs-tools/scripts/init-premount
/etc/initramfs-tools/scripts/init-bottom
/etc/initramfs-tools/scripts/init-top
/etc/gdb/gdbinit.d
/etc/gdb/gdbinit
/etc/dradis/initializers
/etc/cryptsetup-initramfs
/etc/apparmor/init
/etc/init.d
/etc/X11/xinit
/etc/X11/xinit/xinitrc
/etc/security/namespace.init
/etc/alternatives/initdb.1.gz
/etc/wireshark/init.lua
/etc/xdg/xfce4/xinitrc
/etc/default/grub.d/init-select.cfg

```

#####  find /etc -size +204800  ------------在目录/etc中查找大于204800的文件

```python
 find / -size +204800     #1数据块     512字节     0.5k
    					#100mb=102400km  204800数据块
 ----------------------------------------------
/usr/bin/burpsuite
/usr/lib/oracle/19.6/client64/lib/libociei.so
/usr/lib/jvm/java-11-openjdk-amd64/jmods/java.base.jmod
/usr/lib/jvm/java-11-openjdk-amd64/lib/modules
/usr/lib/firefox-esr/libxul.so
find: ‘/run/user/1000/gvfs’: 权限不够
/proc/kcore
find: ‘/proc/2032/task/2032/fd/5’: 没有那个文件或目录
find: ‘/proc/2032/task/2032/fdinfo/5’: 没有那个文件或目录
find: ‘/proc/2032/fd/6’: 没有那个文件或目录
find: ‘/proc/2032/fdinfo/6’: 没有那个文件或目录
/sys/devices/pci0000:00/0000:00:0f.0/resource1
/sys/devices/pci0000:00/0000:00:0f.0/resource1_wc
            
            
  #    +n  大于  	  -n    小于     n  等于


```

##### 	find  /home -user yangyubo-----------在home目录下查找所有者为yangyubo的文件

##### 	find /home -group yangyubo-------------在home目录下查找所属组为yangyubo的文件

##### 	find /home -cmin -5-------------------在home目录下查找5分钟内被修改过属性的文件和目录

```python
-amin   访问时间 access
-cmin   文件属性 change
-mmin	文件内容 modify
```

##### find  /etc -size +163840 -a  -size -204800   ---------在etc目录下，查找大于80mb小于100mb的文件

```python
-a  两个条件同时满足	and
-o 两个条件满足一条		or
```

##### find /etc -name ini -exec ls -l {} \;-------------------在etc文件夹下查找名字为ini的文件并显示详细信息

​		-ok为进一步确认

```python
 find /king -name james -exec ls -ld {} \;                                       
----------------------------------
dr---w---x 2 root root 4096 11月  9 22:44 /king/james

```

##### -inum------根据节点查找

```java
find /king -inum 28835844 -exec rm {} \; 
// 在king文件下查找节点为28835844的文件并把它删除
```

##### -type-----根据文件类型查找

```python
-f  文件
-d  目录
-l	软链接
```

#### locate----在文件资料库中查找文件

```python
命令名称：locate  #updatedb  #升级文件资料库	
					#临时文件不在收纳目录内
​	命令所在路径：/usr/bin/locate
​	执行权限：所有用户
​	语法：locate 文件名
​	功能描述：在文件资料库中查找文件
	范例：locate inittab
	------------------------
	└─# locate inittab
	/usr/share/terminfo/a/ansi+inittabs
	/usr/share/vim/vim82/syntax/inittab.vim

```

#### which----搜索命令所在目录及别名信息

```python
命令名称：which  #updatedb  #升级文件资料库	
					#临时文件不在收纳目录内
​	命令所在路径：/usr/bin/which
​	执行权限：所有用户
​	语法：which 命令
​	功能描述：搜索命令所在目录及别名信息
	范例：which ls
	------------------------
	└─# which cp
		/usr/bin/cp
               
```

#### whereis----搜索命令所在目录及帮助文档路径

```python
命令名称：whereis
	命令所在路径：/usr/bin/whereis
	执行权限：所有用户
	语法：whereis 命令
	功能描述：搜索命令所在目录及帮助文档路径
	范例：whereis rm
------------------------
# whereis rm
rm: /usr/bin/rm /usr/share/man/man1/rm.1.gz
```









##  Linux及操作系统介绍

### 一、操作系统的作用

#### 1、五大基本功能

- 进程和线程的管理：进程线程的状态、控制、同步互斥、通信调度等
- 存储管理：分配/回收、地址转换、存储保护等
- 文件管理：文件目录、文件操作、磁盘空间、文件存取控制
- 设备管理：设备驱动、分配回收、缓冲技术等
- 用户接口：系统命令、编程接口

#### 2、三个作用

- 资源的管理者
- 向用户提供各种服务
- 对硬件机器的扩展

<img src="https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532227.png" alt="image-20220126115908802" style="zoom:67%;" />

![image-20220126122834697](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532228.png)

![image-20220126143656800](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532229.png)

**SSH默认端口号为22**

## 使用Xshell

![image-20220126144605696](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532230.png)

### SSH

```
可以使用window连接，也可以使用Linux连接
方式一
ssh root@192.168.184.133
方式二
ssh -l root 192.168.184.133
```

### SCP

```
上传
scp Windows文件路径 root@192.168.184.133:Linux路径
下载
scp root@192.168.184.133:Linux路径 Windows文件路径
```

## Linux的文件系统

```python
/dev/shm          #这个目录不在硬盘上，而是在内存里。
```

### 一、文件系统目录

**/bin：**
bin是Binary的缩写, 这个目录存放着最经常使用的命令。
**/boot：**
这里存放的是启动Linux时使用的一些核心文件，包括一些连接文件以及镜像文件。
**/dev ：**
dev是Device(设备)的缩写,该目录下存放的是Linux的外部设备，在Linux中访问设备的方式和访问
文件的方式是相同的。
**/etc：**
这个目录用来存放所有的系统管理所需要的配置文件和子目录。
**/home：**
用户的主目录，在Linux中，每个用户都有一个自己的目录，一般该目录名是以用户的账号命名的。
**/lib：**
这个目录里存放着系统最基本的动态连接共享库，其作用类似于Windows里的DLL文件。几乎所有的应用
程序都需要用到这些共享库。
**/lost+found：**
这个目录一般情况下是空的，当系统非法关机后，这里就存放了一些文件。
**/media：**
linux 系统会自动识别一些设备，例如U盘、光驱等等，当识别后，linux会把识别的设备挂载到这个目
录下。
**/mnt：**
系统提供该目录是为了让用户临时挂载别的文件系统的，我们可以将光驱挂载在/mnt/上，然后进入该目
录就可以查看光驱里的内容了。
**/opt：**
这是给主机额外安装软件所摆放的目录。比如你安装一个ORACLE数据库则就可以放到这个目录下。默认
是空的。
**/proc：**
这个目录是一个虚拟的目录，它是系统内存的映射，我们可以通过直接访问这个目录来获取系统信息。
这个目录的内容不在硬盘上而是在内存里，我们也可以直接修改里面的某些文件，
比如可以通过下面的命令来屏蔽主机的ping命令，使别人无法ping你的机器：
echo 1 > /proc/sys/net/ipv4/icmp_echo_ignore_all
**/root：**
该目录为系统管理员，也称作超级权限者的用户主目录。
**/sbin：**
s就是Super User的意思，这里存放的是系统管理员使用的系统管理程序。
**/selinux：**
这个目录是Redhat/CentOS所特有的目录，Selinux是一个安全机制，类似于windows的防火墙，但
是这套机制比较复杂，这个目录就是存放selinux相关的文件的。
**/srv：**
该目录存放一些服务启动之后需要提取的数据。
**/sys：**
这是linux2.6内核的一个很大的变化。该目录下安装了2.6内核中新出现的一个文件系统 sysfs 。
sysfs文件系统集成了下面3种文件系统的信息：针对进程信息的proc文件系统、针对设备的devfs文件
系统以及针对伪终端的devpts文件系统。该文件系统是内核设备树的一个直观反映。
当一个内核对象被创建的时候，对应的文件和目录也在内核对象子系统中被创建。
**/tmp：**
这个目录是用来存放一些临时文件的。
**/usr：**
这是一个非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似于windows下的
program files目录。
**/usr/bin：**系统用户使用的应用程序。
**/usr/sbin：**
超级用户使用的比较高级的管理程序和系统守护程序。
**/usr/src：**
内核源代码默认的放置目录。
**/var：**
这个目录中存放着在不断扩充着的东西，我们习惯将那些经常被修改的目录放在这个目录下。包括各种日
志文件。
**/run：**
是一个临时文件系统，存储系统启动以来的信息。当系统重启时，这个目录下的文件应该被删掉或清除。
如果你的系统上有 /var/run 目录，应该让它指向 run。

**通常情况下，我们可以使用/opt和/home目录，保存数据，安装应用程序，这两个目录均是由用户自由处理，不存在敏感文件，默认情况下程序安装路径回在/usr/bin或/var/目录下。**

### 二、Linux的启动级别

| 命令实例         | 作用                                                     |
| ---------------- | -------------------------------------------------------- |
| 文件/etc/inittab | 设置默认启动级别                                         |
| 0                | 代表halt，关机操作，这个0不能配置，否则机器将不能启动    |
| 1                | 代表单用户模式，采用这个设置，系统只能允许一个用户登录   |
| 2                | 代表多用户模式，但不支持网络工作                         |
| 3                | 代表命令行界面，即文本界面，是企业中服务器通用的启动模式 |
| 4                | 系统预留，改级别目前还没有使用                           |
| 5                | 代表图形界面，也是Linux系统启动时默认的启动模式          |
| 6                | 代表重启模式，这个6也不可设置，否则系统反复重启          |

#### init

```java
init   3   //切换启动级别为3
```

### 三、Linux的关机与重启

| 命令实例          | 作用              |
| ----------------- | ----------------- |
| reboot            | 重启              |
| shutdown -r now   | 现在立即重启      |
| shutdown -r 11:30 | 等到11:30进行重启 |
| shutdown -r +1    | 等待一分钟后重启  |
| halt              | 关机              |
| shutdown -h now   | 现在立刻关机      |
| shutdown -h 11:30 | 等到11:30进行关机 |
| init 0            | 关机              |
| init 6            | 重启              |

### 四、常见命令使用

#### 1、top命令

类似于Windows的任务管理器，可以查看CPU和内存的使用情况，也可以查看每个进程所消耗的CPU和内存，及进程ID等信息

![image-20220126204713571](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532231.png)

top命令是全屏输出结果，如果要退出该命令，可以按`Q`键或`Ctrl+C`退出

#### 2、其他命令

| 命令              | 作用                                             |
| :---------------- | ------------------------------------------------ |
| cd ../或者 cd ..  | 切换到上一层目录(相对目录)                       |
| cd 目录名         | 切换到对应目录（绝对目录）                       |
| pwd               | 查看当前所在目录                                 |
| du -sh            | 查看文件或文件夹的大小                           |
| fdisk -l          | 查看磁盘分区列表                                 |
| free              | 查看内存使用情况                                 |
| cat 文件名        | 查看文本文件内容，如cat/etc/passwd可查看用户信息 |
| cat /proc/meminfo | 查看内存信息                                     |
| cat /proc/cpuinfo | 查看CPU信息                                      |

## 文本编辑器VI的使用

### 一、文本的创建和查看

| 功能项   | 命令实例                        | 作用                                                         |
| -------- | ------------------------------- | ------------------------------------------------------------ |
| 文件创建 | vi  /opt/learn/hello.txt        | 在目录/opt/learn下创建hello.txt并进入vi编辑界面              |
|          | touch /opt/learn/test           | 在目录/opt/learn下创建空白文件test                           |
|          | cat > /opt/learn/catfile << EOF | 创建文件catflie并在屏幕上输入内容，最后输入EOF结束，如果不使用 <<EOF,则输入结束时直接按Ctrl+D也可 |
|          |                                 |                                                              |
| 文件查看 | vi /etc/passwd                  | 在vi编辑器中输入文本内容                                     |
|          | cat /etc/passwd                 | 在屏幕上输入文本内容                                         |
|          | more /etc/passwd                | 分屏输出文本内容                                             |
|          | less /etc/passwd                | 分屏输出文本内容并按需加载文件（适合于大文件的查看），看一行加载一行 |
|          | head -n 10 /etc/passwd          | 只输出文件的头10行                                           |
|          | tail -n 20 /etc/passwd          | 只输出文件末尾的20行                                         |
|          | tail -f 文本文件                | 表示通过流的方式实时查看最新的文件内容                       |
|          | strings /bin/ls                 | 查看二进制文件中的可打印字符                                 |



![image-20220127104831502](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532232.png)

### 二、文本内容的编辑

默认两种模式：命令模式和编辑模式。默认模式输入`i`或`a`进入编辑模式，在编辑模式下，按`ESC`进入命令模式

| 命令实例    | 作用                                             |
| ----------- | ------------------------------------------------ |
| vi filename | 生成新文件或者编辑查看文件                       |
| i或者a      | 从命令模式进入编辑模式，i为插入文本，a为追加文本 |
| Esc         | 从编辑模式进入到命令模式                         |
| :w          | 保存文本                                         |
| :wq         | 保存并退出                                       |
| :wq!        | 保存并强制退出                                   |
| :q          | 退出                                             |
| :q!         | 不保存，强制退出                                 |
| o           | 添加一行                                         |
| O           | 在光标所在行的上方添加一行                       |
| dd          | 删除一行                                         |
| D           | 删除从当前光标到行尾的内容                       |
| x           | 删除一个字符                                     |
| s           | 删除一个字符并切换到编辑模式                     |
| S           | 删除一行并切换到编辑模式                         |
| :n          | 光标移至文本第n行                                |
| $           | 光标移动到文本的行尾                             |
| A           | 光标移动到文本的行尾并进入编辑模式               |
| ^           | 光标移动到文本的行首                             |
| G           | 光标移动到文本的末尾                             |
| gg          | 光标移动到文本的首行                             |
| ZZ          | 存盘退出                                         |
| /字符串     | 查找某个字符串                                   |
| n           | 继续查找                                         |
| :u          | 撤销                                             |
| :redo       | 重做                                             |

### 三、修改IP地址为静态IP

默认情况下，Linux的IP地址为动态分配，而面向服务器应用场景，通常建议设置为静态IP，操作步骤如下：

#### 1、查看默认网关，运行`ip route`命令

```
[root@yyb ~]# ip route
default via 192.168.184.2 dev ens33 proto dhcp metric 100 
192.168.184.0/24 dev ens33 proto kernel scope link src 192.168.184.134 metric 100 
```

可以看出默认网关地址为：192.168.184.2

#### 2、确认动态IP地址及网段等信息`ip addr`

```
[root@yyb ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:a9:7f:78 brd ff:ff:ff:ff:ff:ff
    inet 192.168.184.134/24 brd 192.168.184.255 scope global noprefixroute dynamic ens33
       valid_lft 979sec preferred_lft 979sec
    inet6 fe80::aad0:e6bd:aff3:d0dd/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
```

#### 3、使用vi编辑静态IP地址

运行命令：`vi /etc/sysconfig/network-scripts/ifcfg-ens33`，其中ens33与ip addr看到的网卡编号保持一致，并修改网上的IP地址信息如下:

```java
TYPE="Ethernet"
PROXY_METHOD="none"
BROWSER_ONLY="no"
#BOOTPROTO="dhcp"		//Ip地址的分配方式
BOOTPROTO="static"    //修改为静态
DEFROUTE="yes"
IPV4_FAILURE_FATAL="no"
IPV6INIT="yes"
IPV6_AUTOCONF="yes"
IPV6_DEFROUTE="yes"
IPV6_FAILURE_FATAL="no"
IPV6_ADDR_GEN_MODE="stable-privacy"
NAME="ens33"			//网卡的名称
UUID="a46aedd8-dcff-444b-8d94-cf4910ebc4fa"
DEVICE="ens33"
ONBOOT="yes"		//是否在电脑启动的时候启动网卡
    
IPADDR="192.168.184.188"    //IP地址
NETMASK="255.255.255.0"		//子网掩码
GATEWAY="192.168.184.2"		//网关
DNS1="192.168.184.2"		//DNS服务器
//下面这两个可以不用配置，使用默认值
DNS2="114.114.114.114"		//备用DNS服务器
BROADCAST="192.168.184.255"		//广播地址
```

#### 4、重启网卡，使配置生效

```java
systemctl restart network    //重启网络
```

## 文件和文件夹操作

### 一、文件操作

| 功能项       | 命令或者格式                     | 作用                                                         |
| ------------ | -------------------------------- | ------------------------------------------------------------ |
| **文件操作** | cp hello.txt /opt/test           | 把文件hello.txt复制到文件夹/opt/test下                       |
|              | cp hello.txt /opt/test/hello.cp  | 把文件hello.txt复制到文件夹/opt/test下并重命名为hello.cp     |
|              | mv hello.txt /opt/test           | 把文件hello.txt移动到文件夹/opt/test下                       |
|              | mv  hello.txt /opt/test/hello.mv | 把文件hello.txt移动到文件夹/opt/test下并重命名为hello.mv     |
|              | mv hello.txt hello.png           | 重命名                                                       |
|              | rm /opt/test/hello.txt           | 删除文件                                                     |
|              | rm -f /opt/test/hello.png        | 强制删除文件，不会有提示信息                                 |
|              | du -sk hello.txt                 | 查看文件hello.txt的大小（以K为单位）                         |
|              |                                  |                                                              |
| **连接**     | ln -s hello.txt shello           | 为hello.txt文件创建一个名为shello的软链接（类似于快捷方式）  |
|              | ln -d hello.txt dhello           | 为hello.txt文件创建一个名为dhello的硬链接，硬链接表示所有文件中任意更改一个，其他文件的所有属性会跟着变化，如大小、更新时间、权限等 |

### 二、文件夹操作

| 功能项    | 命令或格式                                  | 作用                                             |
| --------- | ------------------------------------------- | ------------------------------------------------ |
| ls / tree | ls [option] [file/directory]                | 显示指定目录下的所有文件或文件夹                 |
|           | ls                                          | 显示当前目录的内容                               |
|           | ls -l                                       | 显示当前目录的详细内容                           |
|           | ls -a                                       | 显示所有文件，包括隐藏文件                       |
|           | ls*.txt                                     | 显示目前目录下所有以.txt为后缀名的文件           |
|           | ls /opt/888                                 | 显示/opt/888下的内容                             |
|           | ls -R /opt/                                 | 列出所有/opt目录及子目录的内容                   |
|           | tree /opt                                   | 用树状图显示目标及文件                           |
|           |                                             |                                                  |
| pwd       | pwd                                         | 显示当前所在目录                                 |
|           |                                             |                                                  |
| cd        | cd directory                                | 切换到指定目录                                   |
|           | cd ~                                        | 切换到当前用户的主目录                           |
|           | cd ..                                       | 返回当前目录的上一级目录                         |
|           | cd /opt/learn                               | 用绝对路径切换到/opt/learn目录下                 |
|           | cd ../../                                   | 使用相对路径切换到当前目录的上一级的上一级目录下 |
|           |                                             |                                                  |
| mkdir     | mkdir [option] [directory1] [directory2]... | 创建目录                                         |
|           | mkdir /opt/learn/other                      | 在目录/opt/learn/下创建目录other                 |
|           | mkdir dir2 dir3 dir4                        | 同时创建dir2 dir3 dir4三个目录                   |
|           | mkdir -p /dir2/dir3/dir4                    | 同时创建多层目录                                 |
|           |                                             |                                                  |
| rmdir     | rmdir dir1                                  | 删除一个空目录                                   |
|           |                                             |                                                  |
| 其他操作  | cp -r /opr/learn   /opt/learn2              | 拷贝文件夹                                       |
|           | mv /opr/learn2  /opt/learn3                 | 重命名文件夹                                     |
|           | rm -rf /opt/learn3                          | 强制删除文件夹                                   |

## 用户与用户权限	

### 一、用户与用户组

| 功能项  | 命令实例                     | 作用                                                 |
| ------- | ---------------------------- | ---------------------------------------------------- |
| 用户组  | cat /etc/group               | 查看当前系统存在的用户组                             |
|         | groupadd testing             | 添加一个新的用户组testing                            |
|         | cat /etc/group               | 查看组是否被新增成功                                 |
|         | groupmod -n test testing     | 将testing重命名成test                                |
|         | groupdel test                | 删除组test                                           |
|         | groups root                  | 查看用户root所在的所有组                             |
|         |                              |                                                      |
| useradd | cat /etc/passwd              | 查看当前系统的用户                                   |
|         | useradd yang                 | 新增一个用户yang（默认将新增一个对应的名为yang的组） |
|         | useradd -g test yang         | 新增一个用户yang并将其加入test组                     |
|         | useradd -g test -G dev  yang | 新增一个用户yang，起主组为test，并附加到组dev中      |
|         |                              |                                                      |
| usermod | usermod -g dev yang          | 将用户yang切换到dev组                                |
|         | usermod -G 502 yang          | 将用户yang附加到gid为502的这个组                     |
|         | usermod -d /home/temp/mary   | 将mary的主目录从/home/mary改为/home/mary             |
|         |                              |                                                      |
| userdel | userdel  yang                | 删除用户yang                                         |
|         | userdel -f  yang             | 强制删除用户yang（即使用户已登录）                   |
|         | userdel -r yang              | 删除用户yang并删除其主目录                           |

### 二、文件与文件夹权限	

| 功能项             | 命令实例                       | 作用                                                         |
| ------------------ | ------------------------------ | ------------------------------------------------------------ |
| chmod              | chmod [权限] [文件或目录]      | 更改文件或目录的权限                                         |
| 用户授权问题       | ls -l hello.txt                | 查看文件的详细属性，对其进行解释                             |
|                    | 左边10位中的第一位代表文件类型 | d------目录，------普通文件，l----链接文件                   |
|                    | 左边10位的后9位代表权限        | 前三位代表文件所有者的权限（用u表示）中间3位代表文件所在组的权限（用g表示）后三位代表其他组的权限（用o表示） |
|                    | 权限rwx的含义                  | r----4----可读，w----2----写，x----1----可执行               |
|                    | chmod u+x hello.txt            | 为hello.txt文件的所有者添加可执行权限                        |
|                    | chmod u-w hello.txt            | 为hello.txt文件的所有者去除可执行权限                        |
|                    | chmod g-r hello.txt            | 为hello.txt文件的所在组去除可读权限                          |
|                    | chmod o+w hello.txt            | 为hello.txt文件的所在组的其他组添加可写权限                  |
|                    | chmod a+w hello.txt            | 为所有三种角色添加可写权限                                   |
|                    | chmod a+wx hello.txt           | 为所有三种角色添加可写权限                                   |
|                    | chmod a-rwx hello.txt          | 去除hello.txt的所有权限（此时仅有root可以编辑）              |
|                    | chmod 777 hello.txt            | 将hello.txt的权限设置为rwxrwxrwx                             |
|                    | chmod 643  hello.txt           | 将hello.txt的权限设置为rw-，r--，-wx                         |
|                    | chmod 777 /opt/test            | 将目录/opt/test的权限更改为777                               |
|                    | chmod -R 755 /opt/test         | 将目录/opt/test及其下所有的文件和子目录的权限更改为755       |
|                    |                                |                                                              |
| chown              | chown yang hello.txt           | 将hello.txt的文件所有者改为yang                              |
| 文件所归属的所有者 | chown yang /opt/test           | 将目录/opt/test的所有者改为yang                              |
|                    | chown -R yang /opt/test        | 将目录/opt/test及其下所有的文件和子目录的所有者改为yang      |
|                    |                                |                                                              |
| chgrp              | chgrp  yang  hello.txt         | 将hello.txt所在组改为yang                                    |
| 文件组的问题       | chgrp yang /opt/test           | 将/opt/test所在组改为yang                                    |
|                    | chgrp -R mary /opt/test        | 将目录/opt/test及其所有子目录和文件所在组改为yang            |
|                    |                                |                                                              |
| passwd             | passwd yang                    | 修改yang 的密码      /etc/shadow保存了所有用户的密码，默认只有root可以查看 |

## 文件内容查找与归档压缩

### 一、文件查找

| 功能项 | 命令实例                                      | 作用                                                         |
| ------ | --------------------------------------------- | ------------------------------------------------------------ |
| find   | find  起始目录  查找类型  查找条件            | 查找其实目录及所有子目录下的文件及文件夹                     |
|        | find . -name "hello.txt"                      | 查找当前目录下文件名为hello.txt的文件或文件夹                |
|        | find . -name "hello"                          | 查找当前目录下文件名包含hello的文件或文件夹                  |
|        | find /home -name "bash"                       | 查找目录/home下文件名包含bash的文件或文件夹                  |
|        | find . -name "*"                              | 查找当前目录下的所有文件或文件夹（作用同-ls -R）             |
|        | find . -name "[h]*"                           | 查找当前目录下以h开头的文件或文件夹                          |
|        | find . -name "[h\|f]*"                        | 查找当前目录下所有以h或f开头的文件或文件夹，\|可以省略       |
|        | find . -name "[a-z]*"                         | 查找当前目录下所有以小写字母开头的文件或文件夹               |
|        | find . -name "[A-Z]*"                         | 查找当前目录下所有以大写字母开头的文件或文件夹               |
|        | find . -name "[a-Z]*"                         | 查找当前目录下所有以字母开头的文件或文件夹                   |
|        | find . -name "[0-9]*"                         | 查找当前目录下所有以数字开头的文件或文件夹                   |
|        | find . -name "h?llo*"                         | 查找当前目录下所有以h后面带一个字符再加llo开头的文件或文件夹 |
|        | find . -name "[ ^ a-b]*"                      | 查找当前目录下不以a-b开头的文件或文件夹                      |
|        | find . -name  ' \ \\'                         | 查找当前目录下包含特殊字符\的文件夹（注意使用单引号）        |
|        |                                               |                                                              |
|        | find . -perm 777                              | 查找当前目录下权限为777的文件或文件夹                        |
|        | find . -path "./test" -prune -o -name "hello" | 查找当前目录下除test目录的其他所有目录中包含hello的文件或文件夹 |
|        | find . -user yang                             | 查找当前目录下文件所有者为yang的文件或文件夹                 |
|        | find . group yang                             | 查找当前目录下文件或所属组为yang的内容                       |
|        | find . -mtime -3                              | 查找当前目录下在3天内更新过的文件或文件夹                    |
|        | find . -mtime +3                              | 查找当前目录下在3天前更新过的文件或文件夹                    |
|        | find . -newer hello.txt                       | 查找当前目录下比hello.txt新的文件或文件夹                    |
|        | find . !-newer hello.txt                      | 查找当前目录下比hello.txt旧的文件或文件夹                    |
|        | find . -type d                                | 查找当前目录下所有的文件夹（普通文件的类型为f），了解Linux文件夹类型：<br />1）f：普通文件，如文本文件，可执行文件<br />2）c：字符设备，如终端、磁带机等<br />3）b：块设备，如光盘、硬盘等<br /> |
|        | find . -type l                                | 查找当前目录下所有的软连接文件                               |
|        | find . -size 200c                             | 查找当前目录下文件大小为200字节的文件（c表示byte）           |
|        | find. -size +200c                             | 查找当前目录下文件大小大于200字节的文件（用-表示小于）       |
|        | find . -name "hello*" -exec ls -l {} \;       | 查找当前目录下所有以hello开头的文件并将其细节显示出来，如果查找出了目录，那么此时目录也会被ls -l列出来 |
|        | find . -name "hello*" -exec rm {} \;          | 查找当前目录下所有以hello开头的文件并将其删除                |
|        | find . -name "hello" \| xargs ls -l           | 查找当前目录下所有以hello开头的文件并将其细节显示出来，xargs可以查找文件内容里面的东西 |
|        | Linux里的\|                                   | 管道，前面内容的输出就是后面内容的输入                       |

### 二、内容查找

| 功能项          | 命令实例                             | 作用                                                  |
| --------------- | ------------------------------------ | ----------------------------------------------------- |
| grep            | grep[选项]匹配模式 目标文件          | 基于行对目标文件的内容进行查找                        |
|                 | grep "root" /etc/passwd              | 查找到/etc/passwd文件中包含root的行                   |
|                 | grep -n "root" /etc/passwd           | 查找到/etc/passwd文件中包含root的行,并显示行号        |
|                 | grep "^root" /etc/passwd             | 查找以root为行首的行                                  |
|                 | grep "root$" /etc/passwd             | 查找以root为行尾的行                                  |
|                 | grep "^[a\|b]" /etc/passwd           | 查找以a或者b为行首的行                                |
|                 | grep -v “abc”                        | 排除包含abd的行                                       |
|                 | ls \| grep test                      | 从ls 的输出中过滤包含test的文件名                     |
|                 | grep -r games /etc                   | 在/etc目录下查找所有包含games的文件                   |
|                 | grep "^s.*login$" ./passwd           | 从passwd下查找s开头，login结尾的行                    |
|                 |                                      |                                                       |
| find 与grep结合 | find ./ -name "*" \| xargs grep word | 遍历某个目录下的所有文件中包含word的文件              |
| wc              | wc -l                                | 统计文件行数或输出的个数，-c只显示Bytes数。-l显示行数 |

### 三、文档归纳压缩

| 功能项     | 命令实例                         | 作用                                  |
| ---------- | -------------------------------- | ------------------------------------- |
| tar /gzip  | tar -cvf hello.tar hello.txt     | 把hello.txt归档并命名为hello.tar      |
|            | tar -cvf test.tar  /opt/test     | 把/opt/test归档并命名成test.tar       |
|            | tar -tf test.tar                 | 将归档文件test.tar中的文件显示出来    |
|            | tar -xvf test.tar                | 提取归档文件中的内容                  |
|            | gzip hello.tar                   | 将归档文件hello.tar压缩成hello.tar.gz |
|            | gzip -d hello.tar.gz             | 解压缩文件成hello.tar                 |
|            | tar -zcvf hello.tar.gz hello.txt | 将hello.txt归档并压缩成hello.tar.gz   |
|            | tar -zxvf hello.tar.gz           | 解压缩                                |
|            |                                  |                                       |
| zip /unzip | zip hello.zip hello.txt          | 将hello.txt压缩并命名成hello.zip      |
|            | zip -r text.zip /opt/test        | 将/opt/test目录压缩                   |
|            | unzip -v hello.zip               | 解压缩，并显示进度                    |
|            | unzip hello.zip                  | 解压缩hello.zip                       |

## 进程与服务管理

### 课堂实验

- 使用`ps`命令查看进程，包括过滤进程信息
- 使用`systemctl`命令管理Linux服务

### 课堂引入

- 进程（Process）：操作系统正在运行的应用程序，任意一个进程，都会有进程ID，都会消耗CPU和内存资源。
- 服务（Service）：通过服务控制面板或命令可以直接启动应用程序，也可能是操作系统启动时自动启动的后台应用程序。服务一旦运行，也是一个进程。
- 在Windows中，可以运行`services.msc`命令打开服务控制面板

### 一、进程相关命令

```shell
ps：当前终端启动的进程
ps -ef  或 ps  aux  ：查看当前操作系统里面所有进程信息
ps aux | grep sbin：查找进程里面包含sbin的进程信息
ps aux | sort -k 3 -r | head -n 6：取出最消耗CPU的前5个进程信息
		-k表示第几列，默认为第一列
		-r表示反转，则降序排列
top：查看进程信息和系统的性能情况
top -n 1 | sort -k 9 -r | headd -n 6：取出最消耗CPU的前5个进程信息
		-n表示更新几次后关闭
kill PID:结束进程
kill -9 PID:强制结束进程
```

### 二、服务管理与运行

1. service:在CentOS7以前的版本使用，另外，在其他Linux发行版中通常也使用service
2. systemctl：在CentOS7以后的版本使用，当然也兼容service

```python
#查看服务状态
service sshd status
systemctl status sshd

#启动某个服务
service sshd start
systemctl start sshd

#停止服务
service sshd stop
systemctl stop sshd

#重启服务
service sshd restart
sysemctl restart sshd

#启用自动启动的功能
systemctl enable sshd

#禁止自动启动的功能
systemctl disable sshd

#查看自动启动服务情况
systemctl list-unit-files
systemctl list-unit-files | grep sshd   #查看sshd服务情况 ,enabled表示自动启动

#启动自带防火墙服务
systemctl start firewalld
```

### 三、Xampp安装

```python
首先Xampp是一个自解压离线安装包，不需要下载，不需要额外命令，先确保上传，然后给安装包赋予可执行权限
默认情况下，即使是执行当前目录下的可执行程序，也不能直接写文件名，而是必须在文件名前面加./，才是表示执行当前目录下的可执行程序
如果不加./，Linux不会在当前目录下寻找，而是去系统预先配置好的环境变量中去寻找，但是找不到，所以会报错
#正确执行命令
./xampp-linux-x64-7.3.29-1-installer.run

安装完成后，/opt/lampp/lampp start 启动Xampp的三个服务：Apache、MySQL、ProFTP
第一次启动时会报错，修改 vi /opt/lampp/lampp ，将2.2.5的内核版本号修改为2.8.0以上
再次启动可能会报netstat:command not found
netstat时Linux中一个常规的网络相关的命令，用于查看系统中开启了那些端口，默认最小化安装时没有安装

#安装命令
yum install net-tools
    
```

## 在Linux中安装应用	

### 一、使用Rpm离线安装

先下载到本地，以.rpm文件名结尾，下载完成后，再安装

```java
rpm -qa | grep mysql    //查询所有的已经安装过的安装包，显示含有mysql关键字的
//安装
rpm -ivh yyb.rpm
//卸载
rpm -e yyb.noarch
```

利用rpm安装MySQL服务器版：

```
error:Failed dependencies：失败的依赖
```

### 二、基于源代码安装应用

源码安装比较适用于专业人员，并不需要安装人员能看懂源码，但需要知道源代码的基本过程

```
解压后去源代码目录下找以下几个文件：configure		setup.sh	install.sh
./configure
make
mkae install
```

使用源码安装nginx，解压后的样子

![image-20220206222256071](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532233.png)

```java
[root@yyb nginx-1.21.2]# ./configure 
checking for OS
 + Linux 3.10.0-1160.el7.x86_64 x86_64
checking for C compiler ... not found

./configure: error: C compiler cc is not found


//解决方法
yum install gcc -y
安装完成后再次进行配置，如果提示缺少依赖pcre或zlib等库，则继续yum install pcre-devel
通常情况下提示缺少什么库，一般先尝试yum install pcre，如果不行，再尝试yun install pcre-devel
```

### 三、Yum命令操作

Yum（全称为Yellow dog Updater，Modified）是一个在Fedora和RedHat以及CentOS中的Shell前端软件包管理器。基于RPM包管理，能够从指定的服务器自动下载RPM包并且安装，可以自动处理依赖性关系，并且一次安装所有的依赖的软件包，无须繁琐地一次次下载、安装。

```java
yum list	//查询本机已安装的包
yum search mysql	//在线搜索当前源（库）可用的包
yum repolist	//列出当前的镜像的仓库（repository）
    
yum install		//安装
yum install gcc -y		//不再提示是否确认，直接选择Yes
yum install gcc cmake gcc-c++ mysql wget -y	：//一次安装多个包  
    
yum deplist curl	//查看应用程序curl的依赖库（library）

yum erase wget 		//卸载wget，卸载过程建议不加-y，做二次确认
yum remove wget 		//同上 
    
yum clera all		//清空缓存的镜像列表
yum makecache		//重新根据配置文件构建镜像缓存列表
    
yum update			//更新
```

### 四、Yum配置源

默认配置文件：/etc/yum.repo.d/CentOS-Base.repo

```
[base]
name=CentOS-$releasever - Base
mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=os&infra=$infra
#baseurl=http://mirror.centos.org/centos/$releasever/os/$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7

mirrorlist并非镜像本身的地址，而是一堆镜像网址的集合，CentOS会自动选择速度最快的一个，每一个对应的就是具体的仓库，比如
http://mirrors.163.com/centos/7.9.2009/os/x86_64/
baseurl:对应的是具体的镜像地址，里面保存着仓库的各个安装包程序
```



http://mirrorlist.centos.org/?release=7&arch=x86_64&repo=os&infra



```
http://mirror.lzu.edu.cn/centos/7.9.2009/os/x86_64/
http://mirrors.neusoft.edu.cn/centos/7.9.2009/os/x86_64/
http://mirrors.cn99.com/centos/7.9.2009/os/x86_64/
http://mirrors.bupt.edu.cn/centos/7.9.2009/os/x86_64/
http://mirrors.163.com/centos/7.9.2009/os/x86_64/
http://ftp.sjtu.edu.cn/centos/7.9.2009/os/x86_64/
http://mirrors.huaweicloud.com/centos/7.9.2009/os/x86_64/
http://mirrors.aliyun.com/centos/7.9.2009/os/x86_64/
http://mirrors.tuna.tsinghua.edu.cn/centos/7.9.2009/os/x86_64/
http://mirrors.bfsu.edu.cn/centos/7.9.2009/os/x86_64/
```

![image-20220207103542581](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532234.png)

下载阿里云的Repo源配置文件http://mirrors.aliyun.com/repo/Centos-7.repo

![image-20220207104540409](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532235.png)

替换CentOS-Base.repo

yum repolist

### 五、Apt安装

- 对于Redhat体系的Linux发行版本，目前主流的是Yum+Rpm的方式，可以在线安装依赖。在新的CentOS-8以后的版本中，引入了新的安装方式：dnf，本质上跟yum几乎没有区别
- 对于Debian体系的Linux发行版本，主要安装命令两个：apt-get，apt，优先考虑使用apt

## 常见的网络相关命令

### 一、常用的网络命令

#### 1、ping命令

```java
ping www.baidu.com		//测试是否和www.baidu.com的服务器连通，同时可以查看响应时间及响应时间分布情况
ping -i 3 www.baidu.com			//每三秒钟访问一次
ping -c 5 www.baidu.com			//一个发送5个数据包
ping -f www.baidu.com			//快速发送ICMP数据包，进行压力测试
ping -f -c 200 www.baidu.com			//设定具体的发包数量，用于快速检测响应时间等数据
ping -s 1024 www.baidu.com			//设定每个ICMP数据包的大小
```

#### 2、ip route2命令

```java
ip addr			//查看网卡及IP信息
ifconfig

ip neigh			//ARP协议，查看相邻计算机
arp -an

ip link				//查看网卡MAC地址等
ip -s link			//查看网卡的收发数据包大小，RX：收    TX：发
ifconfig -s

ip addr add 192.168.1.1/24 dev ens33		//临时为ens33网卡添加一个IP地址，systemctl restart network后消失
ifconfig ens33 192.168.1.1			//临时修改IP地址

ip addr del 192.168.1.1/24 dev ens33			//删除一个IP地址

//查看路由IP地址
ip route			
route
netstat -r
route -n

ip route add default via 192.168.1.1			//为当前网络添加默认路由（网关）
route add default gw 192.168.1.1

ip route del default via 192.168.1.1			//删除路由地址
route del dafaule gw 192.168.1.1
    
ip route flush cache			//刷新路由表
    
ip link set ens33 up			//启动网卡
ifconfig ens33 up
ifconfig ens33 down				//关闭网卡

ss -anl 			//查看当前系统中的端口占用情况
netstat -anlop
```

![image-20220207113558519](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532236.png)

#### 3、traceroute命令

```java
Linux:
tracertoute www.baidu.com			//跟踪到达baidu.com的所有路由节点和路径

windows:
tracert www.baidu.com
```

#### 4、curl命令

```python
curl http://www.baidu.com/			#访问网页
curl -o baidu.html http://www.baidu.com/			#直接保存到文件里
curl -O http://www.baidu.com/train/index.html			#以index.html为文件名保存到本地
```

#### 5、wget

```python
wget http://cn.wordpress.org/wordpress.tar.gz				#下载文件
wget -O yyb.tar.gz http://cn.wordpress.org/wordpress.tar.gz			#指定文件名下载
wget -c yyb.tar.gz http://cn.wordpress.org/wordpress.tar.gz			#断点续传
wget -b yyb.tar.gz http://cn.wordpress.org/wordpress.tar.gz				#后台下载
```

## TCPDump流量监控工具

### 一、流量监控概述

对于一个通信过程的分析，首先需要把握5个基本数据：

```
源IP
源端口
目的IP
目的端口
协议
```

然后具体查看内容

### 二、安装tcpdump

```
yum install -y tcpdump

正在安装:
 tcpdump                   x86_64                   14:4.9.2-4.el7_7.1                    base                   422 k
为依赖而安装:
 libpcap                   x86_64                   14:1.5.3-12.el7                       base                   139 k

 libpcap 是Linux上标准的流量监控的库，大多数流量监控工具都是基于这个底层库进行开发
 在Windows上，比较知名的是winpacap和npcap
 目前市场上主流的防火墙、IDS、IPS、包过滤工具，只要涉及到流量的产品或系统，底层均基于以上这些库
```

### 三、tcpdump使用

```java
tcpdump -i ens33    		//监控ens33网卡上的流量，并输出
tcpdump tcp and dst port 80 -i ens33		//监听tcp协议并且目标端口为80r
tcpdump tcp and dst port 80 -i ens33 -w ./target.pcap			//将流量保存到target.pcap，可以下载到Windows，用wireshark打开
tcpdump tcp and dst port 80 -i ens33 -c 100 			//只捕获100条数据包就自动结束
```

## IPTables应用

### 一、IPTables防火墙介绍

​		**一旦重启IPTables，所有规则均失效**

​		IPTables其实不是真正的防火墙，我们可以把它理解成一个客户端代理，用户通过IPTables这个代理，将用户的安全设定执行到对于的“安全框架”中，这个“安全框架”才是真正的防火墙，这个框架的名字叫netfilter，netfilter才是防火墙真正的安全框架（framework），netfilter位于内核空间。IPTables其实是一个命令行工具，位于用户空间，我们用这个工具操作真正的框架。netfilter/iptables（下文简称iptables）组成Linux平台下的包过滤防火墙，与大多数的Linux软件一样，这个包过滤防火墙是免费的，它可以代替昂贵的商业防火墙解决方案，完成封包过滤、封包重定向和网络地址转换（NAT）等功能。

​		iptables是一个基于命令行的防火墙工具，它使用规则链来允许/阻止网络流量。当一条网络连接试图在你的系统中建立时，iptables会查找对应的匹配规则。如果找不到，iptables将对其采取默认操作。

​		iptables的结构是由表（tables）组成，而tables是由链组成，链又是由具体的规划组成。因此我们在编写iptables规则时，要先指定表，再指定链。tables的作用是区分不同功能的规则，并储存这些规则

#### 1、五张表：filter、nat、mangle、raw、security。主要用于将不同的规则存储在不同的表中

- **filter表：默认表，负责过滤数据包（使用频率最高）**
- nat表：用于网络地址转换（IP、端口）
- mangle表：主要应用在修改数据包、流量整形、给数据包打标识
- raw表：这个表很少用到，主要用于配置连接跟踪相关内容，使用频率较少
- security表：这个表用于安全Linux的防火墙规则，是iptables最近的新增表，使用频率较少

#### 2、五条链：流量方向

- input：匹配目标IP是本机的数据包，入站
- output：出口数据包，出站
- forward：匹配流经本机的数据包
- prerouting：修改目的地址，用来做DNAT。如：把内网中的80端口映射到互联网端口
- postrouting：修改源地址，用来做SNAT。如：局域网共享一个公网IP接入internet。

#### 3、规则

- 基于防火墙策略设置的各类防护规则，防火墙规则的执行顺序认为从前到后依次执行、遇到匹配的规则就不再继续向下检查、如果遇到不匹配的规则则会继续向下进行。

### 二、安装与配置IPTables

```java
systemctl stop firewalld			//firewalld默认在没有设定规则的情况下，是拒绝所有流量，而iptables默认没有设定规则情况下，允许所有流量
    
yum install iptables iptables-services
```

### 三、基本的命令使用

![image-20220208135020001](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532237.png)

![image-20220208140418383](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532238.png)

```java
iptables -nL			//将端口号以数字的形式显示默认表filter中的规则
    
iptables -A INPUT -j DROP 			//所有入站流量全部丢弃，包括SSH请求
iptables -A OUTPUT -j DROP			//所有出站流量全部丢弃，包括SSH响应
    -A代表追加
    -I代表插入到开头 
上述两条命令一旦执行，所有流量无法进来，所有流量无法出去，为断网状态    
    
iptables -I INPUT -j DROP
iptables -I OUTPUT -j DROP
    
iptables -I INPUT -p tcp --dport 22 -j ACCEPT			//打开目标端口22，接受流经该端口的流量
iptables -I OUTPUT -p tcp --sport 80 -j ACCEPT 			//打开源22端口
	--dport代表目的地

iptables -I INPUT -p tcp -m multiport --dport 22,80,443 -j ACCEPT			//同时设定多个端口被允许
    
iptables -I INPUT -p icmp -j DROP			//DROP：直接丢弃数据包，不会向源端做任何回复
iptables -I INPUT -p icmp -j REJECT			//REJECT：拒绝接受数据包，并向源端发送拒绝响应
iptables -I OUTPUT -p icmp -j DROP
    
    
iptables -L OUTPUT --line-numbers			//显示出战规则的行号
iptables -D OUTPUT 3			//删除出战规则第三行的规则
    
service iptables save			//由于IPTables重启后所有规则均会失效，所以可以使用此命令保存规则
cat /etc/sysconfig/iptables			//规则会保存到iptables文本里
    
iptables -F					//清空规则
    
//允许本机访问外部IP地址和端口号，通过设定白名单的方式可以防止本机去访问别的服务器
//通过这种场景的设置，可以最大可能避免反弹Shell和挖矿程序去试图通过本地访问目标服务器下载恶意程序或执行恶意命令   
iptabels -I INPUT -i ens33 -p tcp -s 192.168.112.153  --sport 8088 -j ACCEPT
iptables -I OUTPUT -o ens33 -p tcp -d 192.168.112.153 --dport 8088 -j ACCEPT
    //指定网卡ens33，不指定网卡默认所以网卡
    
//防止DDOS攻击，设定一些数据的限制条件
iptables -A INPUT -p tcp --dport 80 -m limit --limit 25/minute --limit-burst 100 -j ACCEPT
    
//远程端口转发 ： 
    //确认端口转发功能是启用的

```

#### 1、端口转发

- 第一种：本机端口转发，比如80端口对外封闭，开放一个15673供外部访问，外部只知道15673，不知道80，可以避免协议猜测

- 第二种：远程端口转发，把本机接受到的请求转发到远程电脑和对应端口上（远程可以是本地局域网，也可以是公网服务器）

  - 本机端口转发

    ```java
    iptables -t nat -A PREROUTING -p tcp --dport 15673 -j REDIRECT --to-port 80		
        //-t nat  指定使用nat表
    ```
  
- 远程端口转发
  
  - 确认端口转发功能是启用的
  
      ```java
      //开启远程转发
      vi /etc/sysctl.conf
      添加net.ipv4.ip_forward = 1
      执行命令 sysctl -p /etc/sysctl.conf
    ```
  
  - PREROUTING上访问8888时，转发给目标服务器和目标端口
  
  - PREROUTING是先于FILTER执行的，所以不需要转发时允许8888端口
  
      ```java
      //当其他主机访问此电脑（192.168.184.137）的8888端口时，通过DNAT的方式转发到180.101.49.11的80端口
      
      //出去
      iptables -t nat -A PREROUTING -d 192.168.184.137 -p tcp --dport 8888 -j DNAT --to-destination 180.101.49.11:80
      
      //回来
      iptables -t nat -A POSTROUTING -d 180.101.49.11 -p tcp --dport 80 -j SNAT --to 192.168.184.137
    ```
  
      

![image-20220208185936657](https://yang-typora.oss-cn-beijing.aliyuncs.com/202205241532239.png)

### 四、命令参数表

| 参数                | 说明                                                         |
| ------------------- | ------------------------------------------------------------ |
| -A                  | 在最后添加一条规则                                           |
| INPUT               | 链名、常用、大写                                             |
| PREROUTING          | 链名、大写                                                   |
| OUTPUT              | 链名、大写                                                   |
| -I                  | 在最前面插入一条规则                                         |
| -s                  | 指定源地址，可以是IP地址，也可以是网段“192.168.109.10/24”；“-s为空”代表所有 |
| -d                  | 目标地址                                                     |
| -p                  | 协议                                                         |
| --dport             | 指定主机端口（目的端口，本机开放或拒绝端口）                 |
| --sport             | 指定主机端口（禁止连接对方某些接口）                         |
| -i                  | 指定网卡名，表示报文流入端口                                 |
| -j                  | 指定所需要的操作                                             |
| ACCEPT              | 允许                                                         |
| REJECT              | 拒绝，拒绝提供服务                                           |
| DROP                | 拒绝，丢弃数据包不回应                                       |
| --src-range         | 源地址范围（如：拒绝某IP段访问）                             |
| --dsc-range         | 目标地址的范围                                               |
| --mac-source        | 源主机的mac地址                                              |
| -t                  | 指定表名，默认是filter                                       |
| -v                  | 查看详细信息                                                 |
| -nvL --line-numbers | 查看filter表中规则的顺序                                     |
| -nvL -t mangle      | 查看mangle表中的防火墙规则                                   |
| -F                  | 清空filter表                                                 |
| -R                  | 替换规则                                                     |
| -m                  | 指定模块                                                     |

## Firewalld防火墙应用

Linux防火墙是通过netfiler来处理的，他是内核级别的框架。iptables被作为netfiler的用户态抽象层，iptables将包通过一系列的规则进行检查，如果包与特定的IP/端口/协议的组合匹配，规则就会被应用到这个包上，以决定包是否被通过、拒绝或丢弃。firewalld是最新的netfiler用户态抽象层。filewalld可以通过定义源IP和端口网络将入站流量分类到不同区域zone。每个区域基于指定的准则按自己配置去通过或拒绝包。另外的改进是基于iptables进行语法简化。firewalld通过使用服务名而不是它的端口和协议去指定服务，使它更易于使用。例如，是使用samba而不是使用UDP端口137和138和TCP端口139和445.它进一步简化语法，消除了iptables中对语句顺序的依赖

### 一、firewalld的基本使用

```java
systemctl start firewalld			//启动
systemctl status firewalld			//查看状态
systemctl disable firewalld			//停止
systemctl stop firewalld			//禁用
systemctl restart firewalld			//重启
```

- **iptables功能总结**

  ```
  常用的两张表：filter、nat     filter用于过滤数据包，nat用于路由转发功能
  常用的两条链：INPUT、OUTPUT
  常见的三个行为：ACCEPT、DROP、REJECT
  限制流量的三个特征：端口、协议、IP		对应的五元组：-d -s --dport --sport -p
  端口转发：本机端口、远程端口
  ```

- **firewalld中，没有表、没有链、没有行为，默认拒绝**

### 二、区域

在不同的区域下，可以设置不同的防火墙策略，以便在需要的时候可以实现快速切换，而不需要从0开始配置一套。对于一套服务器环境来说，通常情况下，没有那么多需要去切换。drop、public、常用

```java
drop		//丢弃。任何传入的网络数据包都被丢弃，没有回复。只能进行传出网络连接。

block		//阻止。任何传入的网络连接都被拒绝，其中包含用于IPv4的icmp-host-prohibited消息和用于IPv6的icmp6-adm-prohibited。只能从系统内启动网络连接

public		//公共（默认）。用于公共场所。

external		//外部网络。用于特别为路由器启用伪装的外部网络。

work 		//工作。用于工作区域

home		//家庭。适用于家庭领域

internal			//内部。用于内部网络

trusted			//受信任。接受所有网络连接。将接口连接添加到NetworkManager时，会将它们分配给默认区域。安装时，firewalld中的默认区域将设置为公共区域
```

#### 1、配置firewalld-cmd

##### 运行firewalld-cmd --list-all查看基础配置信息：

```java
[root@yyb ~]# firewall-cmd --list-all
public (active)			//表示public区域是默认区域（当接口启动时会自动默认），并且他是活动的。		
  target: default
  icmp-block-inversion: no	//是否拒绝icmp
  interfaces: ens33		//列出了这个区域上关联的接口。
  sources: 			//列出了这个区域的源。格式xxx.xxx.xxx.xxx/xx。
  services: dhcpv6-client ssh		//列出了允许通过这个防火墙的服务。
  ports: 			//列出了一个允许通过这个防火墙的目标端口。
  protocols: 
  masquerade: no		//表示这个区域是否允许IP伪装。如果允许，它将允许IP转发
  forward-ports: 		//列出转发的端口
  source-ports: 		
  icmp-blocks: 		//阻塞的icmp流量的黑名单
  rich rules: 		//在一个区域中优先处理的高级配置
default		//是目标区域，它决定了与该区域匹配而没有由上面设置中显示处理的包的动作。
```

```java
firewall-cmd --get-services得到一个防火墙预定义服务的详细列表
```

##### 运行一下命令理解firewall规则用法：

```java
firewall-cmd --zone=public --list-port			//查看所有打开的端口
firewall-cmd --reload					//更新防火墙规则
firewall-cmd --get-zones				//列出所有区域
firewall-cmd --get-active-zones				//查看区域信息
firewall-cmd --set-default-zone=public		//设定默认区域，立即生效
firewall-cmd --get-zone-of-interface=ens33				//查看指定接口所属区域
firewall-cmd --list-all			//查看所有规则
```

##### 永久修改

```
firewall-cmd --permanent <some modification>
firewall-cmd --reload
```

```
firewall-cmd --add-service=http --permanent
firewall-cmd --reload
```

#### 2、常见使用场景

```java
firewall-cmd --panic-on			//拒绝所有包
firewall-cmd --panic-off			//取消拒绝状态
firewall-cmd --query-panic			//查看是否拒绝
```

```java
firewall-cmd --add-service=ftp				//暂时开放ftp服务
firewall-cmd --add-service=ftp --permanent			//永久开放ftp服务
firewall-cmd --query-service=ftp			//查询服务开启状态
firewall-cmd --remove-service=http			//阻止http服务
firewall-cmd --list-services			//查看开放的服务
cd /usr/lib/firewalld/services				//查看对应规则库文件	
```

```java
firewall-cmd --add-port=3306/tcp			//开放通过tcp访问3306
firewall-cmd --remove-port=3306/tcp			//阻止通过tcp访问3306

firewall-cmd --zone=public --query-port=80/tcp			//查看80端口
firewall-cmd --zone=public --list-ports				//查看所有开放端口

firewall-cmd --zone=public --add-port=80/tcp --permanent			//永久开放80端口
firewall-cmd --zone=public --remove-port=80/tcp --permanent			//删除80端口
```

**允许http服务通过1分钟**

```java
firewall-cmd --zone=public --add-service=http --timeout=1m
//timeout选项	s秒、m分、h小时为单位
```

- 重载防火墙

  ```
  firewall-cmd --reload
  ```

- 检查防火墙状态

  ```
  firewall-cmd --state
  ```

- 让设定生效

  ```
  systemctl restart firewalld
  ```

- 检查设定是否生效

  ```
  iptables -L -n | hrep 21
  firewall-cmd --list-all
  ```

- 查看当前活动区域

```
firewall-cmd --get-active-zone
```

- 获取到所有的区域

  ```
  firewall-cmd --get-zones
  ```

#### 3、富规则

**与iptables一致，富规则中的动作可以设置为：accept、drop、reject（小写）**

- **添加指定ip访问端口规则：**

  ```
  firewall-cmd --permanent -add-rich-rule 'rule family=ipv4 source address="192.168.184.1" port protocol="tcp" port=80 accept'
  ```

- **删除指定某个IP访问特定端口规则**

  ```
  firewall-cmd --remove-rich-rule 'rule family=ipv4 source address="192.168.184.1" port protocol="tcp" port="80" accept'
  ```

- 允许ping

  ```
  firewall-cmd --add-rich-rule='rule family="ipv4" protocol value="icmp" source address="192.168.184.1" accept'
  ```

- 端口转发

  ```
  iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8080
  ```

- 接受192.168.184.0网段所有的IP访问SSH服务

  ```
  firewall-cmd --add-rich-rule='rule family=ipv4 source address="192.168.184.0/24" service name=ssh accept'
  ```

- **直接模式**(使用iptables语法)

  ```java
  firewall-cmd --direct --add-rule ipv4 filter INPUT 1 -p tcp --dport 80 -s 192.168.184.1 -j ACCEPT
  //INPUT后的数字 1 代表规则的优先级，数字越小优先级越高
  firewall-cmd --direct --get-all-rules		//查看直接模式下的规则
  firewall-cmd --direct --remove-rule ipv4 filter INPUT 1 -p tcp --dport 80 -s 192.168.184.1 -j ACCEPT
  ```

#### 4、端口转发

**注意问题**

- 比如我将80端口转发至8080端口，首先检查本地80和8080端口是否开放监听
- 其次检查是否允许伪装IP，没有的话要开启

```java
//将8888端口的流量转发至80
firewall-cmd --add-forward-port=port=8888:proto=tcp:toport=80
firewall-cmd --remove-forward-port=port=8888:proto=tcp:toport=80    
```

- 开启伪装IP

  ```
  firewall-cmd --add-masquerade
  ```

- 关闭伪装IP

  ```
  firewall-cmd --remove-masquerade
  ```

  ****

### 三、扩展

**在linux中，配置文件通常是在/etc/目录下；日志文件一般在/var/log目录下**

可以使用`find /etc/ -name "*frewall*"`查找配置文件

## Shell环境和变量

### 一、Shell基础用法

#### 1、Shell的类型

| 命令         | 作用r                                                        |
| ------------ | ------------------------------------------------------------ |
| Bourne Shell | 是贝尔实验室开发的，Unix普遍使用的Shell，在编程方面比较优秀，但在用户交互方面没有其他Shell优秀 |
| Korn Shell   | 是对Bourne Shell的发展，在大部分内容上与Bourne Shell兼容，集成了C Shell和Bourne Shell的优点 |
| C Shell      | 是SUN公司Shell的BSD版本，语法与c语言相似，比bourne shell更适合编程 |
| BASH         | 是GUN的Bourne Again Shell，是GUN操作系统默认的Shell，在Bourne Shell基础上增加了很多特性，如命令补全、命令历史表 |

#### 2、Shell操作

| 命令             | 作业                                |
| ---------------- | :---------------------------------- |
| cat /etc/shells  | 列出系统中所有的Shell               |
| ksh/csh/zsn/basn | 切换到其他Shell                     |
| chsh yang        | 使用命令chsh更改用户yang的默认Shell |
| cat /etc/passwd  | 查看用户使用的默认Shell             |
| echo &SHELL      | 查看当前环境变量&SHELL的值          |

#### 3、Bash基本操作

| 命令                           | 作用                                            |
| ------------------------------ | ----------------------------------------------- |
| TAB键                          | 命令补全                                        |
| history                        | 命令的历史记录                                  |
| alias gohome="shutdown -h now" | 命令别名功能(给关机起gohome),来执行一些复杂命令 |
| crontab                        | 作业控制功能                                    |
| shell脚本编程                  | 非常灵活的脚本编程能力                          |
| ls;cat /etc/passwd;mount       | 三个命令放在一起通过；分隔，一次性执行完        |

#### 4、echo命令

| 命令                   | 作用                                            |
| ---------------------- | ----------------------------------------------- |
| echo "HelloWorld"      | 在屏幕输出HelloWorld                            |
| echo "Hello\nWorld"    | 在屏幕输出Hello\nWorld                          |
| echo -e "Hello\nWorld" | 在屏幕输出Hello <br />                    World |
| \a                     | 蜂鸣                                            |
| \b                     | 退格，覆盖前一个字符                            |
| \c                     | 不带换行符打印一行                              |
| \f                     | 换页                                            |
| \n                     | 换行                                            |
| \r                     | 回车                                            |
| \t                     | 制表符                                          |
| \v                     | 纵向制表符                                      |
| \\\                    | 反斜杠                                          |
| \0nnn                  | ASCII码是nnn（八进制）的字符                    |

#### 5、环境变量

| 命令                | 作用                                                         |
| ------------------- | ------------------------------------------------------------ |
| set                 | 显示当前shell的变量，包括当前用户的变量                      |
| env                 | 显示当前用户的变量                                           |
| export              | 显示当前导出成用户变量的shell变量                            |
| cat /etc/profile    | 全局的环境变量，对任何用户生效，开机自动启动                 |
| cat ~/.bash_profile | 用户主目录下的环境变量，仅对当前用户生效（本地变量定义在此） |
| export NAME=yang    | 定义一个NAME环境变量并且赋值为yang                           |
| echo $NAME          | 输出环境变量的值                                             |
| unset NAME          | 删除环境变量                                                 |
| echo $USER          | 当前登录的用户名                                             |
| echo $UID           | 当前登录的用户ID号                                           |
| echo $SHELL         | 当前所使用的SHELL                                            |
| echo $HOME          | 当前用户的主目录                                             |
| echo $PWD           | 当前命令行所在的目录                                         |
| echo $PATH          | 当前可执行程序的路径（设定了PATH，执行命令就不需要输入命令的绝对路径） |
| echo $PS1           | 命令的提示字符串（重启会失效，如想永久生效，则保存到profile） |
| echo $PS2           | 命令一行未写完时换行提示符                                   |

#### 6、普通变量

| 命令                                              | 作用                                         |
| ------------------------------------------------- | -------------------------------------------- |
| read NAME       Bill Gates                        | 从终端将值读入并赋值给变量NAME               |
| read  NAME SURNAME     Bill Gates                 | 此时会将BIll赋值给NAME，而Gates赋值给SURNAME |
| NAME=yang echo $NAME                              | 在命令行定义变量NAME并取得其值               |
| SOURCE=/etc/passwd DEST=/opt/<br />cp SOURCE DEST | 利用变量代替对应值进行操作                   |
| NAME=yang <br />readonly NAME                     | 设置只读变量，此时变量的值不能修改           |

#### 7、管道及重定向

| 命令                            | 作用                                                         |
| ------------------------------- | ------------------------------------------------------------ |
| set \| grep USER                | 从set的输出中查找包含USER的行                                |
| ls \| wc -l                     | 根据ls输出的行数来统计该文件夹下的文件数量                   |
| tail /etc/passwd >> passwd.txt  | 在文件passwd.txt后面累加                                     |
| cat < /etc/passwd               | 将/etc/passwd文件作为cat的输入                               |
| cat < /etc/passwd >passwd2.txt  | 将/etc/passwd文件作为cat的输入，并将输出结果重定向到passwd2.txt中 |
| ifconfig \| tee ifconfig.tee    | 将ficonfig的内容输出到屏幕同时重定向到ifconfig.tee中         |
| ifconfig \| tee -a ifconfig.tee | 以追加的方式输出到文件ifconfig.tee中                         |
| ifconfig 1> ifconfig.out        | 标准输出重定向到文件ifconfig.out中（报错的话不输入）         |
| ifconfig 2> ifconfig.error      | 标准错误重定向到文件ifconfig.error中（正确的不会输入，报错才会输入） |
| ls /opt/optt 1>cat.error 2>&1   | 标准输出和标准错误一起重定向到一个文件                       |
| ls /opt/optt 2> /dev/null       | 标准错误信息会输送到系统垃圾箱，不会输出到屏幕和任何地方     |
| ls /opt /oppp 2>ls.err 1>ls.out | 正确的输出和错误的输出分别重定向到不同的文件                 |
| 命令1 && 命令2                  | 命令1执行成功后才会执行命令2                                 |
| 命令1 \|\| 命令2                | 命令1执行失败后才会执行命令2                                 |
| tty                             | 查看当前终端设备编号                                         |

## Shell脚本基础应用

### 一、脚本运行

#### 1、最基础的脚本

```shell
#!/usr/bin/bash
#这是Shell的注释，用#开头
echo "Hello World"
echo "一共有 $# 个参数"
echo "参数一的值为：$1"
echo "参数二的值为: $2"
echo "参数九的值为: $9"
#在Shell中，最多只接受9个参数
```

#### 2、使用如下命令运行helloworld.sh

```java
. helloworld.sh
sh helloworld.sh
bash helloworld.sh				//最常用
source helloworld.sh		//最常用
chmod u+x helloworld.sh
./helloworld.sh
```

#### 3、引号的特殊用法

| 命令        | 作用                  |
| ----------- | --------------------- |
| echo "$1"   | 输出第一个参数的值    |
| echo '$1'   | 输出$1,变量不会被替换 |
| echo 'date' | 输出date              |

```shell
now=`date "+%Y-%m-%d %H:%M:%S"`		#使用``反引号，使它称为独立的代码
echo $now
-----------------------------
2022-02-11 16:33:20
```

完善脚本，明确提醒用户，如果输入错误参数，则给予及时帮助

```shell
#!/usr/bin/bash
#通过参数来决定对某个文件进行查找，并输出对相应的行数和行号，只接受一个参数
filename=$1
grep -n root $filename
```

### 二、特殊用法

#### 1、特殊变量

| 命令   | 作用                                                         |
| ------ | ------------------------------------------------------------ |
| **$#** | **传递到脚本的参数个数**                                     |
| $0     | 脚本的名称                                                   |
| $*     | 以一个单字符串的形式显示所有向脚本传递的参数，与位置变量不同，此项参数可超过9个 |
| $$     | 脚本运行的当前进程ID号                                       |
| $!     | 后台运行的最后一个进程的进程id号                             |
| $@     | 与$*相同，但是使用时加引号，并在引号中返回每个参数           |
| **$?** | **显示最后命令的退出状态，0表示正确，其他任何值表示错误     特别的：在脚本中可以自定义0~255的退出状态码** |
| $_     | 代表上一个命令的最后一个参数                                 |

**理解$@和$*的区别**

```shell
bash helloworld.sh 11 22 33 44 55 66 77 88

echo "使用 $ * 的结果为：$*"
echo "使用 $ @ 的结果为：$@"

上述脚本的结果为
使用 $ * 的结果为：11 22 33 44 55 66 77 88			#其结果是所有的参数构成一个字符串："11 22 33 44 55 66 77 88"
使用 $ @ 的结果为：11 22 33 44 55 66 77 88			#其结果是每一个参数单独加上引号："11" "22" "33" "44" "55" "66" "77" "88"
```

```shell
#通过函数+参数的方式进行验证
function testargs
{
	echo "There is $# args"
	echo $10
}
testargs "$*"
testargs "$@"
```

#### 2、expr表达式

| 命令                   | 作用                                             |
| ---------------------- | ------------------------------------------------ |
| expr 10 + 10           | expr作为一个手工计算器，此处会输出20（注意空格） |
| expr 10+10             | 输出10+10                                        |
| expr 10.1 + 10         | expr不能处理小数                                 |
| expr “hello” = “hello” | 成功返回1，失败返回0                             |
| 练习                   | 使用echo命令输出一句话：300/56=360               |

### 三、test命令

#### 1、test文件

| 命令                  | 作用                                             |
| --------------------- | ------------------------------------------------ |
| test -e   /etc/passwd | 测试passwd文件是否存在，存在$*则返回0，否则返回1 |
| [ -e /etc/passwd ]    | 与上条命令一样，注意空格                         |
| -d file               | 如果文件为一个目录，则为真                       |
| -e                    | 如果文件存在，则为真                             |
| -f                    | 如果一个文件为普通文件，则为真                   |
| -r                    | 如果文件为可读，则为真                           |
| -w                    | 如果文件为可写，则为真                           |
| -x                    | 如果文件可执行，则为真                           |
| -s                    | 如果文件的长度不为零，则为真                     |
| -L                    | 如果文件为符号文件，则为真                       |

#### 2、逻辑处理

| 命令                                 | 作用                         |
| ------------------------------------ | ---------------------------- |
| [ -e /etc/passwd -a -r /etc/passwd ] | 逻辑与，两边都为真，结果为真 |
| -o                                   | 逻辑或                       |
| [ ! -e /etc/passwd ]                 | 逻辑否                       |

#### 3、test字符串

| 命令                | 作用         |
| ------------------- | ------------ |
| [ $USER = "root"]   | 字符串比较   |
| [ “$USER” = "root"] | 建议用此方式 |
| =                   | 等于         |
| ！=                 | 不等于       |
| -z                  | 为空字符串   |
| -n                  | 非空字符串   |

#### 4、test数值

| 命令           | 作用                     |
| -------------- | ------------------------ |
| [ $$ -eq 1231] | 对数值的测试             |
| -eq            | 数值相等                 |
| -ne            | 数值不相等               |
| -le            | 第一个数小于等于第二个数 |
| -ge            | 第一个数大于等于第二个数 |
| -gt            | 第一个数大于第二个数     |
| -lt            | 第一个数小于第二个数     |

## 分支与循环语句

### 一、分支语句

```shell
if 或 elif #后面跟的条件，事实上是一条可执行程序，判断条件是该程序是否成功执行

if	条件
then
	命令
fi		#结束

#如果脚本的个数少于三个，则提示用户至少需要3个参数
#方式一
if [ $# -lt 3]
then
	echo "Sorry， it need 3 args"
fi
#方式二
if [ $# -lt 3]; then
then
	echo "Sorry， it need 3 args"
fi

if 条件; then
	命令1
else
	命令2
fi
```

- 提示用户输入他的账号，并显示欢迎信息。如果为空则提示：

  `echo "Please input your name："`

  ```shell
  read NAME
  if [ "$NAME" = "" ]; then
  	echo "Your name is null"
  else
  	echo "Welcome,$NAME"
  fi
  ```

- 多重分支语句

  ```shell
  if 条件1; then
  	命令1
  elif 条件2; then
  	命令2
  else
  	命令3
  fi
  ```

- 分支语句case

  ```shell
  $num=$1
  case $num in
  	1)
  		echo "Monday"
  		;;
  	2)
  		echo "Tuesday"
  		;;
  	3)
  		echo "Wednesday"
  		;;
  	4)
  		echo "Thursday"
  		;;
  	5)
  		echo "Friday"
  		;;
  	6)
  		echo "Saturday"
  		;;
  	7)
  		echo "Sunday"
  		；；
  	*) 
  		echo "erro"
  esac
  ```

- 求和

  ```shell
  #计算从1加到10的结果
  sun=0
  for i in 1 2 3 4 5 6 7 8 9 10; do
          sum=`expr $sum + $i`
  done
  echo "sum=$sum"
  ```

  ```shell
  sun=0
  for i in 1 2 3 4 5 6 7 8 9 10; do
          let sum=sum+i	// let sum+=i	// ((sum+=i))
  done
  echo "sum=$sum"
  ```

  ```shell
  for i in {1..100};		#范围简写
  for i in {1..100..1};		#默认的步长为1
  for ((i=1;i<=100;i+=1))
  ```

- while循环

  ```shell
  i=0
  while [ $i -lt 10 ]
  do	
  	i=`expr $i + 1`
  	if [ $i -eq 5 ];then
  		break
  	fi
  	echo $1
  done
  ```

## 函数与数组 

### 一、函数的定义与调用

#### 1、函数的调用

函数可以将一个专门的功能进行封装，用于解决一个特定的问题，并且可以通过传递不同的参数给某个函数，实现处理不同数据的能力。函数的参数跟脚本的参数比较类似。

#### 2、函数的使用

函数名、参数、返回结果，其中函数名必须的，参数和返回结果可选，根据需要进行处理。



```shell
function 函数名()			#建议使用这种方式
{ …… }

或

函数名()
{ 命令1 }
```

```shell
#定义一个函数
function add(){
	let sum=$1+$2
	echo $sum    
}

#调用add函数
result=`add 100 26`
等价于 result=$(add 100 200)
echo "结果为$result"
```

- 关于括号的几个特殊用法

  ```shell
  (())	双圆括号，用于运算，可代替expr,也可以用于for循环条件 for ((i=1;i<=100;i++))
  ${}		可以取特定参数或变量的值，比如${1},${username}
  $()		可以代替反引号执行圆括号中的命令
  $[]		用于整数运算，也可代替 expr
  ```

- 检查参数是否是一个目录

  ```shell
  function is_directory(){
  	if [ -d $1 ]; then	
  		echo "Great,$1 is a directory ..."
  	else 
  		echo "Sorry,$1 is not a dirctory ..."
  	fi
  }
  echo "check if the input is a directory ..."
  ```

### 二、数组

#### 1、定义数组的方式有两种

- 第一种

```shell
declare -a weekday
#给数组的每个元素赋值
weekday[1]=Monday
weekday[2]=Tuesday
weekday[3]=Wednesday
weekday[4]=Thursday
weekday[5]=Fridat
weekday[6]=Saturday
weekdat[7]=Sunday
#数组的取值
echo ${weekday[@]}			#输出所有数

for day in ${weekday[@]}; do		#遍历输出
	echo $day
done
echo ${weekday[3]}			#输出下标为3的元素
echo ${#weekday[@]}			#一共有多少个元素

let len=${#weekday[@]}-1
for i in {0..$len};do
	echo ${weekday[i]}
done
```

- **第二种（比较简便）**

```shell
weekday=(Monday Tuesday "Yang Yubo")
echo ${weekday[@]}
for i in ${weekday[@]}; do
	echo $i
done
```

- 使用`#`字符取整个数组有多少个元素如

  ```shell
  echo ${#weekday[@]}
  或者
  echo ${#weekday[*]}
  
  #获取单个数组元素的长度
  echo ${#weekday[3]}
  ```

- `unset`命令可以删除数组元素，甚至整个数组。

  ```shell
  unset weekday[1]	#删除weekday[1]的值
  unset weekday		#删除weekday所有的元素
  ```


## CronTab及定时任务

### 一、定时任务的基本原理

```shell
# 每5秒向文本中输出一次时间
for i in {1..10}; do
	date "+%Y-%m-%d %H:%M:%S" >> /opt/learn/date.txt
	date "+%Y-%m-%d %H:%M:%S"
	sleep 5
done
```

### 二、Cron定时任务

| 命令实例                            | 作用                                                         |
| ----------------------------------- | ------------------------------------------------------------ |
| crontab                             | 每个用户都可以有一个crontab文件来保存调度信息，通过该命令运行任意一个shell脚本或者命令 |
| /var/spool/cron                     | 保存所有用户的crontab文件                                    |
| /etc/cron.deny<br />/etc/cron.allow | 系统管理员可以通过cron.deny和cron.allow这两个文件夹来禁止或允许用户拥有自己的crontab文件（crontab.allow需要自己创建） |
| crontab的域                         | * * * * * command<br />第1列 分钟 0~50  第2列  小时 0~23（0表示子夜）第3列 日 1~31 第4列 月 1~12  第5列 星期0~6 （星期0代表周日）执行的用户名 第6列 要运行的命令 |
| 常用规则                            | *： 匹配任何值   */n：匹配每n个单位    1-9：匹配从1-9的值    1，2，3：匹配123 |
| crontab[ -u user ] -e -l -r         | -u：用户名   -e：编辑文件   -l  列出crontab文件中的内容   -r  删除crontab的值 |
| systemctl start crond               | 启动crond进程                                                |
| 不发送邮件                          | 在-e状态下编辑任务的时候，在第一行添加：MAILTO=""，则不会发送邮件 |
| 查看日志                            | 可通过/var/log/cron查看执行的日志                            |

**提示：编写定时任务时，确定好定时规则后，要执行的指令建议直接卸载Shell脚本中，让Cron直接执行脚本即可，尽量避免在定时规则文件中直接调用命令，比如**

```shell
*/1 * * * * /opt/learn/crondate.sh
```

**一定要保证Shell是有执行权限的，并且在Cron文件中指定的时绝对路径**

```shell
crontab -l		#查看当前系统有那些定时任务
crontab -e		#编辑定时任务
```

```shell
20 * * * * >> /opt/crontab.txt	#每小时的20分钟时执行一次，并重定向到/opt/crontab.txt
*/2 * * * * >> /opt/crontab.txt	#每2分钟时执行一次，并重定向到/opt/crontab.txt
20,25,30 * * * * >> /opt/crontab.txt	#每小时的20分钟,25分钟，30分钟时执行一次，并重定向到/opt/crontab.txt
20,25,30 5-8 * * * >> /opt/crontab.txt	#5点到8点的20分钟,25分钟，30分钟时执行一次，并重定向到/opt/crontab.txt
```

### 三、其他补充命令

| 命令实例            | 作用                                                         |
| ------------------- | ------------------------------------------------------------ |
| at                  | 单次定时任务。yum install -y at;   systemctl start atd;      |
| at  时间            | 指定某一特定时间去做某件事情                                 |
| at HH:MM            | at 16:00                                                     |
| at HH:MM YYYY-MM-DD | at 19:00 2022-09-16                                          |
| at now + 5 minutes  | 从现在开始5分钟后                                            |
| 退出at编辑模式      | Ctrl+D                                                       |
| atq                 | 查询现有任务                                                 |
| atrm id             | 删除某个任务                                                 |
|                     |                                                              |
| command &           | 后台运行，如果有输出，会输出到前台                           |
| nuhup command &     | 后台运行，所有输出将会转存到当前目录下的nuhup.out文件中,nohup输出是输出到屏幕的内容 |
|                     |                                                              |
| sleep n             | 让Shellp脚本暂停n秒，n秒运行一次                             |
| usleep n            | 让Shellp脚本暂停n纳秒，10的-9此方秒                          |
|                     |                                                              |
| time command        | 计算某一个命令或脚本运行所花的时间（精确到毫秒）：如time ls  ;time sh myshell.sh |



## 站点可用性监测

**利用Crontab来判断Web服务器是否可用，如果不可用，则自动启动，并且将过程的操作写入到日志文件中**

- 一个站点无法访问的原因可能有两个

  - Web服务器没有正常启动：如何使用Shell进行判断

    ```shell
    使用curl直接访问对应网页，如果成功 $? 为0，否则非零
    使用 netstat -ant | grep :80 进行查询，如果端口被打开，则 $? 为0，表示成功启动80端口
    也可用过 ps -ef  查询对应的进程
    ```

  - 防火墙没有允许80端口通过：让Shell执行firewall-cmd --add-port=80/tcp添加端口通过命令即可

    ```shell
    firewall-cmd --list-port | grep 80
    ```

**具体步骤**

😘编写脚本

```shell
curl http://192.168.184.138/dashboard/ > /dev/null
if [ $? -ne 0 ]; then
	/opt/lampp/lampp start
	echo "检测到lampp未启动，已自动完成启动 - "`date "+%Y-%m-%d %H:%M:%S"` >> /opt/learn/site_check.log
fi

firewall-cmd --list-port | grep 80
if [ $? -ne 0 ];then
	firewall-cmd --add-port=80/tcp
	echo "检测到80端口没有通过，已完成添加 - "`date "+%Y-%m-%d %H:%M:%S"` >> /opt/learn/site_check.log
fi
```

😘启动定时任务

```shell
crontab -e
* * * * * /opt/learn/site_check.sh
```

## 字符串处理及awk与sed

### 一、字符串处理

```shell
假设有变量 url="http://www.baidu.com/index.html"，以下用法及结果输出，/只是变量

*// 从左边开始删除第一个 // 号及左边的所有字符：
echo ${url#*//}		输出结果：www.baidu.com/index.html

##*/  表示从左边开始删除最后一个/号及左边的所有字符：
echo ${url##*/}		输出结果：index.html

%/* 表示从右边开始，删除第一个/号及右边的字符：
echo ${url%/*}		输出结果：http://www.baidu.com

%%/* 表示从右边开始，删除最后（最左边）一个/号及右边的字符：
echo ${url%%/*}		输出结果：http:
```

```shell
假设有变量：phone=“18222362661”，利用：进行字符串截取：
echo ${phone:0:5} 		#从第1个位置开始往后截取5个字符，输出为：18222
echo ${phone:6}			#从第7个位置开始往后知道结束，输出为：362661
echo ${phone:0-7:5}		#从右边第7个字符开始，截取5个，输出为：23626
echo ${phone:0-7}		#从右边第7个字符开始，直到结束，输出为：2362661
echo ${#phone}			#取得phone的字符数量，即字符串长度
```

### 二、AWK

对文本进行逐行处理的编程语言，awk是一种样式扫描与处理工具，但其功能却强于sed和grep

- 默认分隔符为  空格  ，可以使用-F指定分隔符

```shell
awk 选项 处理逻辑 文件或脚本		#如果要针对命令执行结果进行过滤，则必须使用管道

echo "Hello woniuxy welcome Shanxi" | awk '{print $2}'		#默认按照空格隔开，并输出第2列的内容： woniuxy

#从awk的处理视角看，任意一段文本，均可以按照行列（二维表）的形式进行理解
echo -e "Hello Woniuxy Welcome Shanxi\nA B C D" | awk '{print $2}'
-------------------------------------
Woniuxy
B

echo "http://www.baidu.com/index.html" | awk '{print $2}'   #无第2列
echo "http://www.baidu.com/index.html" | awk -F '.' '{print $2}'		#以.作为分隔符
-------------------------------------
baidu

echo "http://www.baidu.com/index.html" | awk -F '[./]' '{print $3}'		#同时以/和.作为分隔符
-------------------------------------
www


-F '[/.]'   #多个分隔符同时使用
```

- **通过 ping www.baidu.com -c 1结合awk或其他已经学过的知识，输出其ip地址**

```shell
ping -c 1 www.baidu.com | head -n 1 | awk -F '[ ()]' '{print $4}' 
------------------------------
180.101.49.11

ping -c 1 www.baidu.com | grep ^PING | awk -F [\(\)] '{print $2}'
------------------------------
180.101.49.12

ping -c 1 www.baidu.com | head -n 2 | tail -n 1 | awk -F [\(\)] '{print $2}'	#如果没有规则可以grep的情况下，则head 和tail联合使用
------------------------------
180.101.49.12
```

- **正则表达式格式 '$1~/格式/'.   1代表第几列**

```shell
#查找/etc/passwd下面第一个域为root的行并将其第一个域打印出来（-F：表示以冒号分割域）
awk -F ： '$1~/root/ {print $1}' /etc/passwd

#查找/etc/passwd中不包含root的行并统计一个有多少行
awk -F ： 'BEGIN {sum=0} $0!~/root/ {sum+=1} END {print sum}' /etc/passwd

#文件/etc/passwd中如果第一个域包含root则打印它，否则打印第三个域的值
awk -F : '{if ($1=="root") print $1; else print $3}' /etc/passwd

#打印文件中不包含bin或者root的行（特别的$0表示整行）
awk -F ： '$0!~/(bin|root)' /etc/passwd

#查找进程中包含yes的进程并打印出其cpu的使用率
top -d 1 | awk '$0~/yes/ {print $10}'shell

ps -aux|sort -k 3 -r|head -n 5|awk '{print "%-10s %-10s\n",$2,$3}'

cpu=`tcp -n 1 | grep "^%Cpu" | awk -F " " '{print int($8)}'`
```

### 三、sed

sed可依照脚本的指令来处理、编辑文件。

#### 1、sed的基本用法

##### 常用的三个选项：

- -e   指定脚本 或 进行多点编辑
- -n  显示处理后的结果
- -i    永久将编辑文件保存到指定文件中

##### 常用的6个动作：

- a：新增
- c：取代
- d：删除
- i：插入
- p：打印
- s：取代

```shell
head /ect/passwd > test.txt

sed '5a Hello' test.txt		#在第5行后面添加 Hello 的新行
sed '5i Hello' test.txt		#在第5行前面添加 Hello 的新行
sed '2d' test.txt			#删除第2行
sed '2,5d' test.txt			#删除第2行到第5行
sed '2,$d' test.txt			#删除第2行到最后
sed '2,5c Good' test.txt			#将第2行到第5行替换为Good
sed -n '/root/p' test.txt			#搜索包含root的行
sed  '/root/d' test.txt			#删除所有包含root的行
sed 's/要被取代的字串/新的字串/g'		#搜索并进行替换，支持正则表达式，其中g代表全局替换，可以不加，按行找第一个
sed -e '' -e '' -e ''			#多点编辑
sed -i '4a Hello' test.txt			#直接修改文件，永久生效
```

## 性能指标监控与通知

**系统的性能指标监控是比较常见的针对系统的管理场景，比如系统有挖矿程序，或者系统本身存在高CPU进程（正常应用），除了CPU之外，也可以监控内存、硬盘、网络流量等使用情况。通过监控和发送通知，可以及时对系统的运行情况进行把控进而实现正确的处置。如果发现某些异常CPU消耗，甚至可以直接结束到进程。**

- 通过相应的命令能够输出需要的指标。
- 通过awk对输出结果进行过滤，找到对应的值
- 根据对应的值进行判断，进而决定后续处理方式

### 一、使用yes程序监控CPU

- 获取总的CPU使用率并转化为整数用于后续判断

```SHELL
cpu=$(top -n 1 | grep ^%Cpu | awk '{print int($8)}')
或
cpu=$(top -n 1 | grep ^%Cpu | awk '{print int($8)}')
```

- 获取最消耗CPU的进程信息

```shell
ps -aux | sort -k 3 -r | head -n 2 | tail -n 1 
```

- 获取最消耗CPU的进程所消耗的CPU

```shell
ps -aux | sort -k 3 -r | head -n 2 | tail -n 1 |  awk '{print $3}'
```

- 获取最消耗CPU的进程所消耗的PID

```shell
ps -aux | sort -k 3 -r | head -n 2 | tail -n 1 |  awk '{print $2}'
```

- 获取真实的CPU消耗

```shell
cpu=`ps -aux | sort -k 3 -r | head -n 2 | tail -n 1 |  awk '{print int($3)}'`
echo $cpu / 2 | bc		#计算单核CPU的使用率，与总CPU使用率才有可比性
```

- 如何收集内存使用信息

```shell
top -n 1 | grep "^KiB Mem" | awk '{print $6}
#或者可以使用free采集
free | grep Mem | awk '{print $4}'
```

- 搜集硬盘使用信息

```shell
df -h | grep ^/dev/mapper
```

- 网络流量

```shell
ip -s link
```

**😁编写脚本**

```shell
cpu=$(top -n 1 | grep ^%Cpu | awk '{print int($8)}')
if [ $cpu -lt 50 ]; then
	echo "CPU is lower"
	pcpu=$(ps -aux | sort -k 3 -r | head -n 2 | tail -n 1 |  awk '{print int($3)}')
	ppcup=$(echo $pcpu / 2 | bc)
	pid=$(ps -aux | sort -k 3 -r | head -n 2 | tail -n 1 |  awk '{print int($2)}')
	echo "CPU is lower,$pid consume $ppcup% CPU" 
else
	echo "CPU is ok"
fi
```

### 二、发送邮件通知

#### 1、安装mailx邮件客户端

```shell
yum install -y mailx
```

#### 2、向本地系统用户发送邮件

**使用mail命令可以直接查看邮件，输入序号查看邮件正文，输入q退出，输入h回到邮件列表**

```shell
#确保postfix邮件发送服务启动
systemctl status postfix

#echo后面是内容，管道后面mail -s "标题" 用户
echo "Hello Boy" | mail -s "Test Email" root

#清空邮件
cp /dev/null /var/spool/mail/root
```

- 也可以使用输入重定向的方式发送文件

```shell
mail -s "Test Email" root < /etc/passwd
```

#### 3、向外部邮箱发送邮件

- 确定邮件账号的SMTP信息，可以使用QQ邮箱账号
- 编辑/etc/mail.rc ，将上述SMTP信息输入

```shell
set from=qqYikJiang-bs@163.com				#发件人的邮箱地址
set smtp=smtp.163.com								#邮件服务器
set smtp-auth-user=qqYikJiang-bs@163.com		#邮箱账号
set smtp-auth-password=ZOXHAITKPXDUKGYV			#授权码
set	smtp-auth=login			#认证方式通过密码登录
```

- 使用以下命令发送邮件

```shell
mail -s "HaHa" YikJiang-bs@qq.com < /etc/passwd
mail -s "HaHa" -a /opt/learn/1 YikJiang-bs@qq.com < /etc/passwd  #携带附件发送
```

### 三、使用sysbench

- 安装

```shell
curl -s https://packagecloud.io/install/repositories/akopytov/sysbench/script.rpm.sh | bash
yum install -y sysbench
```

- 执行

```shell
sysbench cpu run --threads=20 --time=100		#--threads代表线程数 --time代表持续时间单位s，
sysbench memory run --threads=20
```

## 敏感文件监控

### 一、敏感文件监控原理

判断一个文件是否被篡改，可以使用md5sum命令记录文件的md5的数字指纹。md5是一种摘要算法，是不可逆的加密，主要用于标识某个文件是否被篡改，或者用于保存密码。

`md5sum`