Android Internals Shanghai - 22 September 2014

Marius Mailat - Appsrise.com, marius.mailat@gmail.com


Homework Day 1

- compile the platform using > time make and follow the instruction on page 212-218
- modify the name of the Browser app from Browser to "{yourname} Browser" for the chinese locales

Homework Day 2

- use the instructions on page 220 in the course to have the library and the binary created

Homework Day 3

- use the instructions on page 219 for having a custom kernel
- use the instructions on page 221 for adding a custom daemon and have it in the init.goldfish.rc added

For Kernel use the bellow instructions:

Step 1

cp device/generic/goldfish/init.goldfish.rc device/marakana/alpha/init.goldfish.rc
cp device/generic/goldfish/ueventd.goldfish.rc device/marakana/alpha/goldfish.marakanaalphaboard.rc
cp device/generic/goldfish/fstab.goldfish device/marakana/alpha/fstab.goldfish

Step 2

cp prebuilts/qemu-kernel/x86/kernel-qemu device/marakana/alpha/kernel

Step 3

in device/marakana/alpha/BoardConfig.mk
…
TARGET_NO_KERNEL := false