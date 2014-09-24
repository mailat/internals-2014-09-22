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

- cp device/generic/goldfish/init.goldfish.rc device/marakana/alpha/init.goldfish.rc
- cp device/generic/goldfish/ueventd.goldfish.rc device/marakana/alpha/goldfish.ueventd.goldfish.rc
- cp device/generic/goldfish/fstab.goldfish device/marakana/alpha/fstab.goldfish

Step 2

- cp prebuilts/qemu-kernel/x86/kernel-qemu device/marakana/alpha/kernel

Step 3

- in device/marakana/alpha/BoardConfig.mk
- change to TARGET_NO_KERNEL := false

Step 4
- in  device/marakana/alpha/common.mk change to 

# Enable our custom kernel
LOCAL_KERNEL := $(MY_PATH)/kernel
PRODUCT_COPY_FILES += $(LOCAL_KERNEL):kernel

# Copy our init and ueventd configuration files to the root
# file system (ramdisk.img -> boot.img)
- PRODUCT_COPY_FILES += $(MY_PATH)/init.goldfish.rc:root/init.goldfish.rc
- PRODUCT_COPY_FILES += $(MY_PATH)/ueventd.goldfish.rc:root/ueventd.goldfish.rc
- PRODUCT_COPY_FILES += $(MY_PATH)/fstab.goldfish:root/fstab.goldfish

- work further on ShanghaiWeather with a ListActivity
- use the url: http://api.openweathermap.org/data/2.5/weather?q=Shanghai,en&units=metric
- create 2 button on the MainActivity and redirect to ForecastActivity.java
- ForecastActivity.java will extend a ListActivity and please use the example project "06_ListView", class SimpleListActivity.java
