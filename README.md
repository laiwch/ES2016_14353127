### About DOL

- Description
  
- How to install
  操作系统：使用在虚拟机VMware上安装的Ubuntu 14.04
  1. 安装必要的环境：
         $ sudo apt-get updata
         $ sudo apt-get install ant
         $ sudo apt-get install openjdk-7-jdk
         $ sudo apt-get install unzip
     
  2. 下载文件
         $ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
         $ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
     
  3. 解压文件
     新建dol的文件夹
         $ mkdir dol
     将dol_ethz.zip解压到dol文件夹中
         $ unzip dol_ethz.zip -d dol
     解压systemc
         $ tar -zxvf systemc-2.3.1.tgz
     
  4. 编译systemc
     解压后进入systemc-2.3.1的目录下
         $ cd systemc-2.3.1
      新建一个临时文件夹objdir
         $ mkdir objdir
     进入该文件夹objdir
          $ cd objdir
      运行configure（根据系统的环境设置一下参数，用于编译）
          $ ../configure CXX=g++ --disable-async-undates
     
     编译
         $ sudo make install
     
     记录当前的工作路径
         $ pwd
     
  5. 编译dol
     进入刚刚dol的文件夹
         $ cd ../dol
     修改build_zip.xml文件
     

- Experimental experience
  
