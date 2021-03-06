

ln:link


ln是linux中又一个非常重要命令，它的功能是为某一个文件在另外一个位置建立一个同步的链接.
当我们需要在不同的目录，用到相同的文件时，我们不需要在每一个需要的目录下都放一个必须相同的文件，我们只要在某个固定的目录，放上该文件，然后在 其它的目录下用ln命令链接（link）它就可以，不必重复的占用磁盘空间。

命令功能
Linux文件系统中，有所谓的链接(link)，我们可以将其视为档案的别名，而链接又可分为两种 :
硬链接(hard link)与软链接(symbolic link)
硬链接的意思是一个档案可以有多个名称，而软链接的方式则是产生一个特殊的档案，该档案的内容是指向另一个档案的位置。
硬链接是存在同一个文件系统中，而软链接却可以跨越不同的文件系统。
不论是硬链接或软链接都不会将原本的档案复制一份，只会占用非常少量的磁碟空间。
* 软链接
    * 软链接，以路径的形式存在。类似于Windows操作系统中的快捷方式
    * 软链接可以 跨文件系统 ，硬链接不可以
    * 软链接可以对一个不存在的文件名进行链接
    * 软链接可以对目录进行链接
* 硬链接
    * 硬链接，以文件副本的形式存在。但不占用实际空间。
    * 硬链接只有在同一个文件系统中才能创建
    * 不允许给目录创建硬链接


语法：
ln(选项)(参数)

选项
* -b或--backup：删除，覆盖目标文件之前的备份；
* -d或-F或——directory：建立目录的硬连接；
* -f或——force：强行建立文件或目录的连接，不论文件或目录是否存在；
* -i或——interactive：覆盖既有文件之前先询问用户；
* -n或--no-dereference：把符号连接的目的目录视为一般文件；
* -s或——symbolic：对源文件建立符号连接，而非硬连接；
* -S<字尾备份字符串>或--suffix=<字尾备份字符串>：用"-b"参数备份目标文件后，备份文件的字尾会被加上一个备份字符串，预设的备份字符串是符号“~”，用户可通过“-S”参数来改变它；
* -v或——verbose：显示指令执行过程；
* -V<备份方式>或--version-control=<备份方式>：用“-b”参数备份目标文件后，备份文件的字尾会被加上一个备份字符串，这个字符串不仅可用“-S”参数变更，当使用“-V”参数<备份方式>指定不同备份方式时，也会产生不同字尾的备份字符串；
* --help：在线帮助；
* --version：显示版本信息。

参数
* 源文件或目录
* 目标文件或目录

使用示例

给文件创建软链接，
为log2013.log文件创建软链接link2013，如果log2013.log丢失，link2013将失效：
>ln -s log2013.log link2013

给文件创建硬链接
>ln log2013.log ln2013

给目录创建软链接
>ln -sv /opt/soft/test/test3 /opt/soft/test/test5
