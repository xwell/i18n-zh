#
# $Id$
#

# 概述 #

随着 OpenLDAP 的流行，我们迫切需要一个 Windows 平台的发行版本。
然而现在我们能找到的版本很古老，是 2.2.29：

  * [openldap-2.2.29-db-4.3.29-openssl-0.9.8a-win32\_Setup.exe](http://download.bergmans.us/openldap/openldap-2.2.29/openldap-2.2.29-db-4.3.29-openssl-0.9.8a-win32_Setup.exe)
  * [openldap-2.2.29-db-4.3.29-openssl-0.9.8a-BDB\_ONLY-win32\_Setup.exe](http://download.bergmans.us/openldap/openldap-2.2.29/openldap-2.2.29-db-4.3.29-openssl-0.9.8a-BDB_ONLY-win32_Setup.exe)

现在 OpenLDAP 2.4 已经是生产适用版本了，很多新的 Linux 发行版本都开始采用
OpenLDAP 2.4 系列。

所以有需要、有兴趣、有能力的我就针对 32 位 Windows 平台构建了 OpenLDAP 2.4.10，
与大家共享。

# 下载地址 #
  * [OpenLDAP 2.4.10 for 32 bit Windows](http://i18n-zh.googlecode.com/files/openldap-2.4.10-w32-2.tar.gz)
  * [OpenLDAP 2.4.10 for 32 bit Windows (PGP signature )](http://i18n-zh.googlecode.com/files/openldap-2.4.10-w32-2.tar.gz.asc)

**说明**：
  * 我没有兴趣，也没有时间将它做成安装包，需要大家手工配置。如果有人有兴趣，无限欢迎。
  * 将下载的安装包解压后，按照下节的说明，配置后运行。

# 运行环境 #
## slapd.conf ##
配置文件 slapd.conf 中使用了相对路径，这在大多数情况下是正确的，
你也可以使用绝对路径。

## 注册表中的参数 ##
**注意**：
  * 你只需要让注册表中的参数 ConfigFile 指定配置文件 slapd.conf 的位置即可。
  * 注册表中的参数会**覆盖**配置文件中的参数！

**说明**：
  * 一般无需配置参数 DebugLevel (它覆盖配置文件 slapd.conf 的参数 loglevel)。
  * 如果不需要修改端口，或者想只监听限定的 IP 地址，那么也不必配置参数 Urls。
  * 参数 ConfigFile 指定了配置文件 slapd.conf 的位置，下面的例子用的是相对于 slapd.exe 的路径，你也可以使用绝对路径。

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\OpenLDAP\Parameters]
"DebugLevel"=dword:00004120
"ConfigFile"="./slapd.conf"
"Urls"="ldap://:389/"
```

## 安装为 Windows 服务 ##
**注意**：
你必须先在注册表中增加参数 ConfigFile，指定配置文件 slapd.conf 的位置。

## 安装服务 ##
```
C:\usr\openldap-2.4\libexec>slapd install OpenLDAP-slapd "OpenLDAP Directory Service" auto
The install path is C:\usr\openldap-2.4\libexec\slapd.exe.
service has been installed ...
```

## 启动服务 ##
```
C:\usr\openldap-2.4\libexec>net start OpenLDAP-slapd
OpenLDAP Directory Service 服务正在启动 .
OpenLDAP Directory Service 服务已经启动成功。
```

## 停止服务 ##
```
C:\usr\openldap-2.4\libexec>net stop OpenLDAP-slapd
OpenLDAP Directory Service 服务正在停止.
OpenLDAP Directory Service 服务已成功停止。
```

## 删除服务 ##
```
C:\usr\openldap-2.4\libexec>slapd remove OpenLDAP-slapd
The installed path is C:\usr\openldap-2.4\libexec\slapd.exe.
service has been removed ...
```


# 构建环境 #
这里不讲述构建方法，只说明构建依赖的软件包。

需要自行编译的软件包：
  * OpenLDAP 2.4.10 (Jun 11, 2008)
  * Berkeley DB 4.6.21 (September 27, 2007, With patchs from Debian lenny)
  * libiconv 1.11.1 (December 10, 2007)
  * zlib 1.2.3 (With patchs from Debian lenny)
  * OpenSSL 0.9.8h (May 28, 2008)

从 MinGW 下载的软件包：
  * MinGW 5.1.4
  * MSYS 1.0.10 + MSYS Base System 1.0.11
  * mingw-libgnurx-2.5.1
  * binutils-2.18.50-20080109-2.tar.gz
  * gcc-core-3.4.5-20060117-3.tar.gz
  * gcc-g++-3.4.5-20060117-3.tar.gz
  * mingw32-make-3.81-2.tar.gz
  * mingw-runtime-3.14.tar.gz
  * w32api-3.11.tar.gz

从 GnuWin32 下载的软件包：
  * groff-1.19.2

从 Cygwin 下载的软件包：
  * cygwin-1.5.25-14.tar.bz2 (cygpath only)

从 ActiveState 下载的软件包：
  * ActivePerl-5.10.0.1003-MSWin32-x86-285500.zip