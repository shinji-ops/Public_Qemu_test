
how to excute qemu system

qemu-system-arm -M versatilepb -m 128M -kernel arch/arm/boot/zImage  -append "console=ttyAMA0 mem=128M root=/dev/ram0 rdinit=/bin/sh"  -dtb arch/arm/boot/dts/versatile-pb.dtb -initrd ../busybox-1.34.1/rootfs -nographic

Linux 
make versatile_defconfig



cd busybox-1.34.1/
make defconfig
make
make install

make etc/init.d/rcS
make etc/inittab

find . | cpio -o --format=newc > ../rootfs

