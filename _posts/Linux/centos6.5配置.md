```
yum groupinstall "Development tools"
```

Centos 5 默认的 gcc 版本为 4.1，某些软件在其上会编译不过，自己编译高版本的 gcc 可能也会遇到一些问题，比较麻烦。但有一个第三方库可以解决这个问题，即 `devtoolset`。devtoolset 有很多版本，例如 devtoolset-2(gcc-4.8.2)、devtoolset-3(gcc-4.9.2)、devtoolset-4(gcc-5.2.1)。

```
yum install zlib-devel
yum install bzip2-devel
yum install openssl-devel
yum install ncurses-devel
yum install sqlite-devel
```

```
cd /opt
wget --no-check-certificate https://www.python.org/ftp/python/2.7.9/Python-2.7.9.tar.xz
tar xf Python-2.7.9.tar.xz
cd Python-2.7.9
```

编辑安装

```
./configure --prefix=/usr/local
make && make altinstall
```

将python命令指向Python 2.7.9

```
ln -s /usr/local/bin/python2.7 /usr/local/bin/python
```

检查Python版本

```
sh
sh-4.1# python -V
Python 2.7.9
```

# 配置Pip：

```
# cd /usr/local/src
# wget "https://pypi.python.org/packages/source/p/pip/pip-1.5.4.tar.gz#md5=834b2904f92d46aaa333267fb1c922bb" --no-check-certificate
```

```
如果提示：-bash: wget: command not found
那么安装wget，执行如下：
# yum -y install wget 

解夺安装pip
# tar -xzvf pip-1.5.4.tar.gz
# cd pip-1.5.4
# python setup.py install
```

```
如果安装报下面的错：
Traceback (most recent call last):
  File "setup.py", line 6, in <module>
    from setuptools import setup, find_packages
ImportError: No module named setuptools

那么就要先安装setuptools包
(1)下载setuptools包
# wget http://pypi.python.org/packages/source/s/setuptools/setuptools-2.0.tar.gz
(2)解压setuptools包
# tar zxvf setuptools-2.0.tar.gz
# cd setuptools-2.0
(3)编译setuptools
# python setup.py build
(4)开始执行setuptools安装
# python setup.py install

安装完成setuptools包后，在重新执行：
# cd /usr/local/src/pip-1.5.4
# python setup.py install
至此pip安装完成
```