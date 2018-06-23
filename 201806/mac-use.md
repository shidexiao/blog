







* 在终端（Terminal）输入如下命令，即可显示隐藏文件和文件夹
<pre>
defaults write com.apple.finder AppleShowAllFiles -boolean true ; killall Finder
</pre>


* 如需再次隐藏原本隐藏的文件和文件夹，可以输入如下命令
<pre>
defaults write com.apple.finder AppleShowAllFiles -boolean false ; killall Finde
</pre>