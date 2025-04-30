# j7eltetmo-3.10.108-kernel


This variant of the j7 was a #$&!@ to get the sources completely working without errors. I almost gave up but thanks to @prashantpaddune for his quantum kernel sources: https://github.com/Quantum-kernel/Quantum-kernel-G610x
Also a big thanks to @daishi4u for his Afterburner kernel sources: https://github.com/daishi4u/AB_7.1.1

I originally used linaro GCC 7.5.0 but was plagued with random reboots. That got old real quick since this phone is my daily driver. 
I finally got my kernel image stable with no random reboots using GCC 8.x UBERTC: https://bitbucket.org/matthewdalex/aarch64-linux-android-8.x/src/master/

EDIT the Makefile accordingly and set your environment up and you should be good to go. 
export TMPDIR=/path/to/sources/out
make clean
make mrproper 
make ARCH=arm64 CROSS_COMPILE=/path/to /toolchain/bin/executable (don't forget the -) j7eltetmo_defconfig it'll warn about dangling pointer in symbol.c, ignore it unless you know how to fix it. 
make Image ARCH=arm64 CROSS_COMPILE=/path/to /toolchain/bin/executable (don't forget the -) -j$(nproc) 
Image will be in arch/arm64/boot folder use stock boot.img-dt 

Enjoy, this has brought new life to my j7
BTW this is setup to have as little SELINUX/TIMA/KNOX/SECURITY as possible so you have to edit quite a bit of files to re-enable.

I will not help you re-enable that functionality. 
