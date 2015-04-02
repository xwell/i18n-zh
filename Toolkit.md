﻿#summary 相关工具软件

# 概述 #

> 这里枚举了本项目可能用到的工具包，以及其下载地址。

# 工具列表 #
> 以下给出的工具版本是经过测试的版本，低版本可能不工作(尤其是 xsltproc)，如果有高版本不能工作，请立即报告。其 Windows 下的二进制包下载地址附后。

  * Java SE 1.4.2/6.0 [1](1.md)            : http://java.sun.com/javase
  * Python 2.4.4/2.5.1 [1](1.md)           : http://www.python.org/windows
  * python-libxml2 2.6.27            : http://users.skynet.be/sbi/libxml-python
  * libxml2-utils 2.6.27 [1](1.md)         : http://code.google.com/p/i18n-zh/downloads/list
  * xsltproc 1.1.20 [1](1.md)              : http://code.google.com/p/i18n-zh/downloads/list
  * gettext 0.16.1 [1](1.md)               : http://code.google.com/p/i18n-zh/downloads/list
  * poedit 1.3.6 [2](2.md)                 : http://www.poedit.net
  * ant 1.7 [3](3.md)                      : http://ant.apache.org/
  * fop 1.0-dev [4](4.md)                  : http://xmlgraphics.apache.org/fop/
  * translate-toolkit                : http://sourceforge.net/projects/translate/

  1. 将这些可执行文件的路径加入环境变量“PATH”中。
  1. poedit 输出的 po 格式与标准 gettext 格式不同。如果你与他人协作翻译，请约定好格式(po 文件编辑工具很多，因此不推荐 poedit 之类的专用格式，**强烈建议**使用标准 gettext 格式)。poedit 保存的 po 文件格式就是 poedit，如果要转换成标准 gettext 格式，那么用命令行工具 msgmerge 即可。
  1. ant 已经提交到 i18n-zh，无须下载。
  1. fop 已经提交到 i18n-zh，无须下载。为了生成的中文 PDF 文件支持复制或搜索等特性，只好使用开发版本。
  1. gettext，libxml2-utils，xsltproc 都在 gettext-0.16.1\_xsltproc-1.1.20.tar.bz2 中。
  1. translate toolkit 中的 pomerge 是合并翻译的工具，pofilter 是检查翻译的工具。参见 http://translate.sourceforge.net/wiki/toolkit/index 。

> 下面给出 Debian GNU/Linux 下的安装方法，以 root 身份运行一个简单的命令即可：
```
apt-get install sun-java5-jdk python python-libxml2 libxml2-utils xsltproc gettext kbabel
```

> 它假设你用的是 KDE 中的翻译工具 KBabel，当然你也可以用 Gnome 的翻译工具 gtranslator。

# 项目列表 #
  * l10n(cpio, icewm, iso-codes, nano, seahorse, sed, etc.)
    * gettext，translate toolkit，poedit 或 kbabel，或 gtranslator
  * doc(docbook, subversion, etc.)
    * gettext，translate toolkit，poedit 或 kbabel，或 gtranslator
    * Java SE
    * Python
    * python-libxml2
    * libxml2-utils
    * xsltproc