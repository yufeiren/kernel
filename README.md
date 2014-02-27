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

Compile and Install
-------------------

* move source code into /usr/src/

* make menuconfig

* make

# make modules_install install


check /boot/grub/grub.conf

root/kernel/initrd


Process
-------

Process descriptor: circular doubly linked list, 
in <linux/sched.h>  
struct task_struct {
...
/* open file information */
        struct files_struct *files;
...
}

fork: Copy-on-Write
duplication of resources occurs only when they are written.

fork/vfork/__clone() --call--> do_fork() in kernel/fork.c




Error
-----

sh /home/ren/kernel/linux-2.6.34.15/arch/x86/boot/install.sh 2.6.34.15 arch/x86/boot/bzImage \
		System.map "/boot"
E: Missing a shared library required by /usr/lib64/plymouth//renderers/drm.so.
E: Run "ldd /usr/lib64/plymouth//renderers/drm.so" to find out what it is.
E: dracut cannot create an initrd.
ERROR: modinfo: could not find module nf_defrag_ipv6
ERROR: modinfo: could not find module iscsi_boot_sysfs
ERROR: modinfo: could not find module cxgb4i
ERROR: modinfo: could not find module mlx5_ib
ERROR: modinfo: could not find module mlx5_core
ERROR: modinfo: could not find module compat
ERROR: modinfo: could not find module knem

check: ldd /usr/lib64/plymouth//renderers/drm.so

	libpciaccess.so.0 => not found


yum install libpciaccess libpciaccess-devel

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

