Linux kernel 4.19.90 for phytium FT-1500a. Can boot with grub by loading grub.efi in mksh.

Need uboot mkimage to generate bootable image:
* mkimage -A arm64 -O linux -T kernel -a 0x80080000 -e 0x80080000 -d Image uImage

Boot args are:
* video=radeonfb fbcon=font:7x14 console=tty0 console=ttyAMA0 console=ttyS0,115200 root=/dev/ram rdinit=/sbin/init earlycon=uart8250,mmio32,0x28000000,115200n8 KEYBOARDTYPE=pc KEYTABLE=us maxcpus=4 selinux=0

Initramfs is provided in BOOT.zip in releases.

Current status:
* Almost everything beside video card works. Radeon driver can detect the card, but end up with PCI ROM error. Trying to fix.
