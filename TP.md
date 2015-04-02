﻿#summary TP 软件翻译规范
[回到新手指南](Newbie.md)
## TP 的翻译流程 ##

1. 挑选要翻译的软件包。
> 请先查看地址(1)上面的列表，然后在讨论组(2)里边帖子里面找标题包含"Translation-team-zh-cn" 的帖子。如果已经有人在翻译，那么请挑选其他包，或者与前面的翻译人员协调，有的翻译人员已经确定失去联系了，那么你也可以接着翻译。
  * (1)http://translationproject.org/team/zh_CN.html
  * (2)http://groups.google.com/group/i18n-zh

2. 发文声明自己开始翻译。
> 你可以直接回复[讨论组(2)](http://groups.google.com/group/i18n-zh)上来自 TP-robot 的帖子。如果论坛上没有对应的帖子，那就直接发文声明，不过请在标题里包含软件包的名字。
**注意：对于 TP 项目的翻译，可以发送邮件至 <coordinator@translationproject.org>并抄送一份给现在的[TeamLeader](mailto:zhengyuji@gmail.com)。主题为 ask assignment of somefile，内容为你申请翻译的文件名（不带版本号）。但如果你真的要求了 assignment，则意味着除了你以外，其他任何人（TeamLeader 除外）以后都无法提交此文件的翻译。也就是说，你成了此包的专职翻译维护者:-)**

3. 下载pot或po文件。
> 你可以从链接[地址(1)](http://translationproject.org/team/zh_CN.html)里边的链接找到 pot 文件或 po 文件的下载地址。如果你连接[地址(1)](http://translationproject.org/team/zh_CN.html)存在问题的话，请直接[发电子邮件给我](mailto:zhengyuji@gmail.com)。我可以帮你下载 pot/po 文件，再发给你。如果你喜欢直接在 SVN 上编辑的话，可以在[讨论组(2)](http://groups.google.com/group/i18n-zh)上申请权限。SVN 指的是(3)，区别在于当你有了帐号以后，可以把 http 改成 https 连接进入。这样就有上传的权力了。有关在 windows 和 linux 下使用 svn 的方法，windows 的请看[TortoiseSVN快速指南](TortoiseSVN_Quick_Guide.md)。linux 下的请看 [svn日常使用](svneveryday.md)。
  * (3)http://i18n-zh.googlecode.com/svn/trunk/l10n/TP/

4. [从 pot 文件生成 po](GeneratePO.md)，[具体翻译](EditPoFilesWithVimOrEmacs.md)。
> 翻译时遇到的问题可以在[这里看看](QuestionAndAnswer.md)。
> 对于新手，推荐使用 poEdit 或者 KBabel 来翻译。
> 建议翻译时，每翻译一部分就进行检查。如果没用 vim/emacs 来翻译，则需要手工以 `msgfmt -cv filename -o /dev/null` 来检查。

5. 复查。
> 将你的翻译发在[讨论组(2)](http://groups.google.com/group/i18n-zh)上，特别是对你把握不大的部分可以具体说明，然后根据大家的反馈进行修改。我们建议复查的时间最好不要少于一周，但如果是基于前面的工作修改且修改的部分极小的话，可以考虑跳过此步。翻译过程中有的词拿捏不准的，可以先用 wikipedia 查一下。实在没把握的词，请打上“fuzzy”标记。
有关翻译的规范，请[详细查看此处的文档](http://people.ubuntu.com/~happyaron/l10n-guide-zh-chs.pdf)。以上文档如有变动，请及时关注[讨论组(2)](http://groups.google.com/group/i18n-zh)上的信息，或者直接发信求助于[讨论组(2)](http://groups.google.com/group/i18n-zh)

6. 用 tp-robot 进行提交。请先从[此处](http://translationproject.org/extra/sendpo.sh)得到 tp-robot 的提交脚本，它能简化你的工作。提交前请先将文件名改为 packagename-VERSION.zh\_CN.po。用
> `msgfmt -cv --statistic -o /dev/null your_file` 检查无误后再提交。
  * 提交命令为 /prefixpath/sendpo.sh packagename-VERSION.zh\_CN.po
> 至于要怎么样才算是“检查无误”，除了自己做好 msgfmt 以后，还要不要有什么特殊检查。来自[TP协调员的回信](envelope.md)给了我们很好的解释。
另一种提交的方法是自己以电子邮件直接向[robot@translationproject.org 机器人tp-robot]提交。请以主题“PACKAGENAME-VERSIONNUMBER.zh\_CN.po”，内容为空，packagename-VERSION.zh\_CN.po 为附件向[robot@translationproject.org 机器人tp-robot]提交。如果能用 gzip 压缩一下的话，更好。
**绝对不要直接将 po 文件的内容粘贴在邮件内容中发送！切记！**

一般十分钟左右，你就会收到 tp-robot 的回信，回信中会告诉你提交是否已经通过。如果未通过，请按照 tp-robot 所说的内容进行修改。你可以任何时间不限次数地提交你的翻译成果:-)
如果你一时没办法提交，可以选择下面所说的代理提交。

7. 代理提交。
> 作为 TeamLeader 我可以任意提交 po 文件，不论该文件是否已经被其他翻译人员占据。我会对你要求我提交的 po 文件用 msgfmt 做一些简单检查，如果检查合格就直接提交，这个时间一般不会很长，我尽量控制在 24 小时以内。但有如下的注意事项:
    * 我需要把 Last translator 更改为我的名字才能提交，不过你的名字会出现在文件头部的注释里边。(也需要把提交人员加到注释里边，尽管可能我一句都没翻译 :)
    * 通过我提交的话，版权已转让给 FSF，我默认你已经清楚这点。
    * 现有的提交人员就只有[zhengyuji@gmail.com 我TeamLeader]

8. 签署协议吗？
> 请参看[这里](http://translationproject.org/html/whydisclaim.html)，上面详细解释了原因和作法。如果不签这一份协议的话，请在[地址(1)](http://translationproject.org/team/zh_CN.html)中选择那些文件名下为浅绿色底的文件翻译，不要翻译那些文件名下为粉红色底的文件。看仔细点，我的笔记本上看不太清楚 :-)

9. 上游出新版 pot 了，怎么办？
> 请看[合并 po 部分](Merge.md)，只要看第一种情况即可。

10. 如果还有什么不清楚的，可以[发电子邮件给我](mailto:zhengyuji@gmail.com)，我愿意详细解释。我可以解释绝大多数你想问的问题。对这份流程有意见和建议的，请[给我留言](mailto:zhengyuji@gmail.com)

[回到新手指南](Newbie.md)