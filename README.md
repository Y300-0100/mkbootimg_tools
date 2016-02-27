mkbootimg_tools
===============

### Unpack and repack boot.img,support dtb(dt.img):
		darkside@darkside-MS-7592:~$ cd /home/darkside/mkbootimg_tools-master
		darkside@darkside-MS-7592:~/mkbootimg_tools-master$ ./mkboot recovery.img ksuamg5
		Unpack & decompress recovery.img to ksuamg5
		kernel         : kernel
		ramdisk        : ramdisk
		page size      : 2048
		kernel size    : 11808344
		ramdisk size   : 605289
		base           : 0x00000800
		kernel offset  : 0x00008000
		ramdisk offset : 0x01000000
		tags offset    : 0x00000100
		cmd line       : init=/sbin/init root=/dev/ram rw initrd=0x11000000,16M console=ttyDCC0 mem=88M
		ramdisk is gzip format.
		Unpack completed.
		darkside@darkside-MS-7592:~/mkbootimg_tools-master$ ./mkboot ksuamg5 recovery.img
		mkbootimg from ksuamg5/img_info.
		kernel         : kernel
		ramdisk        : new_ramdisk
		page size      : 2048
		kernel size    : 11808344
		ramdisk size   : 605238
		base           : 0x00000800
		kernel offset  : 0x00008000
		ramdisk offset : 0x01000000
		tags offset    : 0x00000100
		cmd line       : init=/sbin/init root=/dev/ram rw initrd=0x11000000,16M console=ttyDCC0 mem=88M
		ramdisk is gzip format.
		Kernel size: 11808344, new ramdisk size: 605238, recovery.img: 12417024.
		recovery.img has been created.
		darkside@darkside-MS-7592:~/mkbootimg_tools-master$ 
		...

### Create a dt.img:
		xiaolu@xiaolu-ubuntu64:/media/diskd/kernel/SHV-E330S_JB_Opensource/Kernel$ scripts/dtbTool -s 2048 -o arch/arm/boot/dt.img -p scripts/dtc/ arch/arm/boot/
		DTB combiner:
		  Input directory: '/media/diskd/kernel/SHV-E330S_JB_Opensource/Kernel/arch/arm/boot/'
		  Output file: '/media/diskd/kernel/SHV-E330S_JB_Opensource/Kernel/arch/arm/boot/dt.img'
		Found file: msm8974-sec-ks01-r03.dtb ... chipset: 2114015745, platform: 3, rev: 0
		Found file: msm8974-sec-ks01-r07.dtb ... chipset: 2114015745, platform: 7, rev: 0
		Found file: msm8974-sec-ks01-r06.dtb ... chipset: 2114015745, platform: 6, rev: 0
		Found file: msm8974-sec-ks01-r04.dtb ... chipset: 2114015745, platform: 4, rev: 0
		Found file: msm8974-sec-ks01-r11.dtb ... chipset: 2114015745, platform: 11, rev: 0
		Found file: msm8974-sec-ks01-r02.dtb ... chipset: 2114015745, platform: 2, rev: 0
		Found file: msm8974-sec-ks01-r00.dtb ... chipset: 2114015745, platform: 0, rev: 0
		Found file: msm8974-sec-ks01-r05.dtb ... chipset: 2114015745, platform: 5, rev: 0
		Found file: msm8974-sec-ks01-r01.dtb ... chipset: 2114015745, platform: 1, rev: 0
		=> Found 9 unique DTB(s)

		Generating master DTB... completed


### dtbToolCM support dt-tag & dtb v2/3(https://github.com/CyanogenMod/android_device_qcom_common/tree/cm-13.0/dtbtool):

 	dtbToolCM -s 2048 -d "htc,project-id = <" -o arch/arm/boot/dt.img -p scripts/dtc/ arch/arm/boot/

