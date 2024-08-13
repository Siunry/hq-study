# shell命令

### ls命令

功能 :  显示当前路径下的内容

格式:

​			==ls 	or	ls + 参数==

ls 参数:

- -l :`ls -l`	:显示当前路径下文件的详细信息

  - `-lh`与`-l`相比更注重文件的大小(将文件大小转换为K,M单位)易于理解

- -a :`ls -a`显示当前路径下所有文件(包含隐藏文件)

  注意: linux中的隐藏文件全都是以`·` 开头的

- -i :`ls -i`显示文件的inode号 在一个文件系统下 inode号相同的文件是一个 (根目录存在多个文件系统 )

- -R :`ls -R`递归显示当前文件夹内的所有文件

##### 详细信息说明

​	`-rw-rw-r-- 1 linux linux 1231 10月27 14:45 client.c`

- `-` 文件的类型

bsp-lcd

|     字母     |                文件类型                |
| :----------: | :------------------------------------: |
|   b(block)   |               块设备文件               |
|  s(socket)   |       套接字文件(主要应用于网络)       |
|   p(pipe)    |        管道文件(进程间通讯使用)        |
|      -       |                普通文件                |
|   l(link)    | (小写L)链接文件(windows当中的快捷方式) |
|   c(char)    |              字符设备文件              |
| d(directory) |                目录文件                |



 -	`rwx`文件的权限

​	三组 rwx 分别对应   当前用户权限    组用户权限    其他权限     的权限

​	r 	读权限				二进制: 100(4)

​	w 	写权限		       二进制: 10(2)

​	x      可执行权限	  二进制:  01(1)

​    -		无权限		![image-20240722135812407](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240722135812407.png)

		- `1`  硬链接个数
		- `linux` 文件创建者
		- `linux` 文件创建所属组
		- 1231 文件大小
		- 10月27 14:45  时间戳
		- client.c 文件名

### clear命令

功能:

​		清空当前窗口的内容

快捷方式: ctrl + L

### cd命令

功能:

​		进入指定目录

格式:

​		`cd 相对路径/目录名称`

​		`cd 绝对路径/目录名称`

特殊使用:

​		`cd ./`   :切换到当前路径

​		`cd ../`  :切换到上一层目录

​		`cd ~`   :切换到用户的家目录

​		`cd/`	:切换到根目录

​		`cd -`    :切换到上一次所在的目录

### pwd命令

功能:

​		以绝对路径的形式显示当前所在位置

格式: `pwd`

### touch命令

功能:

​		创建一个普通文件

格式:

  - `touch + 文件名` (如果创建文件不存在,创建文件.如果创建文件已经存在 则更行时间戳)
  - `touch + 文件1 文件2 文件3 `(touch命令支持同时创建多个文件)

### mkdir命令

功能:创建出一个目录文件.如当前目录已经存在则会报错

格式:

		- `mkdir 文件名` 创建一个目录文件 (同一录下不可存在名称相同的目录文件)
		- `mkdir -p 文件1/文件2/文件3` (创建一个层级结构目录)

### rm命令

功能:

​		删除普通文件or 目录

格式:

- `rm 文件名`(删除文件)
- `rm 文件1 文件2 文件3`(支持同时删除多个文件)
- `rm -rf 目录名`(删除目录 也可以删除文件)
  - `*`表示任意个 任意字符
- `rm -rf * `删除目录内所有文件

### cp命令

功能:拷贝文件或者目录到指定的目录下

格式:

- `cp 路径  src(源文件)  目标路径`(拷贝文件)

  ​			eg:`cp ./info.c   ./DC24071`

- `cp 路径 src(源目录名称)  目标路径  -r`(拷贝文件夹)

​							eg:`cp ./info.c   ./DC24071  -r`

### mv命令

功能:

1. 剪切文件或者目录
2. 重命名

格式:

- `mv 路径 src(源文件或目录名称)   指定目录`
- `mv 文件或目录名称  新名称`

### cat命令

功能:

​		将文件的内容显示到终端中

格式:

1. 将文件的内容显示到终端中

- `cat fliename`	

2. 将文件的内容显示到终端中并==显示行号==(适用于看一下小型文件(配置文件))

- `cat -n filename`

### head命令

功能:

​		将文件的内容显示到终端中,默认显示==前==10行内容

使用方式:

1. 将文件的内容显示到终端中,默认显示前10行的内容
   - `head filename`
2. 将文件的内容显示到终端中,显示前n行的内容
   - `head -n filename`



### tail命令

功能

​		:将文件的内容显示到终端中,默认显示==倒数==10行内容

使用方式:

1. 将文件的内容显示到终端中,默认显示倒数10行的内容
   - `head filename`
2. 将文件的内容显示到终端中,显示倒数n行的内容
   - `head -n filename`

### echo命令

功能:

​		在终端中输出一个字符串

格式:`echo 要输出内容`

- 重定向符号 
  - ` >`以覆盖的形式重定向到一个文件中
    - `head -7 hello.txt> hello2.txt `
  - `>>`以追加的形式重定向到一个文件中

### 管道命令

功能:

​			前一条命令的输出,作为后一条命令的输入使用

格式:

- `code1 | code2`

eg:

- `head -7 hello.txt | tail -3 `

### wc命令

功能:

​		对文件进行统计: 行数  单词数 字符数

格式:

- `wc filename`

  - `-l`行数
  - ``-c`字符数
  - `-w`单词数

- eg:

- `wc code.txt`

  - 结果: 		10 		 30 		 141

    ​				行数	单词数	  字符数

### grep命令

功能:

​		在文件中搜索指定字符串的内容.一般情况下会配合 | (管道)进行使用

格式:

- `grep -ni str filename`

参数:

- `-n`显示出查找内容所在==行号==
- `-i`忽略大小写
- `-w`按单词精确查找
- `-R`递归查找
- `^string` 找到以string开头的行
- `string$` 找到以string结尾的行
- `^string$` 精确查找string所在位置

### find命令

功能:

​		按照文件名字(可以按照类型查找)查找文件所在位置

### cut命令

功能:

​		文件切割命令,切割文件中的字符串,按照指定的格式进行切割

参数:

- `-d`后面跟指定的切割内容
- `-f`裁剪的域

使用方式:

- 



### shutdown命令

1. 关机shutdown
   - 使用格式:
     - sudo  shutdown -h 15:30 : 指定时间进行关机, 将在15:30的时候进行关机
     - sudo  shutdown -h +60  :  60分钟之后进行关机.     
     - sudo  shutdown -h  now :  立即关机   
     - 统一使用 shutdown  -c 进行取消操作.

​		

### ln命令

#### 软链接

​	软链接类似于windows中的快捷方式

格式:

- `ln -s srcfile linkfile`

  - eg:

    - `ln -s code.c hello`

      //为code.c创建一个链接文件hello

  1. 软连接是一个全新的文件有独立的inode号,软连接里面存放的数据是创建软链接的时候使用的路径
     - 如果使用的是相对路径,则文件不可以动位置
     - 如果使用的是绝对路径,则文件可以动位置
  2. 对软连接文件里面的内容进行修改的时候. 会对源文件进行修改

#### 硬链接

​	硬链接:相当于为文件重新起了一个别名,可以通过别名找到这个文件.

使用方式:

- `ln  srcname filename`

  - eg:

    - `ln hello.c world.c`

      //为hello.c创建一个硬链接

注意:

1. 硬链接相当于给文件起别名,每创建一个硬链接,硬链接个数+1
2. 当硬链接个数不为1时,删除文件,硬链接个数-1;当硬链接个数为1时,删除之后才会真正删除.
3. 硬链接只能链接普通文件,不能链接目录文件.

### 管理用户命令

简介:

​		

#### adduser命令

向linux操作系统中操作系统中添加一个用户

- `sudo adduser username`添加一个username用户.
  - 新创建的用户是没有sudo权限的.
  - 添加 新用户sudo权限.
  - 在文件 /etc/sudoers中添加内容

#### deluser命令

- `sudo deluser username`

### 权限管理

#### chmod

##### 1.通过数字对权限进行修改

- `chmod +3个八进制数字`将文件修改指定权限
  - read  4
  - write 2
  - x        1
    - eg:
    - `chmod 0777 filename`

##### 2.通过+/-方式对用户权限进行操作

- `chmod` 用户 +/- 权限 filename
  - eg:
    - `chmod u-w file1`

如果文件所属人不是自己,则不能修改权限,除非是管理员用户.

#### chgrp命令

功能:

​		更改文件所属组

格式:

- `chgrp groupname filename `

#### chown命令

功能:

​		更改文件的所属人

格式:

- `chown username filename`
- 将文件的所属人修改为username

## 磁盘管理

简介:在Linux操作系统中,使用U盘的时候需要先插入到电脑中,然后在vmware窗口中选择连接到Linux.

#### fdisk命令

进行磁盘管理的命令.

`sudo fdisk -l`

#### df命令

查看磁盘的挂载情况

#### 取消挂载命令

umount

- 取消磁盘挂载.
  - `umount 磁盘挂载点`

#### 挂载命令

mount

- 将磁盘内容挂载到文件夹中.
  - `mount 挂载磁盘 挂载文件夹`

## 软件安装

linux提供两种安装软件的方式:==在线安装(apt-get)==       ==离线安装(dpkg)==

#### 离线安装(dpkg)

```
linux 软件包
	sl		-	  			5.02-1_					 amd64.      deb
   软件名	间隔符  版本号:主版本号 次版本号 修订版本号   主机架构		文件后缀													ubuntu软件包后缀都是.deb
   
   dpkg命令
   功能:ubuntu中离线管理安装包的工具. 
   		缺点:不会安装软件所需要的库(如果软件需要C++环境才可安装,)
   注意:在使用dpkg进行软件包安装管理,需要先拥有软件包		
```

#### 共享文件夹(三不管地带)

共享文件夹:Linux与windows都可以访问的文件夹.(仅仅用来进行双系统相互传输数据)

创建步骤:

1. 虚拟机-->设置-->选项-->共享文件夹-->总是启用
2. 先移除原有文件.
3. 添加路径

在Linux中的路径为:==/mnt/hgfs/share/==

### 软件离线安装

==sudo dpkg -i 软件包名称==

### 软件运行

- 直接输入软件包名. `filename`

- 查看软件的使用方式:`man + filename`

### 卸载软件

- 不完全卸载:
  - `sudo dpkg -r filename`

- 完全卸载:
  - `sudo dpkg -P filename`

### 查看安装信息

`sudo dpkg -l filename`

查看文件安装路径:`sudo dpkg -L filename`

## 在线安装

在线安装前提:网络连通.

1. 检测ubuntu是否连网
2. 在终端中输入 ping www.baidu.com

### 更新软件源

- 存放位置: `/etc/apt/source.list`里面存放了所有的软件源
- 1. 点击左下角所有程序按钮
  2. 点击软件更新器---->停止更新---->设置---->ubuntu软件---->勾选全部选项
  3. 在下载自中选择更新源链接
  4. 终端输入指令:`sudo apt-get update.`

### 在线安装/卸载软件

```
//apt-get 是一个软件包管理工具.
//注意:
		apt-get安装软件需要保证在联网情况下
		apt-get安装软件如果需要依赖,apt-get会自动安装依赖文件.		
```

1. 安装软件

   - `sudo apt-get install filename`
     - 从服务器下载软件安装包到系统中.(/var/cache/apt/archives/)并==直接安装==
   - `sudo apt-get download filename`
     - ==仅==从服务器下载软件安装包到系统中.(/var/cache/apt/archives/)
   - `sudo apt-get source filename`
     - 从服务器中下载文件的==源代码==

1. 卸载软件

   - `sudo apt-get rmove  filename` (没有卸载/var/cache/apt/archives/路径中的软件安装包)
   - `sudo apt-get clean `(在文件夹内执行,清楚本文件夹内全部软件安装包)

   

## Shell命令

### 压缩命令

- 简介:Linux有三种压缩方式,压缩是针对单独的文件进行操作的,不能对文件夹进行压缩.
  1. ==gzip==-->压缩后会生成 -->==.gz文件==
  2. ==bzip2== -->压缩后会生成 --> ==.bz2文件==
  3. ==xz== -->压缩后会生成 -->==.xz文件==



- 使用方式:
  1. ==gizp==
     - 压缩:`gizp filename`压缩文件并生成.gz的文件
     - 解压:`gunzip filename.gz`解压缩文件并生成文件
  2. ==bzip2==
     1. `bzip2 filename `压缩文件并生成.bz2的文件
     2. `bunzip2 filename.bz2`解压缩文件并生成文件
  3. ==xz==
     1. `xz`
        1. 压缩:`xz filename`压缩文件并生成.xz的文件
        2. 解压:`unxz filename.xz`解压缩文件并生成文件

三种压缩模式对比:

- gzip:速度快,压缩率低.
- bzip:压缩速度居中,压缩率居中
- ==xz:速度慢,压缩率高.(针对内存较大的文件)==

### 归档命令(tar命令)

- tar命令:

  - 将目录文件或者普通文件  归档生成普通文件()

  - `-c`  打包

  - `-x`  解包

  - `-v`  显示详细过程

  - `-f`  后面需要跟文件名

    _____

  - `-z`打包之后压缩文件并生成.gz的文件

  - `-j`打包压缩文件并生成.bz2的文件

  - `-J`打包压缩文件并生成.xz的文件

```
归档操作:
	tar -cvf name.tar file1 file2
	eg:
			tar -cvf code.tar hello.c test.c demo.c
			//将hello.c test.c demo.c三个文件归档生成一个code.tar文件
			//-c -v 参数位置可以互换,但是f一定放到最后.
			//-v可以省略.
			
解归档操作:
	tar -xvf name.tar
	eg:
			tar -xvf code.tar
			//将code.tar文件进行拆包操作
			
归档同时进行压缩
	tar -czvf filename.ttar.gz file1 file2
	eg:
			tar -cvf code.tar.gz hello.c test.c demo.c
			//将hello.c test.c demo.c三个文件归档生成一个code.tar.gz文件
			
后两种压缩方式同上!!!!!!!!!!!!!!!!

万能解归档 解压缩方式:
	tar -xvf 需要解归档的文件
	//文件会自动匹配格式解压缩方式.
```

# shell语言

## 简介

- 编译型语言(C/C++,Java)
- 解释型语言(shell/python)

### shell解释器

sh:贝尔实验室研发的解释器

csh:具备C语言的编程风格

ksh:在csh解释器的基础之上,添加了数组和函数

bash:兼备了chs与ksh的优点,在ubuntu上使用的解释器(/bin/bash)

### shell脚本

shell脚本是一个以.sh结尾的文件,文件中可以编写多条命令.以及配合简单的逻辑进行使用.

- 本质:shell命令的集合

### shell脚本编写



### shell脚本执行方式

1. ``./filename` 通过./脚本名的方式执行	脚本必须要有执行权限 可以通过 chmog修改权限

2. `bash fliename` 通过解释器进行执行,这种方式不需要可执行权限

3. `source filename`

   - 区别:

     ​		./shell filename 与 bash filename 都是在终端中打开子终端,让子终端去执行shell命令,在原本终端中显示.		source 脚本:直接在本终端中执行脚本.


## shell变量

### 简介

1. shell语言中变量是没有类型的,默认都是字符串类型
2. shell语言中的变量不需要提前声明,即拿即用
3. ==shell语言中变量中间不可以有空格==

### 变量输出

shell语言中,如果需要输出变量里面的内容:

​		echo $变量名		

​		==echo${变量名}==

## 位置变量

shell脚本中的位置变量类似于C语言中的main函数传参.

使用方式:

- bash 脚本名 参数1 参数2 参数3 参数4 ...

位置变量:

- $0: bash: 获取的是脚本名
- $1~9: 位置变量获取的每一个命令行参数 1~9个参数
- 超过10的话需要使用
  - ${10}: 第10个位置变量

特殊变量:

- `$#` 命令行参数个数
- `$@` / `$*` 所有命令行参数
- `$?` 获取上一个程序的执行结果

## 命令置换

简介:

​		当需要获取某个命令的结果的时候,就需要使用命令置换符 ``.

功能:

​		获取命令的执行结果.

- eg:
  - var=`ls -l`    #将"ls -l"的值赋值给 var变量 

## 环境变量

环境变量的查看:

​		env : 将Linux中所有的变量打印到终端中



常见的环境变量:

​	SHELL=/bin/bash

​	PWD :当前所在路径

​	PATH:linux执行命令的路径,去每一个路径中寻找路径,没有则直接报错

​	HOME:用户的家目录



定义环境变量

​	export 环境变量名=value   #注意:环境变量名一般情况下是大写



环境变量对当前用户生效:

​	原理:每打开一次终端,终端都会执行 ~/.bashrc文件.	只要将环境变量添加到  ~ /.bashrc文件里面.那么每打开一次终端,都会执行 ~/.bashrc这个文件,就会重新定义环境变量.

操作步骤:

​		vim ~/.bashrc  -->添加环境变量

​		source ~/.bashrc : 重新加载 .bashrc 文件.

环境变量对所有的用户生效: 运维人员.
    		原理: 当linux用户进行登录的时候, linux 操作系统会去执行 /etc/environment 文件.
    		只要将 /etc/environment 添加上我们自定义的环境变量.
   			 vim  ~/.bashrc   --> 添加环境变量 
    			source /etc/environment: 重新加载 /etc/environment  文件.

## 数组

简介:

​		shell语言中没有一维数组与二维数组之分,shell中所有数组只能是一维数组.

数组定义:

​		==数组名=(元素1 元素2 元素3 ...)==

数组指定下标赋值:

​		==数组名=([下标1]=value [下标2]=value)==

- 在没有赋值的位置上为空

### 数组访问

==${arrname[下标]}==

### 特殊数组访问

shell语言中提供了访问==数组个数==的方式:(只计算非空的成员个数)

- ==${#arrname[@]}==
- ==${#arrname[*]}==



shell语言提供了访问数组==所有元素==的方式:

- ==${arrname[*]}==
- ==${arrname[@]}==



#### 数组的特殊操作

shell语言中的数组==复制==

​		==`arr2=({$arr[*]})`==

shell语言中的数组==拼接==

​		==``arr2=({$arr[*]} {$arr[*]})``==

## 输入输出

### 输入

shell语言中提供输入的命令 read命令

1. read 变量名

2. read -p "提示语句" 变量名
3. read -a 数组名      // shell语言支持直接输入数组
4. read -s 变量          // shell支持保密输入
5. read -t time 变量名          //在固定时间内输入内容
6. read -n 字符个数 变量名   //在输入个数

### 输出

shell提供了专门的输出命令 echo

使用方式:

1. `echo 变量名`
2. echo支持同时输出多个变量
   - `echo var1 var2 var3`

3. echo 是默认换行的
   - `echo -n` 可以取消换行操作.

## shell运算符

shell语言本质是命令的集合文件,主要功能解析命令的时候使用的

1. shell语言并不擅长运算,擅长的是处理命令,如果需要处理复杂类型的数据可以通过C语言完成

2. shell脚本是不能进行浮点数运算的.



shell虽然不擅长做运算,但支持一些相对简单的运算 ++  /  --  ...

1. (())
2. ret=$[表达式]
3. expr

### (())

shell语言中(())运算效率是最高的,支持C语言语法.

1. `((sum = 3+7))`    #小括号内可以添加空格,也可以不添加
2. `((sum = num1 + num2))`    `((sum = $num1 + $num2))`		#变量相加 两个写法都可
3. `((n++))`    #shell语言支持++/--这种语法
4. shell语言支持幂运算**
   - ((2**10))
5. (())支持返回值,但前面需要加$
   - ==result=$((n++))==

### $[]

`$[]`也是shell语言中重要的运算符,但他的效率没有``$(())``高

1. `$[x + y]` #x,y可以不加$符号



### expr运算符

expr使用需要严格记录格式.expr执行效率也是所有运算符中最低的,expr可以进行字符运算

- expr 10 + 20            #30
- expr 10+20              #10+20  左右两端没有空格,字符串输出
- expr $x1 + $x2              #变量前需要添加$符号
- sum=`expr 10 + 20 ` # expr 计算的结果会直接输出到终端中， 如果想要将计算的结果保存下来，则需要 `` 符号
- mul=`expr 200 \* 3`  # *是通配符 在使用其 乘的功能的时候，需要转义符号 \

expr比较特殊,可以直接对字符串进行操作

- `expr length $str`			#计算出str字符串的长度
- `expr substr $str n m`         #截取从字符串str中第n位到第m位的字符内容 
- `expr index $str string`    #从str字符串中查找string字符所在的下标 (如果查找内容不存在则返回0)
- `expr match $str1 $str2`    #将str1与str2比较,相同返回字符串长度  不相同则返回0



## shell逻辑语句

### **if 判断语句** 

```shell
if 格式: 
    if [ 表达式 ]  ==> if test 表达式
    then 
        表达式成立执行的code语句
    fi  
    
if..else 格式
    if [ 表达式 ]
    then 
        code1
    else     
        code2
    fi  
                                            
if..elif...else格式
    if [ 表达式1 ]
    then 
        code1 
    elif [ 表达式2 ]  
    then
        code2
    else 
        code
    fi                    
```

### **字符串对象的判断**

```shell
shell语言中对字符串进行判断的时候,需要添加 双引号"". 
字符串判断
    -z : 判断字符串是否为空
    -n : 判断字符串是否为非空
    = 或者 == : 判断字符串是否相等的
    != : 判断字符串是否不相等
    \> : 大于
    \< : 小于.

课堂练习: 从键盘中输入两个字符串.判断字符串是否相等.

#! /bin/bash  

read -p "please input  string1 and string2  >> "  string1  string2  

if [ -z "$string1" ]
then    
    echo "string1 为空"
    exit 
fi 

if [ -z "$string2" ]
then    
    echo "string2 为空"
    exit 
fi 


if [ "$string1" = "$string2" ] 
then 
    echo string1 == string2  
else 
    echo string1 != string2 
fi  
```

### **数字类型判断**

```shell
shell 语言对数字对象进行判断的时候是需要使用
    -eq : 等于 (equle)   eg:  $number1 -eq $number2 
    -ne : 不等于 
    -gt : 大于 great
    -lt : 小于 little
    -ge : 大于等于  
    -le : 小于等于
课堂练习:
    从键盘中输入一个成绩. 输出这个成绩的等级
        >= 85 : A
        >= 75 : B
        >= 60 : C 
        <60   : D
        
#! /bin/bash  

read -p "请输入您的成绩 >> " score 


if [ "$score" -ge 85 ]   # 对于字符串对象必须要使用 "" 对于数字类型的对象，可以加双引号也可以不加
then 
    echo "A"

elif [ "$score" -ge 75 ]
then 
    echo "B"

elif [ $score -ge 60 ] 
then 
    echo C   

else 
    echo D

fi
        
```

**文件类型的判断**

```shell
shell语言提供了对文件的类型判断.文件类型: bsp-lcd  
    shell提供了以下的参数,用来判断文件的类型
        -b filename: 判断文件是否存在,是否是块设备文件.
        -c filename: 判断文件是否存在,是否是字符设备文件
        -d filename: 判断文件是否存在,是否是目录文件
        -f filename: 判断文件是否存在,是否是普通文件 (链接文件也是普通文件.)
        -p filename: 判断文件是否存在,是否是管道文件
        -L filename: 判断文件是否存在,是否是链接文件. 
        -S filename: 判断文件是否存在,是否是套接字文件
        -e filename: 判断文件是否存在.  
        -s filename: 判断文件是否为空. 
课堂练习:
    从键盘中输入一个文件名, 判断这个文件是什么类型的文件, 如果是普通类型的文件,并且为空,
    写入hello world. 
    思路:
        <1>. read -p filename 
        <2> -e 判断文件是否存在, 如果不存在.
        <3> if 嵌套.
        
eg:
#! /bin/bash 

# 从键盘中输入一个文件名
read -p  "please input file : >>"   file

# 判断文件是否存在
if [ -e   $file ]
then 
    echo $file
    if [ -b $file ]
    then 
        echo  块设备文件 
    
    elif [ -c $file ]
    then 
        echo  字符设备文件  

    elif [ -d $file ]
    then    
        echo  目录文件 

    elif [ -L  $file ]
    then 
        echo  链接文件 

    elif [ -f $file ]
    then 
        echo "this is 普通文件"
        if [ -s $file ]
        then 
            echo  "不是一个空文件"
        else 
            echo hello > $file
        fi  
    else 
        echo 其他类型的文件

    fi 

else 
    echo  您输入的文件不存在 
fi
```

### **文件权限的判断**

```shell
Linux文件的权限: w(write) 写权限.   r(read) 读权限   x 执行权限.
shell 判断文件的权限:
    -x filename :  判断文件是否存在, 是否有可执行权限
    -w filename :  判断文件是否存在, 是否有可写权限
    -r filename :  判断文件是否存在, 是否有可读权限. 
    
课堂练习:
    从键盘中输入文件的名称,判断文件的权限.
#! /bin/bash 

read -p "please input filename >> "  filename  


# 判断文件是否存在 
if test -e $filename 
then 
    echo $filename 存在

    # 判断权限问题 
    if test -x $filename 
    then 
        echo $filename 有可执行权限
    fi 

    if test -r $filename 
    then 
        echo $filename 有可读权限 
    fi 

    if test -w $filename 
    then 
        echo $filename  有可写权限 
    fi 

else 

    echo $filename 不存在
fi 

练习: 从键盘中输入一个文件名.判断这个文件是不是有可写权限,如果有可写权限,则追加hello 
#! /bin/bash 

# 使用命令行的位置参数  $1 

if [ -e $1 ]
then 
    
    if [ -w $1 ]
    then
        echo $1 拥有写权限
        echo hello >> $1 
    fi 

else 
    echo $1 不存在
fi 	
```

### **逻辑语句判断**

```shell
shell 在进行计算的时候, 也为我们提供了与或非得计算方式
    -a : and 逻辑与 eg:    表达式1 -a 表达式2
    -o : or  逻辑或
    !  : 逻辑非
    
课堂练习:
    从键盘只输入一个成绩,  100 >=score >= 80 A      
     80 > score >= 60 B     
     
#! /bin/bash 

read -p "please input score >>> "  score 

if [ $score -le 100  -a  $score -ge 80  ]
then 
    echo A 

elif [ $score -lt 80  -a $score -ge 60 ]
then
    echo B 

fi	
```

### **case...in 语句**

```shell
case...in 语句,类似与C语言中的 switch...case 语句, 全部都是多分支结构语句. 
格式:
    case 变量 in 
        匹配项1)
            执行语句
            ;; 
        匹配项2)
            执行语句
            ;; 
    esac 
```

### **case..in 匹配项**

```shell
shell语言中case...in语法是支持通配符的
    * : 任意个任意的字符. 
    []: [0-9]: 通配 0 ~ 9当中的任意一个字符
        [a-z]: 通配 a ~ z当中的任意一个字符
        [acd]: 通配 a c d 当中的任意一个字符 
                [0-9a-z]: 通过数字0 - 9 字母a-z当中的任意的一个字符. 
    ?: 统配一个任意的字符. 

通配符是支持或运算的
    "YES"|"yes"|'Y'|'y' : 使用场景            
```



### **while 循环** 

```shell
shell语言中 while 循环与 C语言中的 while 循环使用的方式是一样的.

shell 语言的while循环格式:
    while [ 循环条件 ]
    do 
        循环语句
    done 
```

### **shell 循环语句使用**

```shell
使用shell当中的循环计算 1 ~ 100 之间的和 
#! /bin/bash 

sum=0

# 产生1 ~ 100之间的数字 
i=0


while [ $i -lt 101  ]
do 
    # sum+= i
    (( sum += i++))
done 

echo $sum

```

### **死循环**

```shell
shell语言专门提供了一种死循环的方式
while true 
do 
    循环体.
done

eg:
#! /bin/bash 


#使用变量 i 用来模拟下载的程度 
i=0

# 定义一个变量 flag 用来表示你是不是会员。
flag=1


while true  # 死循环下载。
do
    if [ $flag -eq 0 ] 
    then 
        sleep 2
    fi 
    
    # 开始下载数组    
    ((i++)) 
    echo  开始下载的进度是 $i %,


    if [ $i -eq 100 ]
    then 
        echo "下载完成"  
        break
    fi 

done 

```

### **for循环**

```shell
shell语言中for循环有两个风格. shell风格for循环   C语言风格的for循环. 

C语言风格的for循环
    for (( 表达式1; 表达式2; 表达式3))
    do 
        循环体
    done  
    eg: 
        #! /bin/bash 

        # target: 向巴黎奥运会开幕式道歉。
        
        i=0
        
        # C语言的for循环
        for ((i = 0 ; i < 100; i++))
        do
            echo 第$i次,sorry, i love 巴黎奥运会.
            sleep 1
        done
        
shell 语言风格for循环
    for  临时变量  in  参数列表 
    do     
        循环体;     // 依次将参数列表里面的每一个值,给到临时变量中.                                                                     
    done 

eg: 
#！/bin/bash 

# shell 语言风格的 for 循环

for var in  11 22 33 44 55 66 77 88 
do 
    echo $var
done

echo ----------------------------------------------

# target 从键盘上输入一个路径， 然后将这个路径里面的每一个文件名打印出来
read -p "please input path"  path 

for name in  `ls $path`
do 
    echo $name 
done 

```

### **循环控制关键字**

```shell
shell语言也是支持break与continue, shell语言中的break与continue 和 C语言中
是相同.

不同点:
    break 数字 : 当循环嵌套的时候进行使用. break 2 跳出2层循环.
    continue 数字: 当嵌套循环的时候进行使用.  
    
```

###  **select...in 语法**

```shell
select ...in 语法:主要使用方便用户与计算机进行交互使用. 一般会配合case..in语句进行使用.

语法格式:
    select 变量 in  列表
    do 
        语句
    done
    
eg:
#! /bin/bash  

select  name in  windows  linux  macOS  harmonyOS  安卓   
                # 将windows  linux  macOS  harmonyOS  安卓    做成一个选项,
                # 选择几 对应 name变量里面的值就是多少.
do 
    echo $name 
done
    
```

### **select..in 使用**

```shell
课堂练习:选择你自己的电脑品牌, 然后输出其操作系统.

#! /bin/bash  

select computer in  apple  dell  联想  华硕  huawei  oppo  小米 雷神 
do 
    # 配合 case... in 进行使用
    case $computer in 
        apple)
            echo MacOS
            ;;
        oppo| dell | 联想|华硕|小米|雷神) 
            echo  windows
            ;;
        huawei)
            echo harmonyOS
            ;;
        *)
            echo other system 
            ;; 
    esac
done 
```

###  **输入提示符修改**

```shell
select...in 语法默认使用的输出提示符 #? 
通过环境变量PS3进行修改
    export PS3=">>" : 将默认的输出提示符#? 修改为 >> 
```

## **函数** 

```shell
shell语言提供简单的函数.函数完成复杂功能. 
定义格式: 
function 函数名
{
    函数体
    return  结果
}

注意:
    1.function 是来声明函数的. 这里的function是可以省略的. 建议不要省略: 方便代码的阅读
    2.shell语言的函数命名规范与C语言是一致的. 
    3.shell的函数传递参数,是通过 位置参数进行传递. eg 函数名 参数1 参数2   $1
    4.shell中所有的变量都是全局变量. 通过local 变量名. local修饰的变量就是局部变量. 
    5.{} 里面的内容就是函数体. 
    6.shell语言中的函数.返回值[0, 255] 之间的数字.如果想返回其他的数字则通过echo拿到.
    7.shell语言中的函数调用方式
            函数名 参数1  参数2  参数3 
```

### **函数练习**

```shell
#! /bin/bash 

# 定义一个加法函数
function add 
{
    var1=$1   #var1 与 var2 全部都是全局变量 
    var2=$2    
    local sum=$(($var1+$var2))    // sum 表示的是一个局部变量。

    #return  $sum  # return 返回值的时候只能返回值 [0 ~ 255]之间的值 
                 #  如果需要获取 return 返回值的值通过$？ 进行获取
    echo $sum 
}
ret=`add 20 30` # echo 返回值的时候需要时用``进行接受一下。 
echo $ret 


# 调用函数   // shell语言函数只支持位置参数。 对于函数add来说  10 就是$1   20就是 $2
# ret=$(add 10 20 )

```

