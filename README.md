# Installation-of-Lucene
Instructions for installation of lucene library in ubuntu and centos
## Installing Dependencies.
### On Ubuntu
Update ubuntu and install java ( java 8 recomended ),ant, gcc, g++.
If gcc and g++ are installed then skip installing them. 

```bash
--------update--------
$ apt-get update && apt-get upgrade
$ apt-get install software-properties-common

--------java--------
$ add-apt-repository ppa:webupd8team/java
$ apt-get update
$ apt-get install oracle-java8-installer

--------ant (if not installed)--------
$ sudo apt-get install ant

------gcc (if not installed)-----
$ sudo apt install gcc
$ sudo apt install build-essential
$ gcc --version
```

### On centos
Installing java, gcc, ant, ivy.

```bash
--------java--------
$ wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u161-b12/2f38c3b165be4555a1fa6e98c45e0808/jdk-8u161-linux-x64.rpm"
$ sudo yum install jdk-8u161-linux-x64.rpm
$ rmjdk-8u161-linux-x64.rpm

--------gcc--------
$ sudo yum install gcc-c++
$ sudo yum install python-devel

--------ant and ivy--------
$ sudo yum install ant
$ yum install apache-ivy
```

# Installing Lucene
  ## On Ubuntu and Centos
  Download lucene (change download url to download different version)
  ```bash
   $ wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://www-eu.apache.org/dist/lucene/pylucene/pylucene-4.10.1-1-src.tar.gz"
  ```
  Extract (chage filename appropriately)
  ```bash
  $ tar -xvzf pylucene-4.10.1-1-src.tar.gz
  ```
  - Set $JAVA_HOME environment variable accordingly. ( modify/set in ~/.bashrc file )
  - Edit jcc/setup.py to match you environment
  - Edit Makefile to match your environment


  ```bash
  $ pushd jcc
  <edit setup.py to match your environment>
  $ python setup.py build
  $ sudo python setup.py install
  popd
  <edit Makefile to match your environment>
  $ make
  $ make test (look for failures)
  $ sudo make install
  ```

  ## Test installation
  ```bash
  $ python
  > import lucene
  > from java.io import File
  > from org.apache.lucene.util import Version
  > from org.apache.lucene.store import SimpleFSDirectory
  ```
  You have successfully installed Lucene if not errors.
  
  ## Reference
  - Installing java on ubuntu [( https://thishosting.rocks/install-java-ubuntu/ ) ](https://thishosting.rocks/install-java-ubuntu/)
  - Installing java on Centos [( https://gist.github.com/skanjo/f07d2d873b3413a6c6bd )](https://gist.github.com/skanjo/f07d2d873b3413a6c6bd)
  - Installing Lucene [( http://lucene.apache.org/pylucene/install.html )](http://lucene.apache.org/pylucene/install.html)
  - Uninstalling java on ubuntu [( https://askubuntu.com/questions/84483/how-to-completely-uninstall-java )](https://askubuntu.com/questions/84483/how-to-completely-uninstall-java)
  
