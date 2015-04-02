# 概述 #

> 随着 DocBook 的流行和普及，我们迫切需要一个完整的中文手册。因为其翻译工作量巨大，所以我们不能翻译将要过时的 4.x 版本的文档，而是正在开发(已经发布了第三个预览版本，接近发布)的 5.x 版本的文档，即《DocBook 5.0: The Definitive Guide》。

> 如果您对此项目感兴趣，请让我们知道您的想法。我们迫切需要帮助，包括但不限于定义样式表，构建，翻译，复审。

# 概要 #

  * 定义 DocBook 5 的基本样式表，能成功构建文档。(done)
  * 编写build.xml，使用ant构建文档，至少包含html和pdf格式。(done)
    * 根据英文源代码构建英文文档。(done)
    * 根据英文源代码生成pot文件。(done)
    * 根据zh\_CN.po生成简体中文文档，至少包含html和pdf格式。(done)
  * 翻译ant创建的pot文件。(done, only remain elements reference)
  * 复审ant创建的doc，至少包含html和pdf格式。(done, only remain elements reference)
  * 迁移原版样式表，使得构建出的文档样式与英文版本基本一致。(pending)

# 快照 #

  * [DocBook：权威指南 - chm(r7547)](http://i18n-zh.googlecode.com/files/defguide5-zh_CN-r7547.chm)
  * [DocBook：权威指南 - pdf(r7547)](http://i18n-zh.googlecode.com/files/defguide5-zh_CN-r7547.pdf.bz2)
  * [DocBook 5.0：权威指南 - r7490/pdf](http://i18n-zh.googlecode.com/files/defguide5-zh_CN-0.0.22-r7490.pdf.bz2)
  * [DocBook 5.0：权威指南 - r7490/html](http://i18n-zh.googlecode.com/files/defguide5-zh_CN-0.0.22-r7490.html.tar.bz2)
  * [DocBook 5.0：权威指南 - r7406/r463](http://i18n-zh.googlecode.com/files/defguide5-zh_CN-r7406.pdf)
  * [DocBook 5.0：权威指南 - r6804/r129](http://i18n-zh.googlecode.com/files/defguide5-zh_CN-r6804_129.pdf)
  * [DocBook 5.0: The Definitive Guide - r6802](http://i18n-zh.googlecode.com/files/defguide5-r6802.pdf)

# 资源 #
  * [DocBook Release](http://www.docbook.org/xml/)
  * [DocBook Specifications](http://www.docbook.org/specs/)
  * [DocBook V4.x](http://docbook.org/schemas/4x)
  * [DocBook V5.x](http://docbook.org/schemas/5x)
  * [DocBook: The Definitive Guide](http://docbook.org/tdg/)
  * [DocBook 5.0: The Definitive Guide](http://docbook.org/tdg5/)
  * [DocBook XSL: The Complete Guide](http://www.sagehill.net/docbookxsl/index.html)
  * [DocBook XSL Stylesheet Reference Documentation](http://docbook.sourceforge.net/release/xsl/current/doc/)
  * [DocBook svn](http://docbook.svn.sourceforge.net/svnroot/docbook/trunk/)

# 进度 #
  * **由于长期无人协作，已经直接在[官方版本库](http://docbook.svn.sourceforge.net/viewvc/docbook/trunk/defguide5/zh/)维护**
  * 2007-10-30 [r7547](https://code.google.com/p/i18n-zh/source/detail?r=7547), 5808/6369(91.19%), tr/fu/un=5808/515/46
  * 2007-10-10 [r507](https://code.google.com/p/i18n-zh/source/detail?r=507), 4601/6369(87.9%),tr/fu/un=5555/770/44
  * 2007-10-09 [r499](https://code.google.com/p/i18n-zh/source/detail?r=499), 4601/6369(72.2%),tr/fu/un=4601/1743/25
  * 2007-08-31 [r463](https://code.google.com/p/i18n-zh/source/detail?r=463), 1213/1213(100%)
  * 2007-06-04 [r267](https://code.google.com/p/i18n-zh/source/detail?r=267), 626/1215(51.5%)
  * 2007-05-28 [r178](https://code.google.com/p/i18n-zh/source/detail?r=178), 535/1215(44.0%)
  * 2007-05-17 [r166](https://code.google.com/p/i18n-zh/source/detail?r=166), 509/1215(41.8%)
  * 2007-05-15 [r133](https://code.google.com/p/i18n-zh/source/detail?r=133), 512/1220(41.9%)
  * 2007-05-14 [r129](https://code.google.com/p/i18n-zh/source/detail?r=129), 468/1220(38.3%)
  * 2007-05-11 [r119](https://code.google.com/p/i18n-zh/source/detail?r=119), 380/1220(31.1%)
  * 2007-05-09 [r111](https://code.google.com/p/i18n-zh/source/detail?r=111), 362/1221(29.6%)