### About DOL

* Description

  ​	The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

  ​

  ​

  ​

* How to install

  操作系统：使用在虚拟机VMware上安装的Ubuntu 14.04

  0. 安装必要的环境：

     ~~~
     $ sudo apt-get updata
     $ sudo apt-get install ant
     $ sudo apt-get install openjdk-7-jdk
     $ sudo apt-get install unzip
     ~~~

     ​

  1. 下载文件

     ~~~
     $ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
     $ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
     ~~~

     ​

  2. 解压文件

     新建dol的文件夹

     ~~~
     $ mkdir dol
     ~~~

     将dol_ethz.zip解压到dol文件夹中

     ~~~
     $ unzip dol_ethz.zip -d dol
     ~~~

     解压systemc

     ~~~
     $ tar -zxvf systemc-2.3.1.tgz
     ~~~

     ​

  3. 编译systemc

     解压后进入systemc-2.3.1的目录下

     ~~~
     $ cd systemc-2.3.1
     ~~~

      新建一个临时文件夹objdir

     ~~~
     $ mkdir objdir
     ~~~

     进入该文件夹objdir

     ~~~
      $ cd objdir
     ~~~

      运行configure（根据系统的环境设置一下参数，用于编译）

     ~~~
      $ ../configure CXX=g++ --disable-async-undates
     ~~~

     ![image](https://github.com/laiwch/ES2016_14353127/raw/master/image_install/1.jpg)

     上图为运行configure之后的截图

     ​

     编译

     ~~~
     $ sudo make install
     ~~~

     编译完后文件目录如下图：

     ![image](https://github.com/laiwch/ES2016_14353127/raw/master/image_install/2.jpg)

     ​

     记录当前的工作路径

     ~~~
     $ pwd
     ~~~

     ![image](http://github.com/laiwch/ES2016_14353127/raw/master/image_install/3.jpg)

     ​

  4. 编译dol

     进入刚刚dol的文件夹

     ~~~
     $ cd ../dol
     ~~~

     修改build_zip.xml文件

     找到显示编译的systemc位置在哪的如下一段话：

     ~~~
     <property name="systemc.inc" value="YYY/include"/>
     <property name="systemc.lib" value="YYY/lib-linux64/libsystemc.a"/>
     ~~~

     YYY要改成pwd的结果，即"/home/conc/ES/systemc-2.3.1"，注意：lib-linux64对应的是64位系统，32位写lib-linux

     然后编译

     ~~~
     $ ant -f build_zip.xml all
     ~~~

     成功显示build successful

     ![image](https://github.com/laiwch/ES2016_14353127/raw/master/image_install/4.jpg)

     接着运行第一个例子：

     进入build/bin/main路径下

     ~~~
     $ cd build/bin/main
     ~~~

     运行第一个例子

     ~~~
     $ ant -f runexample.xml -Dnumber=1
     ~~~

     成功结果如下图：

     ![image](https://github.com/laiwch/ES2016_14353127/raw/master/image_install/5.jpg)

     ​


* Experimental experience

  ​