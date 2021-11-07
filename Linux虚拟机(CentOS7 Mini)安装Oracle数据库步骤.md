# Linux虚拟机(CentOS7 Mini)安装Oracle 19c数据库步骤

```
选择Oracle 19c的原因是因为相比于11G等，19c提供了RPM安装，更方便--不用自己去创建用户组，用户等
```

## 准备工作

(1).下载oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm

```
如何安装oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm?
腾讯云推荐：https://yum.oracle.com/repo/OracleLinux/OL7/latest/x86_64/index.html
可以到上述网址找自己需要下载的rpm包
方式1.Window直接访问http://yum.oracle.com/repo/OracleLinux/OL7/latest/x86_64/getPackage/oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm,自动下载rpm包
```

(2).下载oracle-database-ee-19c-1.0-1.x86_64.rpm

```
官方网址:https://www.oracle.com/database/technologies/oracle-database-software-downloads.html#19c
选择Linux版本 X86-64的RPM下载
```

(3).将以上2个rpm文件复制到Linux虚拟机上面

```
可以通过WinSCP软件上传到Linux虚拟机上面
```

## 开始安装

(1).安装oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm

```
yum -y install oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm
通过安装oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm可以自动修改Linun内核参数，添加oinstall,dba用户，用户组等相关准备工作
```

(2).安装oracle-database-ee-19c-1.0-1.x86_64.rpm

```
yum -y install oracle-database-ee-19c-1.0-1.x86_64.rpm
```

## 创建一个数据库（需要保证数据空间足够大）

```
/etc/init.d/oracledb_ORCLCDB-19c configure
```

## 添加环境变量(修改Linux系统的/etc/profile文件)

```
export ORACLE_BASE=/opt/oracle
export ORACLE_HOME=/opt/oracle/product/19c/dbhome_1
export ORACLE_SID=ORCLCDB
export PATH=$ORACLE_HOME/bin:$PATH:$HOME/.local/bin:$HOME/bin
```

此时便可以执行sqlplus指令进行sql面板了(继续处理数据库的问题...)

````
````

