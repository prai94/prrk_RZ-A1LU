Google docs
https://docs.google.com/document/d/1w8GyxMWnA_x7lYa58piy5L2TIFpZt8YwVmeIJ8Zt2W8/edit?usp=sharing

Host machine: Ubuntu 18.04
Clone git repo:
git clone https://github.com/renesas-rz/rza_linux-4.19_bsp.git
cd rza_linux-4.19_bsp

Pull u-boot and kernel sources:
./build.sh update u
./build.sh update k

Issue config command and setup Stream it board:
./build.sh config

Get buildroot for root file system(rootfs):
./build.sh buildroot

Build u-boot:
./build.sh u-boot


Build Kernel and Device tree:
./build.sh kernel xipImage
./build.sh kernel dtbs

Board Mod:
Remove resistor R1 located on the top of the board.

Download Jlink from https://www.segger.com/downloads/jlink/
Install JLink as sudo
Install cutecom as sudo: sudo apt-get install cutecom\
Connect USB cables to stream-it board and Jlink pod.
Launch Cutecom: cutecom &
Select port ‘/dev/ttyACM0’, baud 115200.

Download u-boot directly to serial flash
sudo ./build.sh jlink u-boot

Download device tree directly to serial flash
sudo ./build.sh jlink dtb

Download kernel to RAM
sudo ./build.sh jlink xipImage

Flash downloaded kernel to flash by issuing below command in cutecom console
sf probe 0 ; sf erase 200000 500000 ; sf write 0c000000 200000 500000

Download rootfs to RAM
sudo ./build.sh jlink rootfs_axfs

Flash downloaded rootfs to flash by issuing below command in cutecom console
sf probe 0 ; sf erase 00800000 C00000 ; sf write 0x0C000000 00800000 C00000

Issue below command to boot the kernel
run xsa_boot

You should be seeing login console. Login creds: root




Link to create 
https://www.datacamp.com/tutorial/git-push-pull 



./serio.py -s /home/priyank/Downloads/Ren_stream_it/License_JlinkSDK.txt -d /tmp/ -p /dev/ttyACM0


copy thru serial interface
https://github.com/renesas-rz/rza_linux-4.19_bsp/tree/master/hello_world






if write to RAM fails use 



AfterResetTarget() end - Took 8.29ms
Downloading file [/tmp/u-boot.bin]...
J-Link: Flash download: Bank 0 @ 0x18000000: 1 range affected (262144 bytes)
J-Link: Flash download: Total: 3.801s (Prepare: 0.166s, Compare: 0.541s, Erase: 0.570s, Program & Verify: 2.367s, Restore: 0.155s)
J-Link: Flash download: Program & Verify speed: 107 KB/s
O.K.
J-Link>loadbin /tmp/r7s72100-streamit.dtb.bin,0x180C0000
'loadbin': Performing implicit reset & halt of MCU.
AfterResetTarget() start
AfterResetTarget() end - Took 8.59ms
Downloading file [/tmp/r7s72100-streamit.dtb.bin]...
J-Link: Flash download: Bank 0 @ 0x18000000: Skipped. Contents already match
O.K.
J-Link>loadbin /tmp/xipImage.bin,0x18200000
'loadbin': Performing implicit reset & halt of MCU.
AfterResetTarget() start
AfterResetTarget() end - Took 8.75ms
Downloading file [/tmp/xipImage.bin]...
J-Link: Flash download: Bank 0 @ 0x18000000: 1 range affected (4063232 bytes)
J-Link: Flash download: Total: 64.988s (Prepare: 0.082s, Compare: 8.101s, Erase: 9.795s, Program & Verify: 46.854s, Restore: 0.155s)
J-Link: Flash download: Program & Verify speed: 84 KB/s
O.K.
J-Link>loadbin /tmp/rootfs.axfs.bin,0x18800000
'loadbin': Performing implicit reset & halt of MCU.
AfterResetTarget() start
AfterResetTarget() end - Took 8.70ms
Downloading file [/tmp/rootfs.axfs.bin]...
J-Link: Flash download: Bank 0 @ 0x18000000: 1 range affected (9109504 bytes)
J-Link: Flash download: Total: 145.384s (Prepare: 0.078s, Compare: 18.057s, Erase: 21.975s, Program & Verify: 105.117s, Restore: 0.154s)
J-Link: Flash download: Program & Verify speed: 84 KB/s
O.K.
J-Link>



debugging uboot

JLinkGDBServer -speed 15000 -device R7S721001

build-gdb/z_install/bin/arm-buildroot-linux-uclibcgnueabi-gdb

(gdb) file /home/priyank/Downloads/Ren_stream_it/rza_linux-4.19_bsp/output/u-boot-2017.05/u-boot
A program is being debugged already.
Are you sure you want to change the file? (y or n) y
Reading symbols from /home/priyank/Downloads/Ren_stream_it/rza_linux-4.19_bsp/output/u-boot-2017.05/u-boot...done.
(gdb) b reset 
Breakpoint 1 at 0x180002e8: file arch/arm/cpu/armv7/start.S, line 40.
(gdb) ^Cquit


debugging running kernel 

(gdb) file /home/priyank/Downloads/Ren_stream_it/rza_linux-4.19_bsp/output/linux-4.19/vmlinux
A program is being debugged already.
Are you sure you want to change the file? (y or n) y
Load new symbol table from "/home/priyank/Downloads/Ren_stream_it/rza_linux-4.19_bsp/output/linux-4.19/vmlinux"? (y or n) y
Reading symbols from /home/priyank/Downloads/Ren_stream_it/rza_linux-4.19_bsp/output/linux-4.19/vmlinux...done.


(gdb) b sysfs_get_uname
Breakpoint 3 at 0xbf837d70: file kernel/time/clocksource.c, line 1075.
(gdb) c
Continuing.
^C
Program received signal SIGTRAP, Trace/breakpoint trap.
cpu_v7_do_idle () at arch/arm/mm/proc-v7.S:81
81		ret	lr
(gdb) b sys_execve
Breakpoint 4 at 0xbf87e724: file fs/exec.c, line 1964.
(gdb) c
Continuing.

Breakpoint 4, __se_sys_execve (filename=832524, argv=832464, envp=832476) at fs/exec.c:1964
1964		return do_execve(getname(filename), argv, envp);
(gdb) bt
#0  __se_sys_execve (filename=832524, argv=832464, envp=832476) at fs/exec.c:1964
#1  0xbf801000 in __idmap_text_end ()
Backtrace stopped: previous frame identical to this frame (corrupt stack?)
(gdb) frame 1
#1  0xbf801000 in __idmap_text_end ()
(gdb) frame 2
#0  0x00000000 in ?? ()
(gdb) frame 3
#0  0x00000000 in ?? ()
(gdb) frame 0
#0  __se_sys_execve (filename=832524, argv=832464, envp=832476) at fs/exec.c:1964
1964		return do_execve(getname(filename), argv, envp);
