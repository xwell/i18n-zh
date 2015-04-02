﻿#summary 翻译工作流程

#labels Featured

# 概述 #

> 这里描述了本项目的翻译工作流程，i18n 流程待时机成熟后制定，如有不妥，请立即指出。

# 准备 #
  * 我们的原则是质量优先，强烈**不赞成**翻译自己不熟悉的软件/文档。
  * 阅读[主页](http://code.google.com/p/i18n-zh/)和[维基](http://code.google.com/p/i18n-zh/w/list)中的所有文档。
  * 根据[Source 页面](http://code.google.com/p/i18n-zh/source)的指令，检出最新工作副本。
  * 下载 [Toolkit](http://code.google.com/p/i18n-zh/wiki/Toolkit) 页面中的工具包。
  * 熟悉翻译和构建流程。

# 协调 #
  * 在论坛发贴，说明你要负责的工作，申请 svn/git 账号。
  * 如果你需要翻译的软件/文档不存在，请提交，自动成为其协调者。
  * 否则，在论坛发贴，抄送给协调者，告诉你目前感兴趣的部分。一周内无回复，视为默许你的翻译计划。
  * 页面 [Merge](Merge.md) 描述了合并协同翻译结果的方法。

# 翻译 #
  * 开始翻译，对于非约定俗成，或有争议，模糊，歧义的翻译在 po 文件的前面建立字典，格式如下：
```
# Dictionary:
# original text     chinese translation     description
```

  * 检查翻译
```
msgfmt --statistics -c zh_CN.po
```

  * 复审翻译
    * 对于 l10，直接复审 po 文件。
    * 对于 doc，构建文档后，精读结果文档。
    * 如果发现问题，回到“开始翻译”，修正问题。

  * 格式化翻译
    * 根据软件/文档之协调者的要求格式化为标准 gettext 格式，或者 poedit 等其它格式。
    * 如果你是协调者，**强烈建议**你使用标准 gettext 格式。
    * 在你准备提交之前，用 msgmerge 格式化 po 文件，假设有 foo.pot，zh\_CN.po 两个文件，方法如下：
```
    msgmerge --no-wrap -o zh_CN-new.po zh_CN.po foo.pot
    mv -f zh_CN-new.po zh_CN.po
```

# 提交 #
  * 提交到 i18n-zh
    * 精心组织语句，编写提交日志。
    * 将结果提交到 git 或 svn 仓库。
    * 如果提交出现错误，参看页面 [Merge](Merge.md) 来合并翻译。
    * 在论坛发贴，请人帮忙复审。
  * 提交到官方版本库
    * 如果你有提交权限，请直接提交。
    * 如果是 [TP](TP.md) 软件，并且你有 [TP](TP.md) 提交权限，请直接提交到 [TP](TP.md)。
    * 否则，请其他人代为提交。切记，**如果其他人也只是有 [TP](TP.md) 提交权限，那么“Last-Translator”不会是你，而是 [TP](TP.md) 提交者，你的名字只会出现在注释域的版权行中，类似“Name**

&lt;email&gt;

, year”