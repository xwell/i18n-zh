﻿#summary 软件翻译的校对
  * 直接打开文件检查
  * 运行程序校对，具体步骤如下
    1. 假定程序名为`foo`, 翻译的po文件叫 `zh_CN.po`
    1. 运行 `msgfmt --statistics -c -v -o foo.mo zh_CN.po` [1](1.md)
    1. 将`foo.mo`拷贝至 `/usr/local/share/locale/zh_CN/LC_MESSAGES/` 和 `/usr/share/locale/zh_CN/LC_MESSAGES/` (需要root权限)
    1. 运行相关的程序，检查翻译是否恰当

PS：
  1. 将这些可执行文件的路径加入环境变量“PATH”中。
  1. 使用 pofilter 检查更完美，参见 http://translate.sourceforge.net/wiki/toolkit/pofilter 。