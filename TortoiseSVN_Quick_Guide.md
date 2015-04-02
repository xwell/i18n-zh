本文简要介绍了利用 TortoiseSVN 上传文件的方法。
## 简介 ##
你不想看 TortoiseSVN 的详细文档，想直接上手操作吧？嘿嘿，这份东西就是为你而写的。

[返回新手指南](Newbie.md)

### 详细说明 ###

好，开始了。哈哈，首先，我假设你已经装上好 TortoiseSVN 了。如果没有，别看了，去装了再说。
边看边做，包你 10 分钟内搞定上传。
  * 在磁盘上新建一个目录。比如像我，d:\test
![http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/1.png](http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/1.png)
  * 右键点新建目录 test，弹出菜单，选中 SVN Checkout ...
![http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/2.png](http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/2.png)
  * 弹出菜单照着我的图片上的填，完了以后点 OK
![http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/3.png](http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/3.png)
  * 出来的应该跟我的是一样的。
![http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/4.png](http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/4.png)
> 因为上面选了 Only check out the top folder。所以这里只会有三个 TP 下的顶层文件。如果你想要那个 TP 下的所有文件的话，就不要勾上这个选项。但那些目录下都是别人的文件，你要有了什么用呢？除非，你要跟别人合作，或是你要检查别人翻译的东西。

> 好了。再下来，就是向服务器上传你自己的东西了。
  * 在 test 目录下，新建一个目录。比如说，你翻译的是 foo-1.0.0。那就新建目录 foo。然后把你的正在翻译的 po 文件放进去。像我这样
![http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/5.png](http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/5.png)
![http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/6.png](http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/6.png)
  * 回到 d 盘。右键点 test 目录，选择 SVN Commit...
![http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/7.png](http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/7.png)
  * 在对话框中，把要更新的文件全选上。点 OK 就行了。
![http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/8.png](http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/TortoiseSVN_Quick_Guide_pic/8.png)

上方的那一句话，是你对这一更新的简要说明。最好加上，否则别人不知道你做了什么。而且这样做的好处就是以后你看 log 时能知道这一步操作是为什么而做的，方便 checkout 特定版本的文件。这年头，做好事要留名，嘿嘿。

  * 以后，所有的修改全要在 d:\test\foo\a.po 上进行。改好了，就回到 d 盘，右键点 test 目录，commit。当然，由于以前已经做过一次 commit 了，这之后也可以直接右键点文件来选择 commit。不过，我的建议是点 test 选 commit。因为，你可能对 test 下又加了什么目录。比如，你不止翻译了一个 foo-1.1.0，你还翻译了 bar-1.1.0。这时候，只要把 bar 建在 test 目录下，然后像第一次操作 foo 时一样操作就行了。
  * 想要知道为什么的话，就去看 download 下的详细中文档吧。不过，普通使用者只要看看第五章就行了，而且就只要最前面的几小节内容就好。看多了，没用。小心头晕
[返回新手指南](Newbie.md)