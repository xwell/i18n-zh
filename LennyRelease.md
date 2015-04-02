# 翻译信息 #
| **文件名**     | **进度**   | **认领者**     | **复审者**         |
|:------------------|:-------------|:------------------|:----------------------|
| about        | 20/20    | chenxianren  | dongsheng.song   |
| installing   | 39/39    | rockrush4    | dongsheng.song   |
| issues       | 96/81    | manphiz      | dongsheng.song   |
| moreinfo     | 21/21    | chenxianren  | dongsheng.song   |
| old-staff    | 15/15    | chenxianren  | dongsheng.song   |
| release-notes| 68/68    | chenxianren  | dongsheng.song   |
| upgrading    | 368/330  | ZhengYuJi    | dongsheng.song   |
| whats-new    | 148/132  | lave.wang.w  | dongsheng.song   |

# 检查方法 #
```
sudo apt-get -y install make gettext po4a w3m xmlroff xsltproc docbook-xml docbook-xsl docbook-xsl-doc-html

make updatepo LINGUA=zh_CN
make tidypo LINGUA=zh_CN
make stat

make validate LINGUA=zh_CN

make html LINGUA=zh_CN architecture=all
make pdf LINGUA=zh_CN architecture=all
make txt LINGUA=zh_CN architecture=all

msgcat -w 80 xxx.po > tmp.po
mv tmp.po xxx.po

msgfmt --statistics -c xxx.po
```

# 最新文档 #
  * [PDF 格式](http://code.google.com/p/i18n-zh/downloads/list)
  * [HTML 格式](http://i18n-zh.googlecode.com/svn/www/lenny-release-notes)