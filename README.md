# Painless-R-compilation-and-installation-on-Ubuntu
Compiling R involves installing tons of dependencies, though there are many documents on the internet instructing you how to achieve it, they are kind of outdated. If you are a lazy guy as me and tired to search for the dependencies of R. This is the right recipe for you. Run the commands at a terminal and you will have all the ingredients ready.

Currently the code has been tested on Ubuntu 18.04.3 LTS. R version :4.0 devel (2019-12-06 r77536). If you like it, please contribute to this project by providing your test result.

# Mandatory packages
```
sudo apt-get install build-essential fort77 xorg-dev liblzma-dev libblas-dev gfortran -y
sudo apt-get install gcc-multilib gobjc++ aptitude -y
sudo apt-get install libreadline-dev -y
sudo apt-get install libbz2-dev -y
sudo apt-get install libpcre2-dev -y
sudo apt-get install libcurl4 libcurl4-openssl-dev -y
sudo apt-get install default-jre -y
sudo apt-get install default-jdk -y
sudo apt-get install openjdk-8-jdk openjdk-8-jre -y 
```
All in one
```
sudo apt-get install build-essential fort77 xorg-dev liblzma-dev libblas-dev gfortran gcc-multilib gobjc++ aptitude libreadline-dev libbz2-dev libpcre2-dev libcurl4 libcurl4-openssl-dev default-jre default-jdk openjdk-8-jdk openjdk-8-jre -y
```

# Optional packages
## For the recommended packages
Go to the top-level directory of the R sources, run
```
./tools/rsync-recommended
```

## For building documents
```
sudo apt-get install texinfo -y
sudo apt-get install texlive -y
sudo apt-get install texlive-fonts-extra -y
```
All in one
```
sudo apt-get install texinfo texlive texlive-fonts-extra -y
```

# If you are as lazy as a sloth
Unzip R source file into a folder and open your terminal at this folder:
## Export JAVA path
R requires a java path to find the include header. This is my personal setting, I am not sure if it will work for all system.
```
## Export a global environment for R to find the java path
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
```

## Compile without documents 
```
./configure --enable-R-shlib --without-recommended-packages
make
make check
sudo make install
```

## Compile With documents
```
./configure --enable-R-shlib --without-recommended-packages
make
make check
make pdf
make info
sudo make install
sudo make install-info
sudo make install-pdf
```


# `devtools` package dependencies
```
sudo apt-get install libssl-dev -y
sudo apt-get install libxml2-dev -y 
```
All in one
```
sudo apt-get install libssl-dev libxml2-dev -y
```



## Key words for search
These are the error message you will see if your system does not meet one or more dependence requirement

1. checking whether bzip2 support suffices… configure: error: bzip2 library and headers are required

2. Either pcre >= 8.32 or pcre2 library and headers are required

3. error: --with-readline=yes (default) and headers/libs are not available

4. WARNING: you cannot build PDF versions of the R manuals

5. WARNING: neither inconsolata.sty nor zi4.sty found: PDF vignettes and package manuals will not be rendered optimally

