kernel
======

boot
----
http://www.osdever.net/bkerndev/Docs/basickernel.htm

xv6
---
http://pdos.csail.mit.edu/6.828/2012/xv6.html

kernel janitors
---------------
http://kernelnewbies.org/KernelJanitors


Linux Kernel Development
------------------------

make config
make menuconfig
make defconfig

make -j [# of parallel jobs]


printk

make modules_install


my kernel test version
----------------------

centos 6.5

http://mirror.rackspace.com/CentOS/6.5/isos/x86_64/

http://irtfweb.ifa.hawaii.edu/~denault/notes/linux-compiling_kernels.html

# make clean
# make mrproper
# make oldconfig    -> generate a .config file based on the running kernel
# make bzImage
# make modules
# make modules_install
# make install     


