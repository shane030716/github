# Goal: Install or update latest Git on a CentOS

Situation: Git is installed in our server, but it's version 1.7.\*. 
I wanted to upgrade to the latest 2.10.0 version, but `yum install git` tells me it's update to date for 1.7.*.

So I am going to follow **Installing from Source** in the [official Git website](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). All comments can be found in the official website. I will just write down the commands here

Login in as super user

```
yum install curl-devel expat-devel gettext-devel openssl-devel perl-devel zlib-devel
yum install asciidoc xmlto
```
The following is mentioned in the document but the command was not provided
```
yum -y --enablerepo=*epel* install docbook2X
```
```
yum install docbook2X
ln -s /usr/bin/db2x_docbook2texi /usr/bin/docbook2x-texi

tar -zxf git-2.10.0.tar.gz
cd git-2.10.0
make configure
./configure --prefix=/usr
make all doc info
make install install-doct install-html install-info
```

Check version
```
git --version
```

*(Need to know how to uninstall it and set up server)*
