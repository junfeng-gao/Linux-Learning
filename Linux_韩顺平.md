### 网络连接的三种模式

桥接模式：虚拟系统可以和外界系统通讯，但容易造成IP冲突。

NAT模式：网络地址转换模式，虚拟系统可以和外界系统通讯，不会造成IP冲突，但外界系统不能向虚拟机通讯。

主机模式：独立系统，不与外界进行通讯。

### Linux目录结果

linux的文件系统采用级层式的树状目录结果，在此结构中的最上层是根目录 /，  在Linux世界中，一切皆文件。Linux中的目录结构是规划好的。Linux会把硬件映射为一个文件来管理

根/下有root、home、bin、etc、boot等目录。

具体的目录结构：

/bin：常用，是binary的缩写，这个目录存放着最常使用的命令。还有在/user/bin     、  /user/local/bin

/sbin：s是super user，这里存放的是系统管理员使用的系统管理程序。还有在/user/sbin  、/useri/local/sbin

/home：常用，粗放普通用户的主目录，在Linux中每一个用户都会有一个自己的目录，一般该目录名是用户的账号命名。

/root：常用，该目录为系统管理员，也成为超级权限者的用户主目录。一般用户进入不了

/lib：系统开机所需要的最基本的动态连接共享库，其作用类似与Windows的DLL文件，几乎所有的应用程序都会使用到这些共享库。

/lost+found：这个目录一般是空的，当系统非法关机后，这里会存放一些文件。

/etc：常用，所有的系统管理所需要的配置文件和子目录my.conf。比如安装了mysql数据库后的配置文件。

/usr：常用，非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似于windows下的program files目录。

/boot：常用，存放的是启动linux是使用的一些核心文件，包括一些连接文件以及镜像文件。

/proc：这是一个虚拟目录，它是系统内存的映射，访问这个目录来获取系统信息。不能动

/srv：service缩写，该目录存放一些服务启动之后需要提取的数据。不能动。

/sys：这是linux2.6内核的一个很大变化，该目录下安装了2.6内核中新出现的一个文件系统sysfs。不能动

/tmp：存放临时文件.

/dev:类似于windows的设备管理器,把所有硬件用文件的形式存储.

/media:常用,linux系统会自动识别到一些设备,如U盘,光驱等,当识别到后,linux系统会把识别到的设备挂在到这个目录下.

/mnt:常用,该目录是为了让用户临时挂载别的文件系统,我们可以将外部的存储挂载到/mnt/上,然后进入该目录就可以查看到里面的内容.

/opt:这是给主机额外安装软件所摆放的目录,如安装oracle数据库就可以放到该目录下,默认为空.

/user/local:常用,这是另一个给主机额外安装软件所安装的目录,一般都是通过编译源码方式安装的程序.

/var:常用,存放着不断扩充着的东西,习惯将经常修改的目录放到该目录下,包括各种日志文件.

/se'linux:security-enhanced linux,是一个安全子系统,他能控制程序智能访问特定的文件,有三种工作模式,可以自行设置.

### 远程登录到linux

原因:linux服务器是开发小组共享的,正式上线的项目是运行在公网的,程序员必须远程登录到linux服务器进行项目管理或开发.

远程登录客户端有Xshell6,Xftp6.

Xshell是目前最好的远程登录linux系统的软件,是一个强大的安全终端模拟软件,他支持ssh1,ssh2以及micros windows平台的telnet协议.

额外:ping ip操作:可以来判断两个设备间是否能够互通.

![image-20230330100904394](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330100904394.png)

Xshell远程登录linux系统:

![image-20230330101059507](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330101059507.png)

名称可以自己设置,但主机必须为所想要去连接的linux系统的ip.

双击所建的会话,弹出下图,一次性接收表示每一次连接到该会话是都需要重新输入用户和密码,在实际开发中可以选择接收并保存,以后连接到该会话就不用输入用户和密码.

![image-20230330101245981](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330101245981.png)

登录成功:

![image-20230330101617213](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330101617213.png)

远程上传下载文件Xftp ,是一个基于windows平台的SFTP,FTP我呢见传输软件,用户可以在windowsPC于linux之间传输文件.

新建会话:

![image-20230330103050052](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330103050052.png)

![image-20230330103259091](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330103259091.png)

额外:reboot命令:重启linux系统

### Vi和Vim

linux系统会内置vi文本编辑器,类似于txt.

vim具有程序编辑能力,可以看作为vi的增强版本,可以主动的一字体颜色辨别语法的正确性,方便程序设计.代码补全编译及错误跳转等方便编程.

vi和vim常用的三种模式:

1.正常模式:以vim打开一个文档就直接进入一般模式(这是默认模式).可以使用上下左右按键来移动光标,可以使用 删除字符 或删除整行 来处理文档内容,也可以使用复制  粘贴来处理文档数据.

2.插入模式:按下i  o  a  r大小写任意一个字母之后才会进入到编辑模式,常用按i.

3.命令行模式:可以提供你相关指令,完成读取\存盘\替换\离开vim\显示行号等动作. 先输入一个esc表示退出插入模式,再输入冒号:  进入命令行模式

![image-20230330104621560](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330104621560.png)

表示要使用vim去编写一个名叫hello的java程序文件.之后按i进入编辑模式,编写代码,

![image-20230330104842264](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330104842264.png)

编写完成后,先输入一个esc,再按冒号: 进入到命令行模式,输入 :wq表示保存该文件并退出(write quite)

若想要再次进入到该文件中,则再输入vim hello.java即可

![image-20230330105233253](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330105233253.png)

**vi和vim各个模式的切换:**

再命令行下输入 vim XXX 回车进入一般模式(正常模式),此时不能输入内容对文档进行编写, 输入i进入编辑模式, 按下esc退出编辑模式,回到了一般模式,从一般模式进入到命令模式需要按下冒号:或者/, 在命令行模式下输入情况有三种:wq(保存并退出)  :q(退出)  :q!(强制退出, 并且不保存).

vim快捷键:

1.拷贝操作是要在一般模式下进行的. 拷贝当前行: yy,拷贝当前行向下的5行:  5yy ,并粘贴,输入p(paste).

2.删除当前行 dd  ,删除当前行向下的5行  5dd.

3.在文件中查找某个单词:命令行模式下输入  /关键字 ,回车进行查找, 输入n查找下一个.  查询关键字后,查询高亮结果会出现一直保留的情况,此时在命令行模式下输入  :noh即可.

4.设置文件的行号,  取消文件的行:  命令行模式下输入   :set nu  和:set nonu

5.编辑/etc/profile文件 ,  在一般模式下,使用快捷键到该文档的最末行 G  和最首行 gg

6.在一个文件中输入"hello" 然后又想要撤销这个动作  u   需要在一般模式下

7.在编辑 /etc/profile文件 ,并将光标移动到  20行 : 在一般模式下输入 20 在输入shift+g

更多快捷建详见doc文档

### Linux实操_开机,重启和用户登录注销

基本介绍:

shutdown  -h  now 立即进行关机

shutdown  -h  1  会向正在操作linux的用户发送消息,将在1分钟后关机  若只输入shutdown则默认为1分钟后关机

shutdown  -r  now   立刻重新启动

halt  关机和上面的shutdown作用一样

reboot  现在立刻重新启动

sync  把内存的数据同步到磁盘

**注意细节**:不管是重启系统还是关闭系统,**首先要运行sync命令**,把内存中的数据写到磁盘中,防止数据丢失.

目前shutdown和reboot/halt等命令都已经在关机前进行了sync,但小心驶得万年船.

用户登录和注销:

基本介绍:登录时尽量少用root账号登录,因为他是系统管理员,最大的权限,避免操作失误.可以利用普通用户登录,登录后再用su - 用户名  命令来切换成系统管理员.    在提示符下输入logout即可注销用户.

使用细节:logout注销指令在图形运行级别无效,  在运行级别3下有效.  运行级别在后续介绍.

### 用户管理

linux系统是一个多用户多任务的操作系统,任何一个要使用系统资源的用户,都必须首先向系统管理员申请一个账号,然后以这个账号的身份进入系统.

添加用户:

基本语法: useradd  用户名    当创建用户成功后,会自动的创建和用户名同名的家目录,默认的家目录在/home/XXX, 也可以通过useradd -d  指定目录  新的用户名 ,给新创建的用户指定家目录.  当用新用户登录时,会自动切换到该家目录下.

指定/修改密码:基本语法:passwd  用户名   

额外补充:pwd指令显示当前用户所在哪个目录下

![image-20230330115728595](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330115728595.png)

删除用户:管理员权限,基本语法:userdel 用户名   有删除用户但保留家目录,则该用户就不能再登录了;  或者删除用户并且删除用户家目录 :userdel  -r  用户名.(此操作要谨慎,会把删除的用户所有数据都删除,  一般都会保留删除用户的家目录).

查询用户信息：基本语法：id  用户名   当用户不存在时，返回无此用户。

切换用户：在操作linux中，如果当前用户的权限不够，可以通过su - 指令，切换到高权限用户，如root。基本语法：su  -  用户名   说明：从高权限用户切换到地权限用户不需要输入密码，反之需要密码，当需要返回到原来用户时使用logout/exit指令。

![image-20230330124813991](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330124813991.png)

查看当前登录用户信息：基本语法whoami 或who am i查看更详细的信息。注意若登录之后又su - 指令切换到其他用户，则查询仍是最开始登录的用户。 

![image-20230330125002841](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330125002841.png)

用户组：类似于角色，系统可以对有共性/权限的多个用户进行统一的管理。

新增组：groupadd  组名      删除组：groupdel  组名    增加用户时直接加上组：useradd -g  用户组  用户名    在在创建用户时没有加组，则默认会创建一个同名的组并将该用户放入到该组中。

修改用户的组：指令：usermod  -g  用户组  用户名

![image-20230330125910057](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330125910057.png)

用户和组相关的文件：

/etc/passwd文件：用户的配置文件，记录用户的各种信息，每行的含义为用户名：口令：用户标识符：组标识符：注释性描述：主目录：登录Shell

/etc/shadow文件：口令配置文件，每行的含义为登录名：加密口令：最后一次修改时间：最小时间间隔：最大时间间隔：警告时间：不活动时间：失效时间：标志

/etc/group文件：组group的配置文件，记录linux包含的组的信息，每行含义为组名：口令：组标识号：组内用户列表

### Linux实操_实用指令

指定运行级别：

基本介绍：运行级别说明：0关机   1单用户(找回丢失密码)   2多用户状态没有网络服务    3多用户状态有网络服务  4系统未使用保留给用户   5图形界面   6 系统重启   常用运行级别是3和5  也可以指定默认运行级别，后面演示。

通过 init  级别数字   来切换不同的运行级别。使用systemctl get-default查看当前运行的级别。systemctl set-default 用户级别  来设置默认的运行级别。在工作中一般不使用图形化界面即不用5级别 

如systemctl set-default multi-user.target 将切换到3级别，不会有图形化界面，若要切换会图形界面，则设为graphical.target级别。

**找回root密码**：1.首先，启动系统，进入开机系统，动作快一点，在界面中按e进入编辑界面，2.进入编辑界面，使用键盘移动往下移动光标，找到linux16 开头内容所在行，在行的最后面输入init=/bin/sh    3.输入完成后，按下ctrl+x进入单用户模式    4.在光标闪烁位置中输入mount -o remount ,rw /    完成后按下回车。   5.在新的一行最后面输入passwd，完成后回车，输入密码，然后再次确定密码即可（密码长度最好在8位以上，但不是强制的），密码修改成功后，会显示passwd....样式，说明密码修改成功。  6.接着，在光标闪烁位置最后输入touch /.autorelabel   之后回车。  7.继续在光标处输入exec  /sbin/init  再回车，等待系统自动修改密码，此过程时间可能会长，请等待，完成后系统将自动重启，新密码就会生效。     若知道当前root密码想要修改一下，则直接在终端中输入 passwd  root进行修改即可。

帮助指令：

man获取帮助信息，基本语法：man  [命令或配置文件]（功能描述：获取帮助信息）。在linux下，隐藏文件是以 . 开头的  ，命令ls可以显示出当前目录下所有非隐藏的文件信息，ls -a 命令可以展示出所有隐藏文件。  选项可以组合使用：ls  -al  展示当前目录下所有的内容，以当行形式进行展示（-l）。

help指令：基本语法：help 命令  （功能描述：获取shell内置命令的版主信息）。    也可以直接百度。

**文件目录类：**

pwd指令： 展示当前工作目录的绝对路径。  

ls指令：基本语法：ls  [选项]  [目录或文件]   常用选项：-a显示当前目录所有的文件和目录，包括隐藏的 。    -l以列表的方式展示信息。

![image-20230330155313137](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330155313137.png)

cd指令：基本语法  [参数]     功能切换到指定目录    cd  ~ 或则  cd  :回到自己的家目录，比如你是root，则到/root

cd .. 回到当前目录的上一级目录。

mkdir指令：用于创建目录，基本语法：mkdir  [选项]  要创建的目录      常用选项-p 创建多级目录。mkdir  -p /home/animal/dog

rmdir指令：用于删除空目录，基本语法rmdir [选项]  要删除的空目标     使用细节：rmdir删除的空目标，如果目录下有内容则无法删除。若需要删除非空目录，需要使用指令   rm -rf  要删除的目录   进行强制删除，需要谨慎

 touch命令：创建空文件，基本语法：touch 文件名称

cp指令：拷贝文件到指定目录。基本语法：cp [选项]  suorce  dest    常用选项-r 递归复制整个文件夹

![image-20230330161315675](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330161315675.png)

rm指令：移除文件或目录。基本语法rm [选项]  要删除的文件或目录    常用选项 -r递归删除整个文件夹 -f强制删除不提示。必须带有-r 选项 否则无法删除。

![image-20230330161854443](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330161854443.png)

mv指令：移动文件与目录或重命名。基本语法：mv  oldName  newName  进行重命名  mv suorcepath destpath  进行移动文件

cat命令：查看文件内容，不能修改，所以建议对一些无需修改的重要文件使用cat进行查看。 基本语法：cat [选项]  要查看的文件  常用选项-n显示行号。 为了浏览方便，一般还会带上管道命令 | more  （管道命令即将前面得到的结果交给下一个命令） 如cat -n /etc/profile | more

more指令：是一个基于vi编辑器的文本过滤器，它以全屏幕的方式按页显示文本文件的内容，more指令中内置了若干快捷键(交互的指令) .  空格建向下翻一页   回车向下翻一行    q立刻离开more，不再显示该文件内容   ctrl+F向下滚动一屏    ctrl+B向上滚动一屏   =输出当前行的行号   :f输出文件名和当前行的行号。       基本语法  more 要查看的文件 

less指令：用来分屏查看文件内容，它的功能与more指令类似，但更加强大，支持各种显示终端，less指令在显示文件内容是，并不是一次将整个文件加载完成后才显示，而是根据显示需要加载内容，对于显示大型文件具有较高的效率。  操作说明：空格键向下翻一页    pagedown向下翻一页    pageup向上翻一页    /字符串:向下搜索该字符串；n向下查找  N向上查找        ?字符串:向上搜索字符串，n向上查找，N向下查找       q离开less查询。   基本语法：less  要查看的文件

echo指令：输出内容到控制台。基本语法echo [选项] [输出内容]

![image-20230330164510645](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330164510645.png)

head指令：用于显示文件的开头部分内容，默认情况下head指令显示文件的前10行内容。基本语法head 文件    head  -n  5 文件  查看文件投5行内容。

tail指令：输出文件中尾部的内容，默认情况下显示最后10行

'        >指令和>>指令:       >输出重定向(会覆盖原来的内容)和>>追加   基本语法ls -l >文件(原本输出的列表信息内容写入到a.txt文件中,覆盖写)    ls -al >>文件(将列表的内容追加到文件a.txt的末尾)    cat 文件1 > 文件2(将文件1的内容覆盖到文件2)   echo "内容" >> 文件  (将输出的文件内容,写入到该文件中.)          

**ln指令**:软链接也称位符号链接,类似于windows里的**快捷方式,**主要存放了链接其他文件的路径 .基本语法 ln -s 源文件目录  软链接名 (功能给源文件创建一个软链接).

![image-20230330170604108](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330170604108.png)

history指令:查看已经执行过历史命令,也可以执行历史命令. 基本语法history    history  10 查看最近的10条指令    !5去执行历史编号位5的指令

![image-20230330170948116](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330170948116.png)

**时间日期类:**

date指令:显示当前日期,基本语法date(显示当前时间)   date +%Y显示当前年份    date +%m显示当前月份   date +%d显示当前哪一天.       date "+%Y-%mm-%d %H:%M:%S"显示年月日时分秒

date指令设置日期:date  -s 字符串时间    如:date  -s "2023-04-01 09:09:56"就设置了系统当前时间

cal指令:查看日历指令.基本语法cal  [选项]  不加选项则显示本月日历.   显示整年日历cal 2023

![image-20230330172007117](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330172007117.png)

**搜索查找类**

find指令:将从指定目录下向下递归遍历其各个子目录,将满足条件的文件或者目录显示在终端.基本语法find  [搜索范围]  [选项]    选项说明-name 文件名 :(按照指定的文件名查找模式查找文件)   -user 用户名 : 查找属于指定用户名所有文件     -size 文件大小 :按照指定的文件大小查找文件.  +n大于  -n小于   n等于 

grep指令和管道符号 |:  grep过滤查找 ,管道符号 | ,表示将前一个命令的处理结果输出传递给后面的命令处理.  基本语法 grep [选项]  查找内容  源文件    常用选项-n 显示匹配行及行号   -i忽略大小写.

**压缩和解压类**

gzip和gunzip指令:前者用于压缩文件,后者用于解压. 基本语法gzip 文件  只能将文件压缩为.gz文件   gunzip 文件.gz

![image-20230330180216199](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330180216199.png)

zip和unzip指令:前者用于压缩文件和目录,或者解压,这个指令在项目打包发布中很有用.   基本语法  zip [选项]  XXX.zip  将要压缩的内容          unzip  [选项]   xxx.zip    常用选项-r 递归压缩,即压缩目录  -d 目录  指定解压后文件存放的目录  

tar指令:最后打包后的文件是.tar.gz文件  .基本语法tar  [选项]  XXX.tar.gz 要打包的内容     选项说明:-c产生.tar打包文件     -v显示详细信息    -f指定压缩后的文件名   -z打包同时压缩    -x解包.tar文件(没有untar,通过此选项来实现解压)

### Linux实操_组管理和权限管理

在linux中每个用户必须属于一个组,不能独立于组之外.在linux中每个文件都有 所有者,所在组,其他组的概念.

**文件/目录 所有者:**

一般文件的创建者,谁创建了该文件,就i是该文件的所有者. 查看文件的所有者指令ls -ahl    修改文件所有者chown  用户名  文件名

![image-20230330183519600](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330183519600.png)

**组的创建:**

基本指令:groupadd  组名    

![image-20230330183651518](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330183651518.png)

当用户创建一个文件后,这个文件的所在组就是该用户所在组. 查看文件/目录所在组ls -ahl   修改文件所在组chgrp  组名  文件名

除文件的所有者和所在组的用户外,系统的其他用户都是文件的其他组. 

改变用户所在组: 在添加用户时,可以指定该用户添加到哪个组中,同样的用root的管理权限可以改变某个用户所在的组. 改变用户所在的组usermod -g  组名  用户名         usermod  -d 目录名  用户名  这个命令可以改变该用户登录的初始目录.说明:用户需要有进入到新目录的权限.

![image-20230330184621326](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230330184621326.png)

**权限的基本介绍**

输入命令ls -l指令或 ll指令 后出现各个文件的详细信息：

![image-20230403155855303](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403155855303.png)

每行表示一个文件或文件夹的信息，具体信息解释：（从第0位开始）

0--9位说明：

​	第0位确定文件类型，有：l 是链接，相当于windows中的快捷方式；d 是目录，相当于文件夹；c 是字符设备，鼠标，键盘；b 是块设备，如硬盘。- 代表是一个普通文件。

​	第1--3位确定所有者user(该文件的所有者)拥有该文件的权限 。rwx权限详解： rwx作用到文件上时：r代表可读取查看；w代表可以修改，但不代表可以删除该文件，删除一个文件的前提条件是对该文件所在的目录有写权限，才能删除该文件；x代表可执行，可以被执行。rwx作用到目录上时：r代表可以读取，ls查看目录的内容；w代表可以修改，对目录的创建、删除、重命名目录；x代表可以执行，可以进入该目录。     补充：若发现某个文件有可执行权限时，为绿色高亮显示。

​	第4--6位确定所属组group(同用户组的)拥有该文件的权限。依旧是rwx

​	第7--9位确定其他用户other拥有该文件的权限。依旧时rwx

上图中第一列root位该文件的所有者，第二列为root所在组的用户。

另外可以使用数字来表示权限：r = 4，w = 2， x = 1，因此rwx=7

其他说明：

​	第10位：若是文件，则表示硬链接数，为1；若是目录，则表示子目录数+文件数。

​	4096：表示文件大小（字节），如果是文件夹，显示4096字节

​	时间：最后修改日期。

​	var：文件名

**修改权限**

基本说明：通过指令chmod指令，可以修改文件或者目录的权限。

第一种方式：+   -   = 变更权限。

u：所有者，g所在组，o:其他人  a:所有人（u  g  o 的综合）  如：

1）chmod  u=rwx,g=rx,o=x  文件/目录名

2）chmod  o+w  文件/目录名      +代表加上权限

3）chmod  a-x  文件/目录名		-代表减去权限

![image-20230403163404766](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403163404766.png)

第二种方式：通过数字变更权限：r=4  w=2  x=1

chmod u=rwx,g=rx,o=x   文件/目录名  就相当于chmod 751 文件/目录名

**修改文件所有者：**

chown newowner  文件/目录   改变所有者

同时修改所有者和所在组chown newowner:newgroup  文件/目录  改变所有者和所在组

-R选项，如果时目录，则使其下所有子文件或目录递归生效。

如：将/home/test目录下所有文件和目录的所有者都修改成tom： chown -R tom /home/test

**修改文件所在组**

基本介绍：chgrp newgrp  文件/目录  改变所在组

如：将/home/kkk目录下所有文件和目录的所在组都修改为 shaolin： chgrp -R shaolin /home/kkk

**案例**

有警察和土匪两个组，jack jerry属于警察，，xh，xq属于土匪：

1）创建组：groupadd  police        groupadd bandit

2）创建用户：useradd -g police jack   useradd -g police jerry    useradd -g bandit xh     useradd -g bandit  xh

3）创建一个文件，自己可以读写，本组人可以读，其他人没有权限

​	首先jack登录，创建文件vim jack.txt      修改权限chmod 640  jack.txt

4）jack修改该文件，让其他组人可以读，本组人可以读写

​	chmod   o=r,g=rw  jack.txt

5）xh投靠警察police，看看是否能够读写.修改用户所在组需要用root修改。

​	usermod  -g police xh        xh不可以读写，因为此时，对于jack家目录，police组的其他成员还没有赋予读写权限，根本不能进去jack文件夹种；需要jack先修改对同组人读写jack家目录的权限。chmod r=rw jack，之后xh作为同组人才能读写jack.txt

**案例练习：**
1）创建两个组神仙sx和妖怪yg：groupadd sx    groupadd yg

2）建立四个用户唐僧，悟空，八戒，沙僧：

​	useradd ts                useradd wk              useradd bj           useradd  ss

3）为上面用户设置密码：

​	passwd ts            passwd  wk     passwd bj          passwd  ss

4）把悟空八戒放入妖怪组，唐僧，沙僧放入神仙组：

​	usermod  -g yg  wk       usermod -g yg bj       usermod -g  sx  ts        usermod  -g  sx  ss

5）用悟空建一个文件monkey.java，该文件输出i am monkey

​	首先用悟空登录 ，创建文件vim  monkey.java     写入内容

6）给八戒一个可以rw 的权限（因为悟空与八戒在同一组，所以悟空需要赋予该文件同组拥有读写权限）

​	chmod g=rw monkey.java

7）八戒修改monkey.java加入一句话 i am  big

​	目前八戒无法进入到wk的家目录wk中，即使八戒与悟空是同一组人，也无法进行到悟空的家目录种对monkey.java进行修改。所以需要wk先修改同组对自己家目录wk的读写权限：悟空登录账号然后：chmod  g=rw  wk，之后八戒即可进入到wk的家目录中的monkey.java文件进行读写，vim  monkey.java

8）唐僧 沙僧对该文件没有权限。

​	此时唐僧 沙僧根本无法进入到悟空的家目录wk中，便就没有对该文件的权限

9）把沙僧放入妖怪组。

​	usermod -g  yg  ss   （注：root用户去切换组，自己不能修改) ，  修改之后发现沙僧的所在组已经修改为了yg，但是仍然无法进入到悟空的家目录wk中，此时可以重新登录沙僧的账号即可或者后面会讲到环境遍历时有其他区方法。之后沙僧作为wk的同组人，同属于yg组，同时悟空对自己的家目录wk的同组人的读写权限也有，所以沙僧可以进行修改monkey.java

**对文件夹的rwx的细节讨论**

​	对文件夹的同一组权限只有x权限即可执行权限，则同一组用户可以进入到该文件夹中，即可以cd ，但无法查看该文件夹中有什么东西，如使用ls命令将显示权限不足。但此外若此时该文件夹中有一个文件的同一组权限是可读可写，则同组的人虽然无法查看该文件夹中有什么东西，但是若知道本人若知道有什么文件，则可以对该文件夹中的此文件进行读写操作。  总的来说：对文件的权限就是对该文件的  对文件夹的权限就是对该文件夹的。

​	对于文件夹的同一组权限的w权限，就是能否对该目录中的文件进行删除或者创建。

​	对于文件夹的同一组权限的r权限，表示可以ls，将文件夹中目录内容进行显示。

### Linux实操_定时任务调度

**crond任务调度**  crond是linux的一个后台程序，可以定时调度设置的任务

任务调度：指系统在某个时间执行的特定的命令或程序。任务调度分类：1.系统工作：有些重要的工作必须周而复始的执行，如病毒扫描等，2.个别用户工作：个别用户可能希望执行某些程序，比如对mysql的备份。

crontab进行定时任务的设置：

基本语法：crontab [选项]    常用选项-e 编辑crontab定时任务  -l查询crontab任务  -r删除当前用户所有的crontab任务

快速入门案例：

设置任务调度文件：/etc/crontab    设置个人任务调度。执行crontab -e命令 。接着输入任务到调度文件，如：※/1 ※ ※ ※ ※ls  -l  /etc/ > /tmp/to.txt 意思是每一个小时的每分钟执行这个命令，将etc文件以以列表形式转存到/tmp/下的to.txt文件中。  参数细节说明：第一个※表示一个小时中的第几分钟（0--59）；第2个※表示一天当中的第几个小时（0--23)；第三个※表示一个月当中的第几天（1--31）；第四个※表示一年当中的第几个月（1--12）；第五个※表示一周中的星期几（0--7 0和7都代表星期日）。上例中在第一个※后加了/1表示一个小时中的每一分钟。  注意：星期几和几号最好不要同时出现，因为他们定义的都是天，容易混乱

特殊符号说明：

​	※代表任何时间，比如第一个※代表一个小时中每一分钟都执行一次

​	，逗号表示不连续的时间，比如“ 0  8,12,16 * * *"命令代表每天的8点0分，12点0分，16点0分都执行一次命令

​	-代表连续的时间范围，如“0 5 * * 1-6”代表周一到周六的5点0分执行一遍

​	*/n代表每间隔多久执行一次，如“※/10 * * * *”代表每间隔10分钟执行一遍

**案例**

1）每隔一分钟就将当前日期信息追加到/tmp/mydate.txt文件中

​	*/1 * * * * date > >  /tmp/mydate.txt

2）每个一分钟将当前日期和日历都追加到/home/mycal中

​	方法1：在写两条crontab -e语句     */1 * * * * date >>  /home/mycal        */1 * * * *cal >>  /home/mycal

​	方法2：写一个shell脚本将上面两句命令写入，然后crontab定时调度执行shell脚本：

​		首先在/home/目录下创建一个my.sh脚本，写入两句语句，

![](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403190108039.png)

​		此时这个脚本并没有x可执行权限，所以root修改该脚本权限；之后crontab -e 设置定时任务：  */1 * * * * 		/home/my.sh

![image-20230403185525160](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403185525160.png)

3）每天凌晨2：00将mysql数据库testdb，备份到文件中，提示：指令为mysqldump -u root -p密码  数据库 >> /home/db.bak

​	法1：直接crontab -e添加调度任务，将此指令写入：0 2 * * *  mysqldump -u root  -ppasswd  testdb > /home/db.bak

​	法2：可以写一个脚本，调度此脚本

crontab -r 终止任务调度    crontab -l列出当前有哪些任务调度   service crond  restart  重启任务调度

**at定时任务**

基本介绍：

1.at命令是一次性定时计划任务，at的守护进程atd会以后台模式运行，检查作业队列来运行。

2.默认情况下，atd守护进程每60秒检查作业队列，有作业，会检查作业运行时间，如果时间与当前时间匹配，则运行此作业。

3.at命令是一次性定时计划任务，执行完一次后不再执行此任务了。

4.在使用at命令时，一定要保证atd进程启动，可以使用相关指令来查看：ps -ef来查看当前正在运行的进程有哪些。信息太多，可以进行过滤：ps -ef |grep atd 

![image-20230403191432748](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403191432748.png)

at命令格式： at [选项] [时间]                  按ctrl+D两次结束at命令的输入 

at命令的选项：

-m当指定的任务被完成后，将给用户发邮件，即使没有标准输出。   -I(这是大写i) atq的别名    -d   atrm的别名

-v显示任务将被执行的时间   -c打印任务的内容到标准输出。     -V显示版本信息。   -q<队列>  使用指定的队列

-f<文件> 从指定文件读入任务而不是从标准输入读入。 -t<时间参数> 以时间参数的形式提交要运行的任务

at指定时间的方法：

1.接受在当天的hh:mm式的时间指定，假设该时间已经过去，那么就放在第二天执行，如04:00

2.使用midnight（深夜），noon（中午），teatime（一般下午4点）等比较模糊的词语来指定时间

3.采用12小时制，即在时间后加上am或pm来说明，如12pm

4.指定命令执行的具体日期，指定格式为month day或mm/dd/yy（月/日/年）或dd.mm.yy，指定的日期必须跟在指定的时间后面。**如：04:00 2021-03-1**，直接精确指定时间

5.使用相对计时法。指定格式为now+count time-units，now就是当前时间，time-units是时间单位，这里能够是minutes，hours，days，weeks，count是时间的数量，几天，几小时。如：now + 5 minutes

6.直接使用today tomorrow 来指定完成命令的时间。

应用案例：

1）2天后的下午5点执行 /bin/ls  /home   即将home目录的内容list出来

​	终端命令输入at  5pm + 2 days回车后，输入指令/bin/ls  /home   最后按ctrl+D两次结束at输入

![image-20230403193539175](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403193539175.png)

通过atq命令来查看系统中没有执行的工作任务。

2）明天17点输出时间到指定文件内，如/root/date100.log

​	at 5pm tomorrow     回车  输入指令date  >  /root/date100.log

![image-20230403193912786](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403193912786.png)

3）2分钟后，输处时间到指定文件内

​	at now + 2 minutes  回车后  输入指令date   >  /root/date200.log

4）删除已经设置的任务：  atrm  编号

![image-20230403194308901](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403194308901.png)

at也可以执行一个脚本：at now + 2 minutes回车后输入执行脚本的代码，如：/root/my.sh即可

### Linux分区

原理介绍：

1.linux来说无论有几个分区，分给哪一个目录使用，它归根到底就只有一个根目录，一个独立且唯一的文件结构，linux中每个分区都是用来组成整个文件系统的一部分。

2.linux采用了一种叫做”载入“的处理方法，它的整个文件系统中包含了一整套的文件和目录，且将一个分区和一个目录练习起来，这时要载入的一个分区将使它的存储空间在一个目录下获得。

硬盘说明：

1.Linux硬盘分IDE硬盘和SCSI硬盘，目前基本上都是SCSI硬盘

2.对于IDE硬盘，驱动器标识符为”hdx~“ ,其中hd表明分区所在设备的类型，这里是指IDE硬盘了。x为盘号（a为基本盘，b为基本从盘  c为辅助主盘  d为辅助从盘），~代表分区，前4个分区采用数字1到4表示，他们是主分区或拓展分区，从5开始就是逻辑分区，如hda3表示为第一个IDE硬盘上的第三个主分区或拓展分区，hdb2表示第2个IDE硬盘上的第二个主分区或拓展分区。

3.对于SCIS硬盘，则标识为sdx~，是用sd来表示分区所在的设备的类型的，其余则和IDE硬盘的表示方法一样.

![image-20230403200149005](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403200149005.png)

![image-20230403200215631](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230403200215631.png)

mountpoint挂载点.

**磁盘情况查询**

查询系统整体磁盘使用情况：

基本语法： df  -h   当已用资源达到80%，就需要考虑对空间进行清理

![image-20230404161649716](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404161649716.png)

查询指定目录的磁盘占用情况：

基本语法：df  -h  /目录    若没有带后面具体的目录，则默认为当前目录 。  参数说明： -s指定目录占用大小汇总  -h带计量单位   -a含文件  --max-depth=1 来指定查询子目录的深度      -c列出明细的同时，增加汇总值

案例：查询/opt目录磁盘占用情况，深度为1  ： du  -h  -max--depth=1  /opt

![image-20230404162500172](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404162500172.png)

磁盘情况-工作实用指令：

1.统计/opt文件夹下文件的个数：ls  -l  /opt  | grep "^-" | wc -l

​	详细解释：ls -l展示此目录下所有文件详情，再利用管道符进行筛选，“^-”匹配以 - 开头的文件，（以d开头的为文件夹），wc -l统计出总数。

2.统计/opt文件夹下的目录的个数：  ls  -l  /opt  | grep "^d"  |  wc -l 

![image-20230404163144130](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404163144130.png)

3.统计/opt文件夹下文件的个数，包括子文件夹里的： ls  -lR  /opt | grep  "^-"  |wc -l

​	详细解释：加上一个-R即表示递归展示。  大写R

4.统计/opt文件夹下文件的个数，包括子文件夹里的： ls  -lR  /opt | grep  "^d"  |wc -l

![image-20230404163531820](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404163531820.png)

5.以树状显示目录结构： tree /目录名     （注意：如果没有tree命令，则用yum  install tree  安装之后再使用，保证网络条件）

![image-20230404163852990](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404163852990.png)



### Linux实操篇_网路配置

**linux网络配置原理图：**

linux中查看ip使用命令ifconfig    windows中是使用ipconfig指令查看    **ip地址要在同一个网段才能相互通讯**，前三个数相同属于同一个网段

![image-20230404165300437](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404165300437.png)

![image-20230404164550005](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404164550005.png)

查看windows中的VMware网络配置ipconfig：

![image-20230404165024042](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404165024042.png)

查看虚拟网络编辑器和修改ip地址：在vmare中可以查看虚拟网络编辑器中的信息，可以修改，如子网、NAT设置中的网关ip。

![image-20230404165726826](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404165726826.png)

![image-20230404165734524](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404165734524.png)

ping测试主机之间网络连通性：

基本语法：ping 目的机ip          测试当前服务器是否可以连接到目的主机    按ctrl+c终止ping

**linux网络环境配置**

第一种方法：自动获取：登陆后，通过界面来设置自动获取ip，特点：linux启动后会自动获取ip，避免ip冲突，缺点：每次自动获取的ip地址可能不一样，就不能做服务器。所以平时自己用机器时，可以自动获取，但在工作环境中，肯定是要固定ip地址的，不能自动获取。

![image-20230404172757105](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404172757105.png)

**第二种方式，指定ip**：直接修改配置文件来指定ip，并可以连接到外网(程序员推荐).

编辑vi  /etc/sysconfig/network-scripts/ifcfg-ens33           要求：将ip地址配置静态的，比如192.168.200.130

ifcfg-ens33文件说明：

![image-20230404173244440](C:\Users\GJF\AppData\Roaming\Typora\typora-user-images\image-20230404173244440.png)

bootproto=dhcp为自动分配的ip地址 ，将其修改为：static   然后给它指定ip地址，网关，域名解析器，如：IPADDR=192.168.200.130     GATEWAY=192.168.200.2   DNS1=192.168.200.2，然后保存文件。之后打开虚拟机的虚拟网络编辑器，修改vmnet8的子网ip为192.168.200.0，让其与linux处于统一网段中，再进行NAT设置，将网关设置为192.168.200.2  最后应用确定，输入service network restart 或reboot重启网络服务或重启系统。

**设置主机名和hosts映射：**

设置主机名：为了方便记忆，可以给linux系统设置主机名，也可以根据需要修改主机名。指令：hostname 查看主机名。修改文件在 /etc/hostname  指定。 修改后重启生效。

**设置host映射：思考：如何通过主机名能够找到某个linux系统。**

windows在c:/windows/system32/drivers/etc/hosts文件指定即可.例添加上：192.168.200.130  gjf23    之后就可以在windows系统中通过主机名ping  gjf23   的方式，ping通连接到linux系统

 linux中在etc/hosts文件指定。例如添加上：192.168.200.1  zhengjiuzhe-PC  之后就可以在linux中通过ping zhengjiuzhe-PC  的方式，连接到windows系统。

**主机名解析过程分析(Hosts、DNS)：**

Hosts是一个文本文件，用来记录IP和hostname(主机名）的映射关系。

DNS就是Domain Name System是域名系统，是互联网上作为域名和ip地址相互映射的一个分布式数据库。

例如：用户在浏览器地址输出www.baidu.com：

1）浏览器先检查浏览器缓存中有没有该域名解析ip地址，有就先调用这个ip完成解析；如果没有，检查操作系统DNS解析器缓存，如果有直接返回ip完成解析。这两个缓存，可以理解为本地解析器缓存。

2）一般来说，当电脑第一次成功访问某一网站后，在一定时间内，浏览器或操作系统会缓存它的ip地址(DNS解析记录)。如在cmd窗口输入ipconfig /displagdns可以查看DNS域名解析缓存。

3）如果本地解析器缓存没有找到对于的映射，检查系统中hosts文件中有没有配置对于的域名ip映射，如果有，则完成解析并返回ip

4）如果本地DNS解析器缓存和hosts文件中均没有找到对于ip映射，则到互联网上的域名服务DNS进行解析域。

5）若还没找到，则返回域名不存在

总结：浏览器缓存---本机操作系统DNS解析器缓存---本机hosts文件中---公网的本地域名服务器DNS进行解析

### **Linux实操_进程管理**

在linux中每一个执行的查询都称为一个进程，每一个进程都分配一个ID号（pid，进程号）。

每个进程都能以两种方式存在：前台和后台，所谓前台进程就是用户的屏幕上可以进行操作的，后台进程则是实际在操作，但由于屏幕上无法看到进程，通常使用后台方式执行。

一般系统的服务都是以后台进程的方式存在，而且都会常驻在系统中，直到关机才结束。

**显示系统执行的进程：**

基本介绍：ps命令是用来查看目前系统中，有哪些正在执行，以及他们的执行状况，可以不加任何参数。

ps显示的信息选项：user是用户名称；pid为进程识别号；%cpu是进程占用cpu的百分比；%mem是进程占用物理内存的百分比；vsz进程占用的虚拟内存大小(KB)；rss是进程占用的物理内存大小；tty是终端机号；time是此进程占用cpu时间；command是正在执行的命令或进程名。  stat是运行状态：S表示sleep休眠，s表示该进程是会话的先导进程，R表示运行状态，N表示进程拥有比普通优先级更低的优先级，D短暂等待，Z僵死进程(需要清除)，T被跟踪或被停止进程；     

ps  -a显示当前终端的所有进程信息       ps  -u以用户的格式显示进程信息      ps  -x显示后台进程运行的参数。

ps详解：1.指令：ps  -aux | grep xxx  ，比如我只想看看有没有sshd服务，sshd是ssh远程连接用到的守护进程。

应用实例：以全格式显示当前所有的进程，查看进程的父进程。

ps  -ef是以全格式显示当前所有的进程   -e显示所有进程   -f全格式

ps  -ef | grep xxx （用于显示某个进程）  

显示信息详解：UID是用户id，pid是进程id，ppid是该进程的父进程id。

**终止进程：**          

介绍：若是某个进程执行一般需要停止时，或是已消耗了很大的系统资源时，此时可以考虑停止此进程。使用kill命令完成此项任务。  若kill掉一个进程，则它的子进程也会被kill。

基本语法：kill  [选项]  进程号        或         killall 进程名（可以支持通配符。这在系统因负载过大而变得很慢时很有用）        常用选项 -9表示强迫进程立刻停止。

**查看进程树：**

基本语法：pstree  [选项]  可以更加直观的看进程信息    常用选项-p显示进程的pid，-u显示进程的所属用户。











