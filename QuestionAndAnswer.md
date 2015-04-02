[返回新手指南](Newbie.md)
## 简介 ##
这份东西的目的是帮助新手解决在编辑 po 文件时的常见问题。以下内容全以 Q＆A 的形式出现。欢迎有人对此进行补充。
## 常见错误(Q&A) ##
  * Q:Desktop/zh\_CN.po:158: 'msgid' and 'msgstr`[`1`]`' entries do not both end with '\n'
原文如下：
```
    #: driver.c:819
    #, c-format
    msgid "fetchlimit %d reached; %d message left on server %s account %s\n"
    msgid_plural ""
    "fetchlimit %d reached; %d messages left on server %s account %s\n"
    msgstr[0] "达到收件上限 %d；%d 邮件留在了服务器 %s 帐号为 %s\n"
    msgstr[1] ""
```
> > 我已经文件头中把 "Plural-Forms: nplurals=INTEGER; plural=EXPRESSION;\n" 改成了"Plural-Forms: nplurals=1; plural=0;\n"，但还是出现这种错误。不是改好以后就只取 msgstr`[`0`]`中的翻译吗？msgstr`[`1`]` 是用不着的啊。
**A:的确，msgstr`[`1`]`是用不着了，请把 msgstr`[`1`]` "" 删掉**

---


  * Q:Desktop/zh\_CN.po:164: 'msgstr' is not a valid C format string, unlike 'msgid'. Reason: In the directive number 1, the character '$' is not a valid conversion specifier.
原文如下：
```
  #: driver.c:876
  #, c-format
  msgid "timeout after %d seconds waiting to connect to server %s.\n"
  msgstr "在等待连接服务器 %$2s %$1d 秒后超时\n"
```
> > 这里我想交换两个字符串的位置。但出错了，为什么？
**A:是 %2$s %1$d，而不是 %$2s。请特别注意 ‘$’ 和 ‘2’ 的位置关系！**


---

  * Q:我在 emacs 中用了 po-mode.el，快捷键

&lt;DEL&gt;

 可以让我加上 fuzzy 标记。但我按 DEL 键没什么效果啊，为什么？
**A：这是由于 DEL 键一般被映射为其它键值，用**

&lt;backspace&gt;

 即“退格键”。它一般被映射为 DEL 键的键值**---

  * Q:我用 sendpo.sh 提交翻译时，被拒收(Rejected)，回信中老是出现以下字样
```
     The copyright for the PO file should be assigned to excactly:
               Eric S. Raymond (msgids)
```
> > 但我可以保证，我绝对没有更改过 po 文件头部的版权声明。这是怎么回事？**

**A：这的确是个非常令人不爽的问题！请在 Eric S. Raymond 的后面加上 (msgids)。注意空格！其实目前一共有8个这样的软件。它们是：**


> 

&lt;domain&gt;

ant-phone
> > 

&lt;potcopyright&gt;

Roland Stigge (msgids)

> 

&lt;domain&gt;

doodle
> > 

&lt;potcopyright&gt;

Christian Grothoff (msgids)

> 

&lt;domain&gt;

e2fsprogs
> > 

&lt;potcopyright&gt;

Theodore Tso (msgids)

> 

&lt;domain&gt;

fetchmail
> > 

&lt;potcopyright&gt;

Eric S. Raymond (msgids)

> 

&lt;domain&gt;

flex
> > 

&lt;potcopyright&gt;

The Flex Project (msgids)

> 

&lt;domain&gt;

gettext-examples

&lt;package&gt;

gettext
> > 

&lt;potcopyright&gt;

Yoyodyne, Inc. (msgids)

> 

&lt;domain&gt;

gtick
> > 

&lt;potcopyright&gt;

Roland Stigge (msgids)

> 

&lt;domain&gt;

man-db
> > 

&lt;potcopyright&gt;

Colin Watson (msgids)

[返回新手指南](Newbie.md)