# 简介 #

关于《Version Control with Subversion》的信息请参见[red-bean](http://svnbook.red-bean.com/index.en.html)网站。官方版本库目前(2007 年 4 月)是直接翻译英文 DocBook 源文件，而大的文件有几十万字，所以翻译工作量大，难以维护，中文内容已经严重滞后于英文版本。

因此，[我](Dongsheng.md)考虑切换到 xml2po 方式翻译，从英文 DocBook 源文件生成 POT 文件，从而化大为小，翻译简单，维护容易。但是初期的切换工作是痛苦的，工作量很大。

根据启动翻译 [Docbook](Docbook.md) 的经验，深思熟虑之下，经过比较，[我](Dongsheng.md)找到与现有中文翻译最接近的英文 DocBook 源文件，与中文对比，生成迁移后的翻译。然后用构建文件生成中文输出，审阅和修正迁移错误。

在 2009 年 2 月初，开始切换到开发维护更活跃，功能更完善的 [PO4A](http://po4a.alioth.debian.org/)，仍旧是基于 PO 的翻译。

在 2009 年 3 月底，由于翻译机制已经成熟，所以开始合并到官方版本库。自此，本书同时在 [i18n-zh](http://code.google.com/p/i18n-zh/) 和 [svnbook](http://code.google.com/p/svnbook/) 维护。原则上，我们鼓励先提交到 [i18n-zh](http://i18n-zh.googlecode.com/svn/trunk/doc/svnbook/)，大家复审后再同步到 [svnbook](http://svnbook.googlecode.com/svn/trunk/src/)。

<font color='#FF0000'>PS: 虽然说 red-bean 是每夜构建，实际上对于大多数中文用户来说，是每天下午 2 点开始构建，最长需要 15 分钟。</font>

# 下载版本 #
  * [i18n-zh](http://code.google.com/p/i18n-zh/downloads/list?q=label:svnbook)
  * [red-bean](http://svnbook.red-bean.com/index.zh.html)

# 在线版本 #
  * [svnbook-1.6(red-bean)](http://svnbook.red-bean.com/nightly/zh/index.html)
  * [svnbook-1.4](http://i18n-zh.googlecode.com/svn/www/svnbook-1.4/index.html)
  * [svnbook-1.6(fallback)](http://i18n-zh.googlecode.com/svn/www/svnbook/zh/index.html)