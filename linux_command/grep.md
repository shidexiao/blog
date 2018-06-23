

grep全称是Global Regular Expression Print，表示全局正则表达式版本

Linux系统中grep命令是一种强大的文本搜索工具，它能使用正则表达式搜索文本，并把匹 配的行打印出来。

语法  
grep [option] [pattern] [file]

grep [-abcEFGhHilLnqrsvVwxy][-A<显示列数>][-B<显示列数>][-C<显示列数>][-d<进行动作>][-e<范本样式>][-f<范本文件>][--help][范本样式][文件或目录...]

功能  
grep指令用于查找内容包含指定的范本样式的文件，如果发现某文件的内容符合所指定的范本样式，预设grep指令会<font color='red'>把含有范本样式的那一列显示出来</font>。
若不指定任何文件名称，或是所给予的文件名为"-"，则grep指令会从标准输入设备读取数据。

选项option  
<ul><li>
<strong>-a 或  --text</strong> : 不要忽略二进制的数据。   
</li><li>
<strong>-A&lt;显示行数&gt; 或   --after-context=&lt;显示行数&gt;</strong> : 除了显示符合范本样式的那一列之外，并显示该行之后的内容。   
</li><li>
<strong>-b  或 --byte-offset</strong> : 在显示符合样式的那一行之前，标示出该行第一个字符的编号。   
</li><li>
<strong>-B&lt;显示行数&gt; 或  --before-context=&lt;显示行数&gt;</strong> : 除了显示符合样式的那一行之外，并显示该行之前的内容。   
</li><li>
<strong>-c  或  --count</strong> : 计算符合样式的列数。   
</li><li>
<strong>-C&lt;显示行数&gt;  或  --context=&lt;显示行数&gt;或-&lt;显示行数&gt;</strong> : 除了显示符合样式的那一行之外，并显示该行之前后的内容。   
</li><li>
<strong>-d &lt;动作&gt;  或    --directories=&lt;动作&gt;</strong> : 当指定要查找的是目录而非文件时，必须使用这项参数，否则grep指令将回报信息并停止动作。</li><li>   

<strong>-e&lt;范本样式&gt; 或 --regexp=&lt;范本样式&gt;</strong> : 指定字符串做为查找文件内容的样式。   
</li><li>
<strong>-E    或  --extended-regexp</strong> : 将样式为延伸的普通表示法来使用。   
</li><li>
<strong>-f&lt;规则文件&gt; 或 --file=&lt;规则文件&gt;</strong> : 指定规则文件，其内容含有一个或多个规则样式，让grep查找符合规则条件的文件内容，格式为每行一个规则样式。   
</li><li>
<strong>-F  或 --fixed-regexp</strong> : 将样式视为固定字符串的列表。   
</li><li>
<strong>-G  或 --basic-regexp</strong> : 将样式视为普通的表示法来使用。   
</li><li>
<strong>-h  或 --no-filename</strong> : 在显示符合样式的那一行之前，不标示该行所属的文件名称。   
</li><li>
<strong>-H  或 --with-filename</strong> : 在显示符合样式的那一行之前，表示该行所属的文件名称。   
</li><li>
<strong>-i  或  --ignore-case</strong> : 忽略字符大小写的差别。   
</li><li>
<strong>-l   或 --file-with-matches</strong> : 列出文件内容符合指定的样式的文件名称。   
</li><li>
<strong>-L 或  --files-without-match</strong> : 列出文件内容不符合指定的样式的文件名称。   
</li><li>
<strong>-n  或 --line-number</strong> : 在显示符合样式的那一行之前，标示出该行的列数编号。   
</li><li>
<strong>-q  或 --quiet或--silent</strong> : 不显示任何信息。   
</li><li>
<strong>-r  或 --recursive</strong> : 此参数的效果和指定"-d recurse"参数相同。   
</li><li>
<strong>-s   或 --no-messages</strong> : 不显示错误信息。   
</li><li>
<strong>-v   或 --revert-match</strong> : 显示不包含匹配文本的所有行。   
</li><li>
<strong>-V  或 --version</strong> : 显示版本信息。   
</li><li>
<strong>-w 或  --word-regexp</strong> : 只显示全字符合的列。   
</li><li>
<strong>-x    --line-regexp</strong> : 只显示全列符合的列。   
</li><li>
<strong>-y </strong>: 此参数的效果和指定"-i"参数相同。
</li></ul>


示例

<code>grep test *file </code>
<pre>
$ grep test test* #查找前缀有“test”的文件包含“test”字符串的文件  
testfile1:This a Linux testfile! #列出testfile1 文件中包含test字符的行  
testfile_2:This is a linux testfile! #列出testfile_2 文件中包含test字符的行  
testfile_2:Linux test #列出testfile_2 文件中包含test字符的行 
</pre>

`grep -r update /etc/acpi `
<pre>
$ grep -r update /etc/acpi #以递归的方式查找“etc/acpi”  
#下包含“update”的文件  
/etc/acpi/ac.d/85-anacron.sh:# (Things like the slocate updatedb cause a lot of IO.)  
Rather than  
/etc/acpi/resume.d/85-anacron.sh:# (Things like the slocate updatedb cause a lot of  
IO.) Rather than  
/etc/acpi/events/thinkpad-cmos:action=/usr/sbin/thinkpad-keys--update 
</pre>


<pre>
shidexiao at shidexiaodeMacBook-Pro in ~
$ ls -a | grep \.ssh
.ssh
</pre>