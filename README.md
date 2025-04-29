# RV1103 Linux Micro Development Board

Essential NON obvious steps for getting installing the RV1103 Linux Micro Development Board:

https://www.luckfox.com/EN-Luckfox-Pico-Plus

![image](https://github.com/user-attachments/assets/6da35e83-3856-4d30-8884-4c2dd1e89cfc)



## TLDR
See https://forums.luckfox.com/viewtopic.php?t=1765

## Installation Steps

1.  **Download "Ubuntu_Luckfox_Pico_Plus_MicroSD_250313.zip" from https://drive.google.com/drive/folders/ ... s1y9xcMG0S

2.  Unzip into  to /tmp/ or some other directory of your choosing.
    cd /tmp/
    unzip Ubuntu_Luckfox_Pico_Plus_MicroSD_250313.zip
3. Get an sd card ....

4. Use blkenvflash to created your SD Card
   (See https://github.com/LuckfoxTECH/luckfox-pico/issues/129)    

$ sudo python3 blkenvflash /dev/sda
[sudo] password:
<snip warnings>
== bl.py 0.0.1 ==
writing to /dev/sda
mmcblk1: env.img size:32,768/32K (offset:0/0B) imgsize:32,768 (32K)
mmcblk1: idblock.img size:524,288/512K (offset:32,768/32K) imgsize:188,416 (184K)
mmcblk1: uboot.img size:262,144/256K (offset:0/0B) imgsize:262,144 (256K)
mmcblk1: boot.img size:33,554,432/32M (offset:0/0B) imgsize:3,150,336 (3,150,336B)
mmcblk1: oem.img size:536,870,912/512M (offset:0/0B) imgsize:113,909,760 (111,240K)
mmcblk1: userdata.img size:268,435,456/256M (offset:0/0B) imgsize:9,999,360 (9,765K)
mmcblk1: rootfs.img size:6,442,450,944/6G (offset:0/0B) imgsize:1,136,914,432 (1,110,268K)
done.

5.  Put sd card into Pico Plus
    Like this:

6. Plug RV1103_LuckFox_PicoPlus into USB-C 

7. Attach USB to Serial:
   Like this

8. Run lsusfb / ls
$ lsusb | grep -i z
Bus 001 Device 102: ID 2207:0019 Fuzhou Rockchip Electronics Company rk3xxx

$ ls -l /dev/ttyUSB0
crw-rw---- 1 root dialout 188, 0 Apr 28 22:39 /dev/ttyUSB0

9. Run GTKterm w/8 1 N/115200 as per:
https://wiki.luckfox.com/Luckfox-Pico/Luckfox-Pico-RV1103/Luckfox-Pico-Plus-Mini/Luckfox-Pico-Login-UART/

## Gotchas and Troubleshooting

  * **Power Issues:** Ensure a stable 5V power supply.
  * **Make sure the SD card is tight and aligned** 
  * **Make sure the Serial TX/RX pins are correctly setup **

## Help Forum and Resources

  * **Luckfox Forum:** [forums.luckfox.com](https://forums.luckfox.com/)
  
This README provides a starting point. Always refer to the official documentation and community forums for the most up-to-date information.
