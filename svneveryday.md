[回到TP](TP.md)
## 简介 ##

本文简要介绍 linux 下 svn 的日常使用。


## 详细说明 ##

首先请在 linux 下装上 subversion 包。对于 Debian，可以用
```
sudo apt-get install subversion
```
来做。其它发行版请在各自的包管理器中找一下。**如果不想用文本界面的话，rapidsvn 是个不错的选择。完全图形化的**

接下来就类似于我写的 TortoiseSVN 了。
  * 先用 svn checkout -N https://https://i18n-zh.googlecode.com/svn/trunk/
> > 这将在当前目录下生成一个名叫“ trunk ” 的目录。且 -N 选项的使用就是告诉 svn 只取出顶层文件，不取目录。这样，我们就取得了一个正常的，可以本地操作的工作目录（working copy）了。如果你有上面服务器的 svn  上传权的话，请在此时输入密码和用户名。如果没有的话，请把上面地址中的 **https** 改成 **http**
> > 。上传帐号的申请，可以看[这里的说明](VCS.md)。
  * 接下来，进入那个” trunk “目录。并建立文件操作一下。
```
cd trunk
mkdir test   # 新建一个 test 目录
vi test.txt
  随便写点东西
```
  * 以上全部做完以后，退回 trunk 目录，用 `svn stat *` 看一下。你会发现刚才新建的东西前面都有一个 ”?“。这表明，这些文件还未受到 svn 的版本控制。所以你需要加上它们，用命令
```
svn add *
```
  * 现在你应该看到输出了，所有文件前面全都有了一个 "A"，代表是新增文件。
  * 最后，上传吧。在 trunk 目录下，用 `svn commit` 命令。它会自动找出要上传的文件的。上传前，会启动你的编辑器，要求你写上点东西，也就是更新说明。最好写上，否则会出现 a)bort c)ontinue 这样的东西。当然你可以选 continue，但这样服务器上的记录中对这一次的操作没有什么说明，以后想 checkout 此版本时你会不知道此版本做了哪些更改。

好了。就这么多内容。呵呵，比 win 下的 tortoisesvn 看上去简单一点。还有一点，上面有些命令是有缩写的。比如，可以把 `svn checkout` 写成 `svn co`，把 `svn commit` 写成 `svn ci` 等等。装上 svn 后可以用 svn help 来看看。应该说 svn 的 help 写得非常不错的。简单实用！我就是看了它学会 svn 的操作的。

## 范例 ##
这是我的一次操作
```
   cd myworkplace
   svn co $repo/fetchmail fetchmail-6.3.8    #取出 fetchmail 并重命名为带上版本号的 fetchmail
   edit&save fetchmail-6.3.8/fetchmail-6.3.8.zh_CN.po
   
   mkdir latrin                               # 新建 latrin
   mv ~/Desktop/latrin-0.10.0.pot latrin/     #将下载到的 pot 放到 latrin 下
   cd latrin/           
   msginit -l zh_CN.utf8                      # 生成一个 utf8 编码的 zh_CN.po，准备翻译
   mv zh_CN latrin-0.10.0.zh_CN.po            # 重命名。方便以后用 sendpo.sh 上传给 tp-robot
   edit&save latrin-0.10.0.zh_CN.po           # 干活
   
   cd ..                                      # 退回 myworkplace
   svn add *                                  # 加上刚才新建的所有东西
   svn ci                                     # 提交今天所做的全部修改
```
日常使用，基本只要会 co 和 ci 就可以了。
上面有段命令是新建一个工程时，一直要做的。命令很多，但每次都很有规律，所以嘛，呵呵。我写成了脚本
```
   #!/bin/bash
   # filename: genpo.sh
   echo -n "Enter a directory name: "
   read d_name
   mkdir ${d_name}
   mv $1.pot ${d_name}
   cd ${d_name}
   msginit -l zh_CN.utf8
   mv zh_CN.po $1.zh_CN.po
   cd ..
   svn add ${d_name}
   vi ${d_name}/$1.zh_CN.po
```

> 这样，以后把下载到的 pot 放在 myworkplace 目录下。然后用 `genpo.sh 文件名-版本号` 不要带后缀 .pot。编辑好以后，直接 `svn ci` 就 OK 了。
[回到TP](TP.md)