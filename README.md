# Painless-R-compilation-and-installation-on-Ubuntu
Compiling R involves installing tons of dependencies, though there are many documents on the internet instructing you how to achieve it, they are kind of outdated. If you are a lazy guy as me and tired to search for the dependencies of R. This is the right receipt for you. Run the commands at a terminal and you will have all the ingredients ready.

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
```

# Optional packages
## For bilding documents
```
sudo apt-get install texinfo -y
sudo apt-get install texlive -y
sudo apt-get install texlive-fonts-extra -y
```

# If you are as lazy as a sloth
Unzip R source file into a folder and open your terminal at this folder:
## Compile without documents 
```
./configure
make
make check
sudo make install
```

## Compile With documents
```
./configure
make
make check
make pdf
make info
sudo make install
sudo make install-info
sudo make install-pdf
```




