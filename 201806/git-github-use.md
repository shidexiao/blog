



注册账户以及创建仓库
要想使用github第一步当然是注册github账号了， github官网地址：https://github.com/。 
之后就可以创建仓库了（免费用户只能建公共仓库），Create a New Repository，填好名称后Create，之后会出现一些仓库的配置信息，这也是一个git的简单教程。



配置Git
首先在本地创建ssh key；

```
$ ssh-keygen -t rsa -C "your_email@youremail.com"

```
后面的your_email@youremail.com改为你在github上注册的邮箱，之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。成功的话会在~/下生成.ssh文件夹，进去，打开id_rsa.pub，复制里面的key。

回到github上，进入 Account Settings（账户配置），左边选择SSH Keys，Add SSH Key,title随便填，粘贴在你电脑上生成的key。


为了验证是否成功，在git bash下输入：
```
$ ssh -T git@github.com

```
如果是第一次的会提示是否continue，输入yes就会看到：You've successfully authenticated, but GitHub does not provide shell access 。这就表示已成功连上github。

接下来我们要做的就是把本地仓库传到github上去，在此之前还需要设置username和email，因为github每次commit都会记录他们。
```
$ git config --global user.name "your name"
$ git config --global user.email "your_email@youremail.com"

```






