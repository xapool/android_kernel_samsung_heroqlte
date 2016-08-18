################################################################################

1. How to Build
	- get Toolchain
		From android git server , codesourcery and etc ..
		 - aarch64-linux-android-4.9

	- make output folder
		EX)OUTPUT_DIR=out
		$ mkdir out

	- edit Makefile
		edit "CROSS_COMPILE" to right toolchain path(You downloaded).
		  EX)  CROSS_COMPILE= $(android platform directory you download)/android/prebuilt/linux-x86/aarch64/aarch64-linux-android-4.9/bin/aarch64-linux-android-
          Ex)  CROSS_COMPILE=/usr/local/toolchain/aarch64-linux-android-4.9/bin/aarch64-linux-android-          // check the location of toolchain
  	
		$ export ARCH=arm64
		$ export SEC_BUILD_OPTION_HW_REVISION=02
		$ make -C $(pwd) O=$(pwd)/out KCFLAGS=-mno-android heroqlte_chnzc_defconfig
		$ make -C $(pwd) O=$(pwd)/out KCFLAGS=-mno-android

2. Output files
	- Kernel : out/arch/arm64/boot/Image
	- module : out/drivers/*/*.ko

3. How to Clean	
		Change to OUTPUT_DIR folder
		EX) $(pwd)/out
		$ make clean

4. How to disable security check

* [Disable TIMA RKP and KNOX KAP ](https://github.com/jcadduono/nethunter_kernel_herolte/commit/a332ead550aea9b9ee2f40a06eccd6a68898ad37)
* [Disable TIMA, Trusted UI, KNOX KAP, and Root Restrictions ](https://github.com/jcadduono/nethunter_kernel_herolte/commit/4343966efe129d7ac52378811452dc4ebbba3ed2)
* [compile a permissive SELinux kernel?](http://forum.xda-developers.com/google-nexus-5/devs-only/correct-to-compile-permissive-selinux-t3074761)
* [Compiling a permissive Android kernel](http://graemehill.ca/compiling-permissive-android-kernel/)
* [selinux enforce/permissive patch ](https://github.com/Tkkg1994/SuperKernel/commit/ab9d79d4c386fcd099381e52afbdee4c816a8874)
################################################################################
