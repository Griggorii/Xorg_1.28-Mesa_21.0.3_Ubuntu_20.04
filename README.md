# Xorg_1.28-Mesa_21.0.3_Ubuntu_20.04
Mesa+Xorg full my build , ubuntu 20.04 , libc-2.31 , (dri new libgallium_drv_video , libmesa_dri_drivers) (vdpau libvdpau_gallium), wayland speed fast +50% , mesa proc self build , libmesa_dri build flag cpp_std=c++2a module , BT709 , IEC61966_2_1 , RGB , FULL

             Ubuntu 20.04 special edition video driver architect Griggorii update old xorg generate 1.20.4 fix fast ui chrome/um resize page F11 11.03.2021

Download mesa+xorg new videodriver: https://github.com/Griggorii/Xorg_1.28-Mesa_21.0.3_Ubuntu_20.04/releases/tag/libmesa_dri

Development xorg: sudo cp libwayland-server.la /usr/lib/x86_64-linux-gnu

Deb kernel recomendation support all nvidia , touchpad , zfs , bbswitch: https://github.com/Griggorii/linux-image-unsigned-5.6.0-1020-oem-kernel-mod-rpm-deb/releases/tag/linux-image-unsigned-5.6.0-1020-fedora

Test run video driver chromium/chrome/opera/brave/and analog engine browser replace (chromium-browser) flag: https://github.com/Griggorii/Chromium_OS_77


Informations all developers /usr/include/X11/Xlib.h a lot of duplicate functions and repeated slightly altered lines that roughly provide the same duplicate functions and the library needs to be redirected



                         ________________________________________________
                        |                                                |
                        | Test fbdev new video driver architect Griggorii|
                        |_______________________________________________ |


The text of the settings on the Internet page FBDEV is not correctly displayed. Downloads readme.md to see the correct settings and correct setting copy alternative raw page https://raw.githubusercontent.com/Griggorii/Xorg_1.28-Mesa_23.0.1_libmesa_dri_Ubuntu_20.04/main/README.md 

Monitor support 60-75 hz replace string  (VertRefresh 60-75) example support  monitor 110-120 hz ? , danger experiment monitor not support blackscreen (VertRefresh 110-120)

$ cat << EOF > xorg.conf
Section "Device"
	Identifier "Configured Video Device"
	Driver "fbdev"
EndSection

Section "Module"
    Load "dbe"
    Load "ddc"
    Load "extmod"
    Load "glx"
    Load "int10"
    Load "record"
    Load "vbe"
    Load "glamoregl"
    Load "xorgxrdp"
    Load "fb"
EndSection

Section "Monitor"
    Identifier "Monitor"
    Option "DPMS"
    HorizSync 30-80
    VertRefresh 60-75
    ModeLine "1920x1080" 138.500 1920 1968 2000 2080 1080 1083 1088 1111 +hsync -vsync
    ModeLine "1280x720" 74.25 1280 1720 1760 1980 720 725 730 750 +HSync +VSync
    Modeline "1368x768" 72.25 1368 1416 1448 1528 768 771 781 790 +hsync -vsync
    Modeline "1600x900" 119.00 1600 1696 1864 2128 900 901 904 932 -hsync +vsync
EndSection

Section "Monitor"
    Identifier "Video Card (fbdev)"
    Driver "fbdev"
    Option "DRMDevice" "/dev/dri/renderD128"
    Option "DRI3" "1"
EndSection

Section "Screen"
    Identifier "Screen (fbdev)"
    Device "Video Card (fbdev)"
    Monitor "Monitor"
    DefaultDepth 24
    SubSection "Display"
        Depth 24
        Modes "640x480" "800x600" "1024x768" "1280x720" "1280x1024" "1600x900" "1920x1080"
    EndSubSection
EndSection
EOF

$ sudo mkdir /etc/X11/xorg.conf.d

$ sudo cp xorg.conf /etc/X11/xorg.conf.d/

_______________________________________________________________________________________________________________________________________________________________

                                    Test xorg.conf log /etc/X11/xorg.conf.d
				    
Correct text click raw page proview https://raw.githubusercontent.com/Griggorii/Xorg_1.28-Mesa_23.0.1_libmesa_dri_Ubuntu_20.04/main/README.md				    
							   
[  3394.609] (--) Log file renamed from "/home/griggorii/.local/share/xorg/Xorg.pid-21294.log" to "/home/griggorii/.local/share/xorg/Xorg.0.log"
[  3394.610] 
X.Org X Server 1.20.11
X Protocol Version 11, Revision 0
[  3394.610] Build Operating System: linux Ubuntu
[  3394.610] Current Operating System: Linux griggoriix64 5.6.0-1020-oem #20 SMP Tue Aug 25 21:54:15 +08 2020 x86_64
[  3394.610] Kernel command line: BOOT_IMAGE=/boot/vmlinuz-5.6.0-1020-oem root=UUID=703ad232-aaac-438f-a2c3-554cd1e68f7e ro quiet splash vt.handoff=7
[  3394.610] Build Date: 11 September 2021  05:21:10PM
[  3394.610] xorg-server 2:1.20.11-1ubuntu1~20.04.2 (For technical support please see http://www.ubuntu.com/support) 
[  3394.610] Current version of pixman: 0.38.4
[  3394.610] 	Before reporting problems, check http://wiki.x.org
	to make sure that you have the latest version.
[  3394.610] Markers: (--) probed, (**) from config file, (==) default setting,
	(++) from command line, (!!) notice, (II) informational,
	(WW) warning, (EE) error, (NI) not implemented, (??) unknown.
[  3394.610] (==) Log file: "/home/griggorii/.local/share/xorg/Xorg.0.log", Time: Mon Oct 11 16:54:31 2021
[  3394.612] (==) Using system config directory "/usr/share/X11/xorg.conf.d"
[  3394.614] (==) No Layout section.  Using the first Screen section.
[  3394.614] (==) No screen section available. Using defaults.
[  3394.614] (**) |-->Screen "Default Screen Section" (0)
[  3394.614] (**) |   |-->Monitor "<default monitor>"
[  3394.615] (==) No monitor specified for screen "Default Screen Section".
	Using a default monitor configuration.
[  3394.615] (==) Automatically adding devices
[  3394.615] (==) Automatically enabling devices
[  3394.615] (==) Automatically adding GPU devices
[  3394.615] (==) Automatically binding GPU devices
[  3394.615] (==) Max clients allowed: 256, resource mask: 0x1fffff
[  3394.615] (WW) The directory "/usr/share/fonts/X11/cyrillic" does not exist.
[  3394.615] 	Entry deleted from font path.
[  3394.615] (WW) The directory "/usr/share/fonts/X11/100dpi/" does not exist.
[  3394.615] 	Entry deleted from font path.
[  3394.615] (WW) The directory "/usr/share/fonts/X11/75dpi/" does not exist.
[  3394.615] 	Entry deleted from font path.
[  3394.615] (WW) The directory "/usr/share/fonts/X11/Type1" does not exist.
[  3394.615] 	Entry deleted from font path.
[  3394.615] (WW) The directory "/usr/share/fonts/X11/100dpi" does not exist.
[  3394.615] 	Entry deleted from font path.
[  3394.615] (WW) The directory "/usr/share/fonts/X11/75dpi" does not exist.
[  3394.615] 	Entry deleted from font path.
[  3394.615] (==) FontPath set to:
	/usr/share/fonts/X11/misc,
	built-ins
[  3394.615] (==) ModulePath set to "/usr/lib/xorg/modules"
[  3394.615] (II) The server relies on udev to provide the list of input devices.
	If no devices become available, reconfigure udev or disable AutoAddDevices.
[  3394.615] (II) Loader magic: 0x55e118cac020
[  3394.615] (II) Module ABI versions:
[  3394.615] 	X.Org ANSI C Emulation: 0.4
[  3394.615] 	X.Org Video Driver: 24.1
[  3394.615] 	X.Org XInput driver : 24.1
[  3394.615] 	X.Org Server Extension : 10.0
[  3394.619] (++) using VT number 2

[  3394.622] (II) systemd-logind: took control of session /org/freedesktop/login1/session/_35
[  3394.624] (II) xfree86: Adding drm device (/dev/dri/card0)
[  3394.625] (II) systemd-logind: got fd for /dev/dri/card0 226:0 fd 12 paused 0
[  3394.630] (--) PCI:*(0@0:2:0) 8086:0116:1025:0649 rev 9, Mem @ 0xb3000000/4194304, 0xc0000000/268435456, I/O @ 0x00003000/64, BIOS @ 0x????????/131072
[  3394.630] (--) PCI: (1@0:0:0) 10de:1140:1025:068e rev 161, Mem @ 0xb2000000/16777216, 0xa0000000/268435456, 0xb0000000/33554432, I/O @ 0x00002000/128
[  3394.630] (II) LoadModule: "glx"
[  3394.631] (II) Loading /usr/lib/xorg/modules/extensions/libglx.so
[  3394.634] (II) Module glx: vendor="X.Org Foundation"
[  3394.634] 	compiled for 1.20.8, module version = 1.0.0
[  3394.634] 	ABI class: X.Org Server Extension, version 10.0
[  3394.635] (==) Matched modesetting as autoconfigured driver 0
[  3394.635] (==) Matched fbdev as autoconfigured driver 1
[  3394.635] (==) Matched vesa as autoconfigured driver 2
[  3394.635] (==) Assigned the driver to the xf86ConfigLayout
[  3394.635] (II) LoadModule: "modesetting"
[  3394.635] (II) Loading /usr/lib/xorg/modules/drivers/modesetting_drv.so
[  3394.636] (II) Module modesetting: vendor="X.Org Foundation"
[  3394.636] 	compiled for 1.20.11, module version = 1.20.11
[  3394.636] 	Module class: X.Org Video Driver
[  3394.636] 	ABI class: X.Org Video Driver, version 24.1
[  3394.636] (II) LoadModule: "fbdev"
[  3394.637] (II) Loading /usr/lib/xorg/modules/drivers/fbdev_drv.so
[  3394.638] (II) Module fbdev: vendor="X.Org Foundation"
[  3394.638] 	compiled for 1.20.1, module version = 0.5.0
[  3394.638] 	Module class: X.Org Video Driver
[  3394.638] 	ABI class: X.Org Video Driver, version 24.0
[  3394.638] (II) LoadModule: "vesa"
[  3394.638] (II) Loading /usr/lib/xorg/modules/drivers/vesa_drv.so
[  3394.640] (II) Module vesa: vendor="X.Org Foundation"
[  3394.640] 	compiled for 1.20.4, module version = 2.4.0
[  3394.640] 	Module class: X.Org Video Driver
[  3394.640] 	ABI class: X.Org Video Driver, version 24.0
[  3394.640] (II) modesetting: Driver for Modesetting Kernel Drivers: kms
[  3394.640] (II) FBDEV: driver for framebuffer: fbdev
[  3394.640] (II) VESA: driver for VESA chipsets: vesa
[  3394.641] xf86EnableIOPorts: failed to set IOPL for I/O (Operation not permitted)
[  3394.641] (II) modeset(0): using drv /dev/dri/card0
[  3394.641] (WW) Falling back to old probe method for fbdev
[  3394.641] (II) Loading sub module "fbdevhw"
[  3394.641] (II) LoadModule: "fbdevhw"
[  3394.641] (II) Loading /usr/lib/xorg/modules/libfbdevhw.so
[  3394.644] (II) Module fbdevhw: vendor="X.Org Foundation"
[  3394.644] 	compiled for 1.20.11, module version = 0.0.2
[  3394.644] 	ABI class: X.Org Video Driver, version 24.1
[  3394.644] (EE) open /dev/fb0: Permission denied
[  3394.644] (WW) VGA arbiter: cannot open kernel arbiter, no multi-card support
[  3394.644] (II) modeset(0): Creating default Display subsection in Screen section
	"Default Screen Section" for depth/fbbpp 24/32
[  3394.644] (==) modeset(0): Depth 24, (==) framebuffer bpp 32
[  3394.644] (==) modeset(0): RGB weight 888
[  3394.644] (==) modeset(0): Default visual is TrueColor
[  3394.644] (II) Loading sub module "glamoregl"
[  3394.644] (II) LoadModule: "glamoregl"
[  3394.644] (II) Loading /usr/lib/xorg/modules/libglamoregl.so
[  3394.653] (II) Module glamoregl: vendor="X.Org Foundation"
[  3394.653] 	compiled for 1.20.11, module version = 1.0.1
[  3394.653] 	ABI class: X.Org ANSI C Emulation, version 0.4
[  3394.691] (II) modeset(0): glamor X acceleration enabled on Mesa DRI Intel(R) HD Graphics 3000 (SNB GT2)
[  3394.691] (II) modeset(0): glamor initialized
[  3394.691] (II) modeset(0): Output LVDS-1 has no monitor section
[  3394.693] (II) modeset(0): Output VGA-1 has no monitor section
[  3394.694] (II) modeset(0): Output HDMI-1 has no monitor section
[  3394.694] (II) modeset(0): Output DP-1 has no monitor section
[  3394.709] (II) modeset(0): EDID for output LVDS-1
[  3394.709] (II) modeset(0): Manufacturer: LGD  Model: 2dc  Serial#: 0
[  3394.709] (II) modeset(0): Year: 2010  Week: 0
[  3394.709] (II) modeset(0): EDID Version: 1.3
[  3394.709] (II) modeset(0): Digital Display Input
[  3394.709] (II) modeset(0): Max Image Size [cm]: horiz.: 34  vert.: 19
[  3394.709] (II) modeset(0): Gamma: 2.20
[  3394.709] (II) modeset(0): No DPMS capabilities specified
[  3394.710] (II) modeset(0): Supported color encodings: RGB 4:4:4 YCrCb 4:4:4 
[  3394.710] (II) modeset(0): First detailed timing is preferred mode
[  3394.710] (II) modeset(0): redX: 0.623 redY: 0.369   greenX: 0.346 greenY: 0.610
[  3394.710] (II) modeset(0): blueX: 0.148 blueY: 0.098   whiteX: 0.313 whiteY: 0.329
[  3394.710] (II) modeset(0): Manufacturer's mask: 0
[  3394.710] (II) modeset(0): Supported detailed timing:
[  3394.710] (II) modeset(0): clock: 70.0 MHz   Image Size:  344 x 194 mm
[  3394.710] (II) modeset(0): h_active: 1366  h_sync: 1402  h_sync_end 1450 h_blank_end 1492 h_border: 0
[  3394.710] (II) modeset(0): v_active: 768  v_sync: 771  v_sync_end 776 v_blanking: 782 v_border: 0
[  3394.710] (II) modeset(0):  LG Display
[  3394.710] (II) modeset(0):  LP156WH4-TLA1
[  3394.710] (II) modeset(0): EDID (in hex):
[  3394.710] (II) modeset(0): 	00ffffffffffff0030e4dc0200000000
[  3394.710] (II) modeset(0): 	00140103802213780aa9059f5e589c26
[  3394.710] (II) modeset(0): 	19505400000001010101010101010101
[  3394.710] (II) modeset(0): 	010101010101581b567e50000e302430
[  3394.710] (II) modeset(0): 	350058c2100000190000000000000000
[  3394.710] (II) modeset(0): 	00000000000000000000000000fe004c
[  3394.710] (II) modeset(0): 	4720446973706c61790a2020000000fe
[  3394.710] (II) modeset(0): 	004c503135365748342d544c41310079
[  3394.710] (II) modeset(0): Printing probed modes for output LVDS-1
[  3394.710] (II) modeset(0): Modeline "1366x768"x60.0   70.00  1366 1402 1450 1492  768 771 776 782 -hsync -vsync (46.9 kHz eP)
[  3394.710] (II) modeset(0): Modeline "1360x768"x59.8   84.75  1360 1432 1568 1776  768 771 781 798 -hsync +vsync (47.7 kHz d)
[  3394.710] (II) modeset(0): Modeline "1360x768"x60.0   72.00  1360 1408 1440 1520  768 771 781 790 +hsync -vsync (47.4 kHz d)
[  3394.711] (II) modeset(0): Modeline "1280x720"x120.0  156.12  1280 1376 1512 1744  720 721 724 746 doublescan -hsync +vsync (89.5 kHz d)
[  3394.711] (II) modeset(0): Modeline "1280x720"x120.0  120.75  1280 1304 1320 1360  720 721 724 740 doublescan +hsync -vsync (88.8 kHz d)
[  3394.711] (II) modeset(0): Modeline "1280x720"x59.9   74.50  1280 1344 1472 1664  720 723 728 748 -hsync +vsync (44.8 kHz d)
[  3394.711] (II) modeset(0): Modeline "1280x720"x59.7   63.75  1280 1328 1360 1440  720 723 728 741 +hsync -vsync (44.3 kHz d)
[  3394.711] (II) modeset(0): Modeline "1024x768"x120.1  133.47  1024 1100 1212 1400  768 768 770 794 doublescan -hsync +vsync (95.3 kHz d)
[  3394.711] (II) modeset(0): Modeline "1024x768"x60.0   65.00  1024 1048 1184 1344  768 771 777 806 -hsync -vsync (48.4 kHz d)
[  3394.711] (II) modeset(0): Modeline "960x720"x120.0  117.00  960 1024 1128 1300  720 720 722 750 doublescan -hsync +vsync (90.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "928x696"x120.1  109.15  928 976 1088 1264  696 696 698 719 doublescan -hsync +vsync (86.4 kHz d)
[  3394.711] (II) modeset(0): Modeline "896x672"x120.0  102.40  896 960 1060 1224  672 672 674 697 doublescan -hsync +vsync (83.7 kHz d)
[  3394.711] (II) modeset(0): Modeline "1024x576"x119.9   98.50  1024 1092 1200 1376  576 577 580 597 doublescan -hsync +vsync (71.6 kHz d)
[  3394.711] (II) modeset(0): Modeline "1024x576"x119.9   78.38  1024 1048 1064 1104  576 577 580 592 doublescan +hsync -vsync (71.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "1024x576"x59.9   46.50  1024 1064 1160 1296  576 579 584 599 -hsync +vsync (35.9 kHz d)
[  3394.711] (II) modeset(0): Modeline "1024x576"x59.8   42.00  1024 1072 1104 1184  576 579 584 593 +hsync -vsync (35.5 kHz d)
[  3394.711] (II) modeset(0): Modeline "960x600"x119.9   96.62  960 1028 1128 1296  600 601 604 622 doublescan -hsync +vsync (74.6 kHz d)
[  3394.711] (II) modeset(0): Modeline "960x600"x120.0   77.00  960 984 1000 1040  600 601 604 617 doublescan +hsync -vsync (74.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "960x540"x119.9   86.50  960 1024 1124 1288  540 541 544 560 doublescan -hsync +vsync (67.2 kHz d)
[  3394.711] (II) modeset(0): Modeline "960x540"x120.0   69.25  960 984 1000 1040  540 541 544 555 doublescan +hsync -vsync (66.6 kHz d)
[  3394.711] (II) modeset(0): Modeline "960x540"x59.6   40.75  960 992 1088 1216  540 543 548 562 -hsync +vsync (33.5 kHz d)
[  3394.711] (II) modeset(0): Modeline "960x540"x59.8   37.25  960 1008 1040 1120  540 543 548 556 +hsync -vsync (33.3 kHz d)
[  3394.711] (II) modeset(0): Modeline "800x600"x120.0   81.00  800 832 928 1080  600 600 602 625 doublescan +hsync +vsync (75.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "800x600"x60.3   40.00  800 840 968 1056  600 601 605 628 +hsync +vsync (37.9 kHz d)
[  3394.711] (II) modeset(0): Modeline "800x600"x56.2   36.00  800 824 896 1024  600 601 603 625 +hsync +vsync (35.2 kHz d)
[  3394.711] (II) modeset(0): Modeline "840x525"x120.0   73.12  840 892 980 1120  525 526 529 544 doublescan -hsync +vsync (65.3 kHz d)
[  3394.711] (II) modeset(0): Modeline "840x525"x119.8   59.50  840 864 880 920  525 526 529 540 doublescan +hsync -vsync (64.7 kHz d)
[  3394.711] (II) modeset(0): Modeline "864x486"x59.9   32.50  864 888 968 1072  486 489 494 506 -hsync +vsync (30.3 kHz d)
[  3394.711] (II) modeset(0): Modeline "864x486"x59.6   30.50  864 912 944 1024  486 489 494 500 +hsync -vsync (29.8 kHz d)
[  3394.711] (II) modeset(0): Modeline "800x512"x120.3   51.56  800 800 828 832  512 512 514 515 doublescan +hsync +vsync (62.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "700x525"x120.0   61.00  700 744 820 940  525 526 532 541 doublescan +hsync +vsync (64.9 kHz d)
[  3394.711] (II) modeset(0): Modeline "800x450"x119.9   59.12  800 848 928 1056  450 451 454 467 doublescan -hsync +vsync (56.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "800x450"x119.6   48.75  800 824 840 880  450 451 454 463 doublescan +hsync -vsync (55.4 kHz d)
[  3394.711] (II) modeset(0): Modeline "640x512"x120.0   54.00  640 664 720 844  512 512 514 533 doublescan +hsync +vsync (64.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "720x450"x119.8   53.25  720 760 836 952  450 451 454 467 doublescan -hsync +vsync (55.9 kHz d)
[  3394.711] (II) modeset(0): Modeline "700x450"x119.9   51.75  700 740 812 924  450 451 456 467 doublescan -hsync +vsync (56.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "700x450"x119.8   43.25  700 724 740 780  450 451 456 463 doublescan +hsync -vsync (55.4 kHz d)
[  3394.711] (II) modeset(0): Modeline "640x480"x120.0   54.00  640 688 744 900  480 480 482 500 doublescan +hsync +vsync (60.0 kHz d)
[  3394.711] (II) modeset(0): Modeline "640x480"x59.9   25.18  640 656 752 800  480 490 492 525 -hsync -vsync (31.5 kHz d)
[  3394.711] (II) modeset(0): Modeline "720x405"x59.5   22.50  720 744 808 896  405 408 413 422 -hsync +vsync (25.1 kHz d)
[  3394.711] (II) modeset(0): Modeline "720x405"x59.0   21.75  720 768 800 880  405 408 413 419 +hsync -vsync (24.7 kHz d)
[  3394.711] (II) modeset(0): Modeline "684x384"x119.8   42.62  684 720 788 892  384 385 390 399 doublescan -hsync +vsync (47.8 kHz d)
[  3394.712] (II) modeset(0): Modeline "684x384"x119.7   36.12  684 708 724 764  384 385 390 395 doublescan +hsync -vsync (47.3 kHz d)
[  3394.712] (II) modeset(0): Modeline "680x384"x119.6   42.38  680 716 784 888  384 385 390 399 doublescan -hsync +vsync (47.7 kHz d)
[  3394.712] (II) modeset(0): Modeline "680x384"x119.9   36.00  680 704 720 760  384 385 390 395 doublescan +hsync -vsync (47.4 kHz d)
[  3394.712] (II) modeset(0): Modeline "640x400"x119.8   41.75  640 676 740 840  400 401 404 415 doublescan -hsync +vsync (49.7 kHz d)
[  3394.712] (II) modeset(0): Modeline "640x400"x120.0   35.50  640 664 680 720  400 401 404 411 doublescan +hsync -vsync (49.3 kHz d)
[  3394.712] (II) modeset(0): Modeline "576x432"x120.1   40.81  576 608 668 760  432 432 434 447 doublescan -hsync +vsync (53.7 kHz d)
[  3394.712] (II) modeset(0): Modeline "640x360"x119.7   37.25  640 672 736 832  360 361 364 374 doublescan -hsync +vsync (44.8 kHz d)
[  3394.712] (II) modeset(0): Modeline "640x360"x119.7   31.88  640 664 680 720  360 361 364 370 doublescan +hsync -vsync (44.3 kHz d)
[  3394.712] (II) modeset(0): Modeline "640x360"x59.8   18.00  640 664 720 800  360 363 368 376 -hsync +vsync (22.5 kHz d)
[  3394.712] (II) modeset(0): Modeline "640x360"x59.3   17.75  640 688 720 800  360 363 368 374 +hsync -vsync (22.2 kHz d)
[  3394.712] (II) modeset(0): Modeline "512x384"x120.0   32.50  512 524 592 672  384 385 388 403 doublescan -hsync -vsync (48.4 kHz d)
[  3394.712] (II) modeset(0): Modeline "512x288"x120.0   23.25  512 532 580 648  288 289 292 299 doublescan -hsync +vsync (35.9 kHz d)
[  3394.712] (II) modeset(0): Modeline "512x288"x119.8   21.00  512 536 552 592  288 289 292 296 doublescan +hsync -vsync (35.5 kHz d)
[  3394.712] (II) modeset(0): Modeline "480x270"x119.3   20.38  480 496 544 608  270 271 274 281 doublescan -hsync +vsync (33.5 kHz d)
[  3394.712] (II) modeset(0): Modeline "480x270"x119.6   18.62  480 504 520 560  270 271 274 278 doublescan +hsync -vsync (33.3 kHz d)
[  3394.712] (II) modeset(0): Modeline "400x300"x120.6   20.00  400 420 484 528  300 300 302 314 doublescan +hsync +vsync (37.9 kHz d)
[  3394.712] (II) modeset(0): Modeline "400x300"x112.7   18.00  400 412 448 512  300 300 301 312 doublescan +hsync +vsync (35.2 kHz d)
[  3394.712] (II) modeset(0): Modeline "432x243"x119.8   16.25  432 444 484 536  243 244 247 253 doublescan -hsync +vsync (30.3 kHz d)
[  3394.712] (II) modeset(0): Modeline "432x243"x119.1   15.25  432 456 472 512  243 244 247 250 doublescan +hsync -vsync (29.8 kHz d)
[  3394.712] (II) modeset(0): Modeline "320x240"x120.1   12.59  320 328 376 400  240 245 246 262 doublescan -hsync -vsync (31.5 kHz d)
[  3394.712] (II) modeset(0): Modeline "360x202"x119.0   11.25  360 372 404 448  202 204 206 211 doublescan -hsync +vsync (25.1 kHz d)
[  3394.712] (II) modeset(0): Modeline "360x202"x118.3   10.88  360 384 400 440  202 204 206 209 doublescan +hsync -vsync (24.7 kHz d)
[  3394.712] (II) modeset(0): Modeline "320x180"x119.7    9.00  320 332 360 400  180 181 184 188 doublescan -hsync +vsync (22.5 kHz d)
[  3394.712] (II) modeset(0): Modeline "320x180"x118.6    8.88  320 344 360 400  180 181 184 187 doublescan +hsync -vsync (22.2 kHz d)
[  3394.716] (II) modeset(0): EDID for output VGA-1
[  3394.718] (II) modeset(0): EDID for output HDMI-1
[  3394.718] (II) modeset(0): EDID for output DP-1
[  3394.718] (II) modeset(0): Output LVDS-1 connected
[  3394.718] (II) modeset(0): Output VGA-1 disconnected
[  3394.718] (II) modeset(0): Output HDMI-1 disconnected
[  3394.718] (II) modeset(0): Output DP-1 disconnected
[  3394.718] (II) modeset(0): Using exact sizes for initial modes
[  3394.718] (II) modeset(0): Output LVDS-1 using initial mode 1366x768 +0+0
[  3394.718] (==) modeset(0): Using gamma correction (1.0, 1.0, 1.0)
[  3394.718] (==) modeset(0): DPI set to (96, 96)
[  3394.718] (II) Loading sub module "fb"
[  3394.718] (II) LoadModule: "fb"
[  3394.718] (II) Loading /usr/lib/xorg/modules/libfb.so
[  3394.734] (II) Module fb: vendor="X.Org Foundation"
[  3394.734] 	compiled for 1.20.11, module version = 1.0.0
[  3394.734] 	ABI class: X.Org ANSI C Emulation, version 0.4
[  3394.734] (II) UnloadModule: "fbdev"
[  3394.734] (II) Unloading fbdev
[  3394.734] (II) UnloadSubModule: "fbdevhw"
[  3394.734] (II) Unloading fbdevhw
[  3394.734] (II) UnloadModule: "vesa"
[  3394.734] (II) Unloading vesa
[  3394.850] (==) modeset(0): Backing store enabled
[  3394.850] (==) modeset(0): Silken mouse enabled
[  3394.876] (II) modeset(0): Initializing kms color map for depth 24, 8 bpc.
[  3394.876] (==) modeset(0): DPMS enabled
[  3394.877] (II) modeset(0): [DRI2] Setup complete
[  3394.877] (II) modeset(0): [DRI2]   DRI driver: i965
[  3394.877] (II) modeset(0): [DRI2]   VDPAU driver: va_gl
[  3394.877] (II) Initializing extension Generic Event Extension
[  3394.877] (II) Initializing extension SHAPE
[  3394.878] (II) Initializing extension MIT-SHM
[  3394.878] (II) Initializing extension XInputExtension
[  3394.879] (II) Initializing extension XTEST
[  3394.879] (II) Initializing extension BIG-REQUESTS
[  3394.879] (II) Initializing extension SYNC
[  3394.880] (II) Initializing extension XKEYBOARD
[  3394.880] (II) Initializing extension XC-MISC
[  3394.880] (II) Initializing extension SECURITY
[  3394.880] (II) Initializing extension XFIXES
[  3394.881] (II) Initializing extension RENDER
[  3394.881] (II) Initializing extension RANDR
[  3394.882] (II) Initializing extension COMPOSITE
[  3394.882] (II) Initializing extension DAMAGE
[  3394.882] (II) Initializing extension MIT-SCREEN-SAVER
[  3394.883] (II) Initializing extension DOUBLE-BUFFER
[  3394.883] (II) Initializing extension RECORD
[  3394.883] (II) Initializing extension DPMS
[  3394.883] (II) Initializing extension Present
[  3394.883] (II) Initializing extension DRI3
[  3394.884] (II) Initializing extension X-Resource
[  3394.884] (II) Initializing extension XVideo
[  3394.884] (II) Initializing extension XVideo-MotionCompensation
[  3394.884] (II) Initializing extension SELinux
[  3394.884] (II) SELinux: Disabled on system
[  3394.884] (II) Initializing extension GLX
[  3394.907] (II) AIGLX: Loaded and initialized i965
[  3394.907] (II) GLX: Initialized DRI2 GL provider for screen 0
[  3394.907] (II) Initializing extension XFree86-VidModeExtension
[  3394.908] (II) Initializing extension XFree86-DGA
[  3394.908] (II) Initializing extension XFree86-DRI
[  3394.908] (II) Initializing extension DRI2
[  3394.912] (II) modeset(0): Damage tracking initialized
[  3394.913] (II) modeset(0): Setting screen physical size to 361 x 203
[  3395.005] (II) config/udev: Adding input device Power Button (/dev/input/event3)
[  3395.005] (**) Power Button: Applying InputClass "libinput keyboard catchall"
[  3395.005] (II) LoadModule: "libinput"
[  3395.008] (II) Loading /usr/lib/xorg/modules/input/libinput_drv.so
[  3395.014] (II) Module libinput: vendor="X.Org Foundation"
[  3395.014] 	compiled for 1.20.4, module version = 0.29.0
[  3395.014] 	Module class: X.Org XInput Driver
[  3395.014] 	ABI class: X.Org XInput driver, version 24.1
[  3395.014] (II) Using input driver 'libinput' for 'Power Button'
[  3395.015] (II) systemd-logind: got fd for /dev/input/event3 13:67 fd 22 paused 0
[  3395.015] (**) Power Button: always reports core events
[  3395.015] (**) Option "Device" "/dev/input/event3"
[  3395.016] (**) Option "_source" "server/udev"
[  3395.019] (II) event3  - Power Button: is tagged by udev as: Keyboard
[  3395.019] (II) event3  - Power Button: device is a keyboard
[  3395.020] (II) event3  - Power Button: device removed
[  3395.020] (**) Option "config_info" "udev:/sys/devices/LNXSYSTM:00/LNXPWRBN:00/input/input3/event3"
[  3395.020] (II) XINPUT: Adding extended input device "Power Button" (type: KEYBOARD, id 6)
[  3395.020] (**) Option "xkb_model" "pc105"
[  3395.020] (**) Option "xkb_layout" "us,ru"
[  3395.020] (**) Option "xkb_variant" ","
[  3395.020] (**) Option "xkb_options" "grp_led:scroll"
[  3395.081] (II) event3  - Power Button: is tagged by udev as: Keyboard
[  3395.081] (II) event3  - Power Button: device is a keyboard
[  3395.083] (II) config/udev: Adding input device Video Bus (/dev/input/event6)
[  3395.083] (**) Video Bus: Applying InputClass "libinput keyboard catchall"
[  3395.083] (II) Using input driver 'libinput' for 'Video Bus'
[  3395.084] (II) systemd-logind: got fd for /dev/input/event6 13:70 fd 25 paused 0
[  3395.085] (**) Video Bus: always reports core events
[  3395.085] (**) Option "Device" "/dev/input/event6"
[  3395.085] (**) Option "_source" "server/udev"
[  3395.087] (II) event6  - Video Bus: is tagged by udev as: Keyboard
[  3395.087] (II) event6  - Video Bus: device is a keyboard
[  3395.087] (II) event6  - Video Bus: device removed
[  3395.087] (**) Option "config_info" "udev:/sys/devices/LNXSYSTM:00/LNXSYBUS:00/PNP0A08:00/LNXVIDEO:01/input/input8/event6"
[  3395.087] (II) XINPUT: Adding extended input device "Video Bus" (type: KEYBOARD, id 7)
[  3395.087] (**) Option "xkb_model" "pc105"
[  3395.087] (**) Option "xkb_layout" "us,ru"
[  3395.087] (**) Option "xkb_variant" ","
[  3395.087] (**) Option "xkb_options" "grp_led:scroll"
[  3395.089] (II) event6  - Video Bus: is tagged by udev as: Keyboard
[  3395.090] (II) event6  - Video Bus: device is a keyboard
[  3395.091] (II) config/udev: Adding input device Power Button (/dev/input/event0)
[  3395.091] (**) Power Button: Applying InputClass "libinput keyboard catchall"
[  3395.091] (II) Using input driver 'libinput' for 'Power Button'
[  3395.093] (II) systemd-logind: got fd for /dev/input/event0 13:64 fd 26 paused 0
[  3395.093] (**) Power Button: always reports core events
[  3395.093] (**) Option "Device" "/dev/input/event0"
[  3395.093] (**) Option "_source" "server/udev"
[  3395.095] (II) event0  - Power Button: is tagged by udev as: Keyboard
[  3395.095] (II) event0  - Power Button: device is a keyboard
[  3395.096] (II) event0  - Power Button: device removed
[  3395.096] (**) Option "config_info" "udev:/sys/devices/LNXSYSTM:00/LNXSYBUS:00/PNP0A08:00/device:01/PNP0C0C:00/input/input0/event0"
[  3395.096] (II) XINPUT: Adding extended input device "Power Button" (type: KEYBOARD, id 8)
[  3395.096] (**) Option "xkb_model" "pc105"
[  3395.096] (**) Option "xkb_layout" "us,ru"
[  3395.096] (**) Option "xkb_variant" ","
[  3395.096] (**) Option "xkb_options" "grp_led:scroll"
[  3395.099] (II) event0  - Power Button: is tagged by udev as: Keyboard
[  3395.099] (II) event0  - Power Button: device is a keyboard
[  3395.100] (II) config/udev: Adding input device Lid Switch (/dev/input/event1)
[  3395.100] (II) No input driver specified, ignoring this device.
[  3395.100] (II) This device may have been added with another device file.
[  3395.102] (II) config/udev: Adding input device Sleep Button (/dev/input/event2)
[  3395.102] (**) Sleep Button: Applying InputClass "libinput keyboard catchall"
[  3395.102] (II) Using input driver 'libinput' for 'Sleep Button'
[  3395.113] (II) systemd-logind: got fd for /dev/input/event2 13:66 fd 27 paused 0
[  3395.113] (**) Sleep Button: always reports core events
[  3395.113] (**) Option "Device" "/dev/input/event2"
[  3395.113] (**) Option "_source" "server/udev"
[  3395.115] (II) event2  - Sleep Button: is tagged by udev as: Keyboard
[  3395.115] (II) event2  - Sleep Button: device is a keyboard
[  3395.116] (II) event2  - Sleep Button: device removed
[  3395.116] (**) Option "config_info" "udev:/sys/devices/LNXSYSTM:00/LNXSYBUS:00/PNP0A08:00/device:01/PNP0C0E:00/input/input2/event2"
[  3395.116] (II) XINPUT: Adding extended input device "Sleep Button" (type: KEYBOARD, id 9)
[  3395.116] (**) Option "xkb_model" "pc105"
[  3395.116] (**) Option "xkb_layout" "us,ru"
[  3395.116] (**) Option "xkb_variant" ","
[  3395.116] (**) Option "xkb_options" "grp_led:scroll"
[  3395.118] (II) event2  - Sleep Button: is tagged by udev as: Keyboard
[  3395.118] (II) event2  - Sleep Button: device is a keyboard
[  3395.120] (II) config/udev: Adding input device Video Bus (/dev/input/event5)
[  3395.120] (**) Video Bus: Applying InputClass "libinput keyboard catchall"
[  3395.120] (II) Using input driver 'libinput' for 'Video Bus'
[  3395.122] (II) systemd-logind: got fd for /dev/input/event5 13:69 fd 28 paused 0
[  3395.122] (**) Video Bus: always reports core events
[  3395.122] (**) Option "Device" "/dev/input/event5"
[  3395.122] (**) Option "_source" "server/udev"
[  3395.124] (II) event5  - Video Bus: is tagged by udev as: Keyboard
[  3395.124] (II) event5  - Video Bus: device is a keyboard
[  3395.125] (II) event5  - Video Bus: device removed
[  3395.125] (**) Option "config_info" "udev:/sys/devices/LNXSYSTM:00/LNXSYBUS:00/PNP0A08:00/device:36/LNXVIDEO:00/input/input7/event5"
[  3395.125] (II) XINPUT: Adding extended input device "Video Bus" (type: KEYBOARD, id 10)
[  3395.125] (**) Option "xkb_model" "pc105"
[  3395.125] (**) Option "xkb_layout" "us,ru"
[  3395.125] (**) Option "xkb_variant" ","
[  3395.125] (**) Option "xkb_options" "grp_led:scroll"
[  3395.128] (II) event5  - Video Bus: is tagged by udev as: Keyboard
[  3395.128] (II) event5  - Video Bus: device is a keyboard
[  3395.130] (II) config/udev: Adding input device HD WebCam: HD WebCam (/dev/input/event13)
[  3395.130] (**) HD WebCam: HD WebCam: Applying InputClass "libinput keyboard catchall"
[  3395.130] (II) Using input driver 'libinput' for 'HD WebCam: HD WebCam'
[  3395.134] (II) systemd-logind: got fd for /dev/input/event13 13:77 fd 29 paused 0
[  3395.134] (**) HD WebCam: HD WebCam: always reports core events
[  3395.134] (**) Option "Device" "/dev/input/event13"
[  3395.134] (**) Option "_source" "server/udev"
[  3395.137] (II) event13 - HD WebCam: HD WebCam: is tagged by udev as: Keyboard
[  3395.137] (II) event13 - HD WebCam: HD WebCam: device is a keyboard
[  3395.137] (II) event13 - HD WebCam: HD WebCam: device removed
[  3395.137] (**) Option "config_info" "udev:/sys/devices/pci0000:00/0000:00:1a.0/usb1/1-1/1-1.3/1-1.3:1.0/input/input14/event13"
[  3395.137] (II) XINPUT: Adding extended input device "HD WebCam: HD WebCam" (type: KEYBOARD, id 11)
[  3395.137] (**) Option "xkb_model" "pc105"
[  3395.138] (**) Option "xkb_layout" "us,ru"
[  3395.138] (**) Option "xkb_variant" ","
[  3395.138] (**) Option "xkb_options" "grp_led:scroll"
[  3395.141] (II) event13 - HD WebCam: HD WebCam: is tagged by udev as: Keyboard
[  3395.141] (II) event13 - HD WebCam: HD WebCam: device is a keyboard
[  3395.142] (II) config/udev: Adding input device HDA Intel PCH Mic (/dev/input/event14)
[  3395.142] (II) No input driver specified, ignoring this device.
[  3395.142] (II) This device may have been added with another device file.
[  3395.143] (II) config/udev: Adding input device HDA Intel PCH Headphone (/dev/input/event15)
[  3395.143] (II) No input driver specified, ignoring this device.
[  3395.143] (II) This device may have been added with another device file.
[  3395.144] (II) config/udev: Adding input device HDA Intel PCH HDMI/DP,pcm=3 (/dev/input/event16)
[  3395.144] (II) No input driver specified, ignoring this device.
[  3395.144] (II) This device may have been added with another device file.
[  3395.145] (II) config/udev: Adding input device USB OPTICAL MOUSE  (/dev/input/event7)
[  3395.145] (**) USB OPTICAL MOUSE : Applying InputClass "libinput pointer catchall"
[  3395.145] (II) Using input driver 'libinput' for 'USB OPTICAL MOUSE '
[  3395.206] (II) systemd-logind: got fd for /dev/input/event7 13:71 fd 30 paused 0
[  3395.206] (**) USB OPTICAL MOUSE : always reports core events
[  3395.206] (**) Option "Device" "/dev/input/event7"
[  3395.206] (**) Option "_source" "server/udev"
[  3395.210] (II) event7  - USB OPTICAL MOUSE : is tagged by udev as: Mouse
[  3395.210] (II) event7  - USB OPTICAL MOUSE : device is a pointer
[  3395.210] (II) event7  - USB OPTICAL MOUSE : device removed
[  3395.211] (**) Option "config_info" "udev:/sys/devices/pci0000:00/0000:00:1d.0/usb2/2-1/2-1.3/2-1.3.2/2-1.3.2:1.0/0003:275D:0BA6.001F/input/input55/event7"
[  3395.211] (II) XINPUT: Adding extended input device "USB OPTICAL MOUSE " (type: MOUSE, id 12)
[  3395.211] (**) Option "AccelerationScheme" "none"
[  3395.211] (**) USB OPTICAL MOUSE : (accel) selected scheme none/0
[  3395.211] (**) USB OPTICAL MOUSE : (accel) acceleration factor: 2.000
[  3395.211] (**) USB OPTICAL MOUSE : (accel) acceleration threshold: 4
[  3395.215] (II) event7  - USB OPTICAL MOUSE : is tagged by udev as: Mouse
[  3395.215] (II) event7  - USB OPTICAL MOUSE : device is a pointer
[  3395.217] (II) config/udev: Adding input device USB OPTICAL MOUSE  (/dev/input/mouse0)
[  3395.217] (II) No input driver specified, ignoring this device.
[  3395.217] (II) This device may have been added with another device file.
[  3395.219] (II) config/udev: Adding input device SZH usb keyboard (/dev/input/event9)
[  3395.219] (**) SZH usb keyboard: Applying InputClass "libinput keyboard catchall"
[  3395.219] (II) Using input driver 'libinput' for 'SZH usb keyboard'
[  3395.221] (II) systemd-logind: got fd for /dev/input/event9 13:73 fd 31 paused 0
[  3395.221] (**) SZH usb keyboard: always reports core events
[  3395.221] (**) Option "Device" "/dev/input/event9"
[  3395.221] (**) Option "_source" "server/udev"
[  3395.225] (II) event9  - SZH usb keyboard: is tagged by udev as: Keyboard
[  3395.225] (II) event9  - SZH usb keyboard: device is a keyboard
[  3395.225] (II) event9  - SZH usb keyboard: device removed
[  3395.225] (**) Option "config_info" "udev:/sys/devices/pci0000:00/0000:00:1d.0/usb2/2-1/2-1.3/2-1.3.4/2-1.3.4:1.0/0003:C0F4:04E0.0020/input/input56/event9"
[  3395.225] (II) XINPUT: Adding extended input device "SZH usb keyboard" (type: KEYBOARD, id 13)
[  3395.225] (**) Option "xkb_model" "pc105"
[  3395.225] (**) Option "xkb_layout" "us,ru"
[  3395.225] (**) Option "xkb_variant" ","
[  3395.225] (**) Option "xkb_options" "grp_led:scroll"
[  3395.230] (II) event9  - SZH usb keyboard: is tagged by udev as: Keyboard
[  3395.230] (II) event9  - SZH usb keyboard: device is a keyboard
[  3395.232] (II) config/udev: Adding input device SZH usb keyboard Consumer Control (/dev/input/event10)
[  3395.232] (**) SZH usb keyboard Consumer Control: Applying InputClass "libinput keyboard catchall"
[  3395.232] (II) Using input driver 'libinput' for 'SZH usb keyboard Consumer Control'
[  3395.234] (II) systemd-logind: got fd for /dev/input/event10 13:74 fd 32 paused 0
[  3395.234] (**) SZH usb keyboard Consumer Control: always reports core events
[  3395.234] (**) Option "Device" "/dev/input/event10"
[  3395.234] (**) Option "_source" "server/udev"
[  3395.238] (II) event10 - SZH usb keyboard Consumer Control: is tagged by udev as: Keyboard
[  3395.238] (II) event10 - SZH usb keyboard Consumer Control: device is a keyboard
[  3395.239] (II) event10 - SZH usb keyboard Consumer Control: device removed
[  3395.239] (II) libinput: SZH usb keyboard Consumer Control: needs a virtual subdevice
[  3395.239] (**) Option "config_info" "udev:/sys/devices/pci0000:00/0000:00:1d.0/usb2/2-1/2-1.3/2-1.3.4/2-1.3.4:1.1/0003:C0F4:04E0.0021/input/input57/event10"
[  3395.239] (II) XINPUT: Adding extended input device "SZH usb keyboard Consumer Control" (type: MOUSE, id 14)
[  3395.239] (**) Option "AccelerationScheme" "none"
[  3395.239] (**) SZH usb keyboard Consumer Control: (accel) selected scheme none/0
[  3395.239] (**) SZH usb keyboard Consumer Control: (accel) acceleration factor: 2.000
[  3395.239] (**) SZH usb keyboard Consumer Control: (accel) acceleration threshold: 4
[  3395.243] (II) event10 - SZH usb keyboard Consumer Control: is tagged by udev as: Keyboard
[  3395.243] (II) event10 - SZH usb keyboard Consumer Control: device is a keyboard
[  3395.245] (II) config/udev: Adding input device SZH usb keyboard System Control (/dev/input/event11)
[  3395.245] (**) SZH usb keyboard System Control: Applying InputClass "libinput keyboard catchall"
[  3395.245] (II) Using input driver 'libinput' for 'SZH usb keyboard System Control'
[  3395.248] (II) systemd-logind: got fd for /dev/input/event11 13:75 fd 33 paused 0
[  3395.248] (**) SZH usb keyboard System Control: always reports core events
[  3395.248] (**) Option "Device" "/dev/input/event11"
[  3395.248] (**) Option "_source" "server/udev"
[  3395.252] (II) event11 - SZH usb keyboard System Control: is tagged by udev as: Keyboard
[  3395.252] (II) event11 - SZH usb keyboard System Control: device is a keyboard
[  3395.253] (II) event11 - SZH usb keyboard System Control: device removed
[  3395.253] (**) Option "config_info" "udev:/sys/devices/pci0000:00/0000:00:1d.0/usb2/2-1/2-1.3/2-1.3.4/2-1.3.4:1.1/0003:C0F4:04E0.0021/input/input58/event11"
[  3395.253] (II) XINPUT: Adding extended input device "SZH usb keyboard System Control" (type: KEYBOARD, id 15)
[  3395.253] (**) Option "xkb_model" "pc105"
[  3395.253] (**) Option "xkb_layout" "us,ru"
[  3395.253] (**) Option "xkb_variant" ","
[  3395.253] (**) Option "xkb_options" "grp_led:scroll"
[  3395.256] (II) event11 - SZH usb keyboard System Control: is tagged by udev as: Keyboard
[  3395.256] (II) event11 - SZH usb keyboard System Control: device is a keyboard
[  3395.257] (II) config/udev: Adding input device AT Translated Set 2 keyboard (/dev/input/event4)
[  3395.257] (**) AT Translated Set 2 keyboard: Applying InputClass "libinput keyboard catchall"
[  3395.257] (II) Using input driver 'libinput' for 'AT Translated Set 2 keyboard'
[  3395.259] (II) systemd-logind: got fd for /dev/input/event4 13:68 fd 34 paused 0
[  3395.259] (**) AT Translated Set 2 keyboard: always reports core events
[  3395.259] (**) Option "Device" "/dev/input/event4"
[  3395.260] (**) Option "_source" "server/udev"
[  3395.263] (II) event4  - AT Translated Set 2 keyboard: is tagged by udev as: Keyboard
[  3395.263] (II) event4  - AT Translated Set 2 keyboard: device is a keyboard
[  3395.264] (II) event4  - AT Translated Set 2 keyboard: device removed
[  3395.264] (**) Option "config_info" "udev:/sys/devices/platform/i8042/serio0/input/input4/event4"
[  3395.264] (II) XINPUT: Adding extended input device "AT Translated Set 2 keyboard" (type: KEYBOARD, id 16)
[  3395.264] (**) Option "xkb_model" "pc105"
[  3395.264] (**) Option "xkb_layout" "us,ru"
[  3395.264] (**) Option "xkb_variant" ","
[  3395.264] (**) Option "xkb_options" "grp_led:scroll"
[  3395.267] (II) event4  - AT Translated Set 2 keyboard: is tagged by udev as: Keyboard
[  3395.267] (II) event4  - AT Translated Set 2 keyboard: device is a keyboard
[  3395.269] (II) config/udev: Adding input device ETPS/2 Elantech Touchpad (/dev/input/event8)
[  3395.269] (**) ETPS/2 Elantech Touchpad: Applying InputClass "libinput touchpad catchall"
[  3395.269] (II) Using input driver 'libinput' for 'ETPS/2 Elantech Touchpad'
[  3395.271] (II) systemd-logind: got fd for /dev/input/event8 13:72 fd 35 paused 0
[  3395.271] (**) ETPS/2 Elantech Touchpad: always reports core events
[  3395.271] (**) Option "Device" "/dev/input/event8"
[  3395.271] (**) Option "_source" "server/udev"
[  3395.272] (II) event8  - ETPS/2 Elantech Touchpad: is tagged by udev as: Touchpad
[  3395.274] (II) event8  - ETPS/2 Elantech Touchpad: device is a touchpad
[  3395.274] (II) event8  - ETPS/2 Elantech Touchpad: device removed
[  3395.275] (**) Option "config_info" "udev:/sys/devices/platform/i8042/serio1/input/input6/event8"
[  3395.275] (II) XINPUT: Adding extended input device "ETPS/2 Elantech Touchpad" (type: TOUCHPAD, id 17)
[  3395.276] (**) Option "AccelerationScheme" "none"
[  3395.276] (**) ETPS/2 Elantech Touchpad: (accel) selected scheme none/0
[  3395.276] (**) ETPS/2 Elantech Touchpad: (accel) acceleration factor: 2.000
[  3395.276] (**) ETPS/2 Elantech Touchpad: (accel) acceleration threshold: 4
[  3395.277] (II) event8  - ETPS/2 Elantech Touchpad: is tagged by udev as: Touchpad
[  3395.279] (II) event8  - ETPS/2 Elantech Touchpad: device is a touchpad
[  3395.280] (II) config/udev: Adding input device ETPS/2 Elantech Touchpad (/dev/input/mouse1)
[  3395.280] (II) No input driver specified, ignoring this device.
[  3395.280] (II) This device may have been added with another device file.
[  3395.285] (II) config/udev: Adding input device Acer WMI hotkeys (/dev/input/event12)
[  3395.285] (**) Acer WMI hotkeys: Applying InputClass "libinput keyboard catchall"
[  3395.285] (II) Using input driver 'libinput' for 'Acer WMI hotkeys'
[  3395.286] (II) systemd-logind: got fd for /dev/input/event12 13:76 fd 36 paused 0
[  3395.286] (**) Acer WMI hotkeys: always reports core events
[  3395.286] (**) Option "Device" "/dev/input/event12"
[  3395.286] (**) Option "_source" "server/udev"
[  3395.287] (II) event12 - Acer WMI hotkeys: is tagged by udev as: Keyboard
[  3395.287] (II) event12 - Acer WMI hotkeys: device is a keyboard
[  3395.288] (II) event12 - Acer WMI hotkeys: device removed
[  3395.288] (**) Option "config_info" "udev:/sys/devices/virtual/input/input13/event12"
[  3395.288] (II) XINPUT: Adding extended input device "Acer WMI hotkeys" (type: KEYBOARD, id 18)
[  3395.288] (**) Option "xkb_model" "pc105"
[  3395.288] (**) Option "xkb_layout" "us,ru"
[  3395.288] (**) Option "xkb_variant" ","
[  3395.288] (**) Option "xkb_options" "grp_led:scroll"
[  3395.289] (II) event12 - Acer WMI hotkeys: is tagged by udev as: Keyboard
[  3395.289] (II) event12 - Acer WMI hotkeys: device is a keyboard
[  3395.310] (**) SZH usb keyboard Consumer Control: Applying InputClass "libinput keyboard catchall"
[  3395.310] (II) Using input driver 'libinput' for 'SZH usb keyboard Consumer Control'
[  3395.310] (II) systemd-logind: returning pre-existing fd for /dev/input/event10 13:74
[  3395.310] (**) SZH usb keyboard Consumer Control: always reports core events
[  3395.310] (**) Option "Device" "/dev/input/event10"
[  3395.310] (**) Option "_source" "_driver/libinput"
[  3395.310] (II) libinput: SZH usb keyboard Consumer Control: is a virtual subdevice
[  3395.311] (**) Option "config_info" "udev:/sys/devices/pci0000:00/0000:00:1d.0/usb2/2-1/2-1.3/2-1.3.4/2-1.3.4:1.1/0003:C0F4:04E0.0021/input/input57/event10"
[  3395.311] (II) XINPUT: Adding extended input device "SZH usb keyboard Consumer Control" (type: KEYBOARD, id 19)
[  3395.311] (**) Option "xkb_model" "pc105"
[  3395.311] (**) Option "xkb_layout" "us,ru"
[  3395.311] (**) Option "xkb_variant" ","
[  3395.311] (**) Option "xkb_options" "grp_led:scroll"
[  3396.414] (II) modeset(0): EDID vendor "LGD", prod id 732
[  3396.414] (II) modeset(0): Printing DDC gathered Modelines:
[  3396.414] (II) modeset(0): Modeline "1366x768"x0.0   70.00  1366 1402 1450 1492  768 771 776 782 -hsync -vsync (46.9 kHz eP)
[  3417.146] (II) modeset(0): EDID vendor "LGD", prod id 732
[  3417.146] (II) modeset(0): Printing DDC gathered Modelines:
[  3417.146] (II) modeset(0): Modeline "1366x768"x0.0   70.00  1366 1402 1450 1492  768 771 776 782 -hsync -vsync (46.9 kHz eP)
[  3607.473] (II) config/udev: Adding input device BT-M-100 (AVRCP) (/dev/input/event17)
[  3607.474] (**) BT-M-100 (AVRCP): Applying InputClass "libinput keyboard catchall"
[  3607.474] (II) Using input driver 'libinput' for 'BT-M-100 (AVRCP)'
[  3607.476] (II) systemd-logind: got fd for /dev/input/event17 13:81 fd 67 paused 0
[  3607.476] (**) BT-M-100 (AVRCP): always reports core events
[  3607.476] (**) Option "Device" "/dev/input/event17"
[  3607.476] (**) Option "_source" "server/udev"
[  3607.479] (II) event17 - BT-M-100 (AVRCP): is tagged by udev as: Keyboard
[  3607.479] (II) event17 - BT-M-100 (AVRCP): device is a keyboard
[  3607.479] (II) event17 - BT-M-100 (AVRCP): device removed
[  3607.479] (**) Option "config_info" "udev:/sys/devices/virtual/input/input59/event17"
[  3607.479] (II) XINPUT: Adding extended input device "BT-M-100 (AVRCP)" (type: KEYBOARD, id 20)
[  3607.479] (**) Option "xkb_model" "pc105"
[  3607.479] (**) Option "xkb_layout" "us,ru"
[  3607.480] (**) Option "xkb_variant" ","
[  3607.480] (**) Option "xkb_options" "grp_led:scroll"
[  3607.483] (II) event17 - BT-M-100 (AVRCP): is tagged by udev as: Keyboard
[  3607.484] (II) event17 - BT-M-100 (AVRCP): device is a keyboard
[  3865.616] (II) modeset(0): EDID vendor "LGD", prod id 732
[  3865.616] (II) modeset(0): Printing DDC gathered Modelines:
[  3865.617] (II) modeset(0): Modeline "1366x768"x0.0   70.00  1366 1402 1450 1492  768 771 776 782 -hsync -vsync (46.9 kHz eP)
[  4367.367] (II) modeset(0): EDID vendor "LGD", prod id 732
[  4367.367] (II) modeset(0): Printing DDC gathered Modelines:
[  4367.367] (II) modeset(0): Modeline "1366x768"x0.0   70.00  1366 1402 1450 1492  768 771 776 782 -hsync -vsync (46.9 kHz eP)
[  6334.309] (**) Option "fd" "22"
[  6334.311] (II) event3  - Power Button: device removed
[  6334.311] (**) Option "fd" "25"
[  6334.311] (II) event6  - Video Bus: device removed
[  6334.311] (**) Option "fd" "26"
[  6334.311] (II) event0  - Power Button: device removed
[  6334.311] (**) Option "fd" "27"
[  6334.311] (II) event2  - Sleep Button: device removed
[  6334.311] (**) Option "fd" "28"
[  6334.311] (II) event5  - Video Bus: device removed
[  6334.311] (**) Option "fd" "29"
[  6334.311] (II) event13 - HD WebCam: HD WebCam: device removed
[  6334.311] (**) Option "fd" "30"
[  6334.311] (II) event7  - USB OPTICAL MOUSE : device removed
[  6334.312] (**) Option "fd" "31"
[  6334.312] (II) event9  - SZH usb keyboard: device removed
[  6334.312] (**) Option "fd" "32"
[  6334.312] (**) Option "fd" "33"
[  6334.312] (II) event11 - SZH usb keyboard System Control: device removed
[  6334.312] (**) Option "fd" "34"
[  6334.312] (II) event4  - AT Translated Set 2 keyboard: device removed
[  6334.312] (**) Option "fd" "35"
[  6334.312] (II) event8  - ETPS/2 Elantech Touchpad: device removed
[  6334.313] (**) Option "fd" "36"
[  6334.313] (II) event12 - Acer WMI hotkeys: device removed
[  6334.313] (**) Option "fd" "32"
[  6334.313] (II) event10 - SZH usb keyboard Consumer Control: device removed
[  6334.314] (**) Option "fd" "67"
[  6334.314] (II) event17 - BT-M-100 (AVRCP): device removed
[  6334.328] (II) UnloadModule: "libinput"
[  6334.328] (II) systemd-logind: releasing fd for 13:81
[  6334.349] (II) UnloadModule: "libinput"
[  6334.349] (II) systemd-logind: not releasing fd for 13:74, still in use
[  6334.349] (II) UnloadModule: "libinput"
[  6334.350] (II) systemd-logind: releasing fd for 13:76
[  6334.377] (II) UnloadModule: "libinput"
[  6334.378] (II) systemd-logind: releasing fd for 13:72
[  6334.425] (II) UnloadModule: "libinput"
[  6334.426] (II) systemd-logind: releasing fd for 13:68
[  6334.449] (II) UnloadModule: "libinput"
[  6334.450] (II) systemd-logind: releasing fd for 13:75
[  6334.473] (II) UnloadModule: "libinput"
[  6334.473] (II) systemd-logind: releasing fd for 13:74
[  6334.501] (II) UnloadModule: "libinput"
[  6334.501] (II) systemd-logind: releasing fd for 13:73
[  6334.533] (II) UnloadModule: "libinput"
[  6334.533] (II) systemd-logind: releasing fd for 13:71
[  6334.573] (II) UnloadModule: "libinput"
[  6334.573] (II) systemd-logind: releasing fd for 13:77
[  6334.613] (II) UnloadModule: "libinput"
[  6334.614] (II) systemd-logind: releasing fd for 13:69
[  6334.637] (II) UnloadModule: "libinput"
[  6334.638] (II) systemd-logind: releasing fd for 13:66
[  6334.661] (II) UnloadModule: "libinput"
[  6334.662] (II) systemd-logind: releasing fd for 13:64
[  6334.693] (II) UnloadModule: "libinput"
[  6334.694] (II) systemd-logind: releasing fd for 13:70
[  6334.711] (II) UnloadModule: "libinput"
[  6334.711] (II) systemd-logind: releasing fd for 13:67
[  6334.766] (II) Server terminated successfully (0). Closing log file.							   
_______________________________________________________________________________________________________________________________________________________________

        Vulkan my build mesa chrome://gpu browser information dump parametr auto compile generation json scheme
					
					Video Acceleration Information
					   
					   
info	{
  "apiVersion": 4202627,
  "usedApiVersion": 4198400,
  "instanceExtensions": [
    {
      "extensionName": "VK_KHR_device_group_creation",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_display",
      "specVersion": 23
    },
    {
      "extensionName": "VK_KHR_external_fence_capabilities",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_external_memory_capabilities",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_external_semaphore_capabilities",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_get_display_properties2",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_get_physical_device_properties2",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_get_surface_capabilities2",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_surface",
      "specVersion": 25
    },
    {
      "extensionName": "VK_KHR_surface_protected_capabilities",
      "specVersion": 1
    },
    {
      "extensionName": "VK_KHR_wayland_surface",
      "specVersion": 6
    },
    {
      "extensionName": "VK_KHR_xcb_surface",
      "specVersion": 6
    },
    {
      "extensionName": "VK_KHR_xlib_surface",
      "specVersion": 6
    },
    {
      "extensionName": "VK_EXT_acquire_xlib_display",
      "specVersion": 1
    },
    {
      "extensionName": "VK_EXT_debug_report",
      "specVersion": 9
    },
    {
      "extensionName": "VK_EXT_direct_mode_display",
      "specVersion": 1
    },
    {
      "extensionName": "VK_EXT_display_surface_counter",
      "specVersion": 1
    },
    {
      "extensionName": "VK_EXT_debug_utils",
      "specVersion": 1
    }
  ],
  "enabledInstanceExtensions": [
    "VK_KHR_external_memory_capabilities",
    "VK_KHR_external_semaphore_capabilities",
    "VK_EXT_debug_report"
  ],
  "instanceLayers": [
    {
      "layerName": "VK_LAYER_NV_optimus",
      "specVersion": 4198519,
      "implementationVersion": 1,
      "description": "NVIDIA Optimus layer"
    },
    {
      "layerName": "VK_LAYER_MESA_device_select",
      "specVersion": 4202569,
      "implementationVersion": 1,
      "description": "Linux device selection layer"
    },
    {
      "layerName": "VK_LAYER_GOOGLE_threading",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "Google Validation Layer"
    },
    {
      "layerName": "VK_LAYER_MESA_overlay",
      "specVersion": 4198473,
      "implementationVersion": 1,
      "description": "Mesa Overlay layer"
    },
    {
      "layerName": "VK_LAYER_KHRONOS_validation",
      "specVersion": 4202627,
      "implementationVersion": 1,
      "description": "Khronos Validation Layer"
    },
    {
      "layerName": "VK_LAYER_LUNARG_core_validation",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "LunarG Validation Layer"
    },
    {
      "layerName": "VK_LAYER_GOOGLE_unique_objects",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "Google Validation Layer"
    },
    {
      "layerName": "VK_LAYER_LUNARG_object_tracker",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "LunarG Validation Layer"
    },
    {
      "layerName": "VK_LAYER_LUNARG_standard_validation",
      "specVersion": 4202627,
      "implementationVersion": 1,
      "description": "LunarG Standard Validation"
    },
    {
      "layerName": "VK_LAYER_LUNARG_parameter_validation",
      "specVersion": 4198482,
      "implementationVersion": 1,
      "description": "LunarG Validation Layer"
    }
  ],
  "physicalDevices": [
    {
      "properties": {
        "apiVersion": 4194306,
        "driverVersion": 1,
        "vendorID": 65541,
        "deviceID": 0,
        "deviceType": 4,
        "deviceName": "llvmpipe (LLVM 12.0.0, 256 bits)",
        "pipelineCacheUUID": [
          118,
          97,
          108,
          45,
          105,
          109,
          101,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0
        ],
        "limits": {
          "maxImageDimension1D": 16384,
          "maxImageDimension2D": 16384,
          "maxImageDimension3D": 4096,
          "maxImageDimensionCube": 32768,
          "maxImageArrayLayers": 2048,
          "maxTexelBufferElements": 134217728,
          "maxUniformBufferRange": 65536,
          "maxStorageBufferRange": 134217728,
          "maxPushConstantsSize": 128,
          "maxMemoryAllocationCount": 4096,
          "maxSamplerAllocationCount": 32768,
          "bufferImageGranularity": 1,
          "sparseAddressSpaceSize": 0,
          "maxBoundDescriptorSets": 8,
          "maxPerStageDescriptorSamplers": 32,
          "maxPerStageDescriptorUniformBuffers": 16,
          "maxPerStageDescriptorStorageBuffers": 16,
          "maxPerStageDescriptorSampledImages": 128,
          "maxPerStageDescriptorStorageImages": 16,
          "maxPerStageDescriptorInputAttachments": 8,
          "maxPerStageResources": 128,
          "maxDescriptorSetSamplers": 32768,
          "maxDescriptorSetUniformBuffers": 256,
          "maxDescriptorSetUniformBuffersDynamic": 256,
          "maxDescriptorSetStorageBuffers": 256,
          "maxDescriptorSetStorageBuffersDynamic": 256,
          "maxDescriptorSetSampledImages": 256,
          "maxDescriptorSetStorageImages": 256,
          "maxDescriptorSetInputAttachments": 256,
          "maxVertexInputAttributes": 32,
          "maxVertexInputBindings": 32,
          "maxVertexInputAttributeOffset": 2047,
          "maxVertexInputBindingStride": 2048,
          "maxVertexOutputComponents": 128,
          "maxTessellationGenerationLevel": 64,
          "maxTessellationPatchSize": 32,
          "maxTessellationControlPerVertexInputComponents": 128,
          "maxTessellationControlPerVertexOutputComponents": 128,
          "maxTessellationControlPerPatchOutputComponents": 128,
          "maxTessellationControlTotalOutputComponents": 4096,
          "maxTessellationEvaluationInputComponents": 128,
          "maxTessellationEvaluationOutputComponents": 128,
          "maxGeometryShaderInvocations": 32,
          "maxGeometryInputComponents": 64,
          "maxGeometryOutputComponents": 128,
          "maxGeometryOutputVertices": 1024,
          "maxGeometryTotalOutputComponents": 1024,
          "maxFragmentInputComponents": 128,
          "maxFragmentOutputAttachments": 8,
          "maxFragmentDualSrcAttachments": 2,
          "maxFragmentCombinedOutputResources": 8,
          "maxComputeSharedMemorySize": 32768,
          "maxComputeWorkGroupCount": [
            65535,
            65535,
            65535
          ],
          "maxComputeWorkGroupInvocations": 1024,
          "maxComputeWorkGroupSize": [
            1024,
            1024,
            1024
          ],
          "subPixelPrecisionBits": 8,
          "subTexelPrecisionBits": 8,
          "mipmapPrecisionBits": 8,
          "maxDrawIndexedIndexValue": 4294967295,
          "maxDrawIndirectCount": 4294967295,
          "maxSamplerLodBias": 16,
          "maxSamplerAnisotropy": 16,
          "maxViewports": 16,
          "maxViewportDimensions": [
            16384,
            16384
          ],
          "viewportBoundsRange": [
            -32768,
            32768
          ],
          "viewportSubPixelBits": 0,
          "minMemoryMapAlignment": 4096,
          "minTexelBufferOffsetAlignment": 1,
          "minUniformBufferOffsetAlignment": 1,
          "minStorageBufferOffsetAlignment": 1,
          "minTexelOffset": -32,
          "maxTexelOffset": 31,
          "minTexelGatherOffset": -32,
          "maxTexelGatherOffset": 31,
          "minInterpolationOffset": -2,
          "maxInterpolationOffset": 2,
          "subPixelInterpolationOffsetBits": 8,
          "maxFramebufferWidth": 16384,
          "maxFramebufferHeight": 16384,
          "maxFramebufferLayers": 2048,
          "framebufferColorSampleCounts": 5,
          "framebufferDepthSampleCounts": 5,
          "framebufferStencilSampleCounts": 5,
          "framebufferNoAttachmentsSampleCounts": 5,
          "maxColorAttachments": 8,
          "sampledImageColorSampleCounts": 5,
          "sampledImageIntegerSampleCounts": 5,
          "sampledImageDepthSampleCounts": 5,
          "sampledImageStencilSampleCounts": 5,
          "storageImageSampleCounts": 5,
          "maxSampleMaskWords": 1,
          "timestampComputeAndGraphics": true,
          "timestampPeriod": 1,
          "maxClipDistances": 8,
          "maxCullDistances": 8,
          "maxCombinedClipAndCullDistances": 8,
          "discreteQueuePriorities": 2,
          "pointSizeRange": [
            0,
            255
          ],
          "lineWidthRange": [
            1,
            1
          ],
          "pointSizeGranularity": 0.125,
          "lineWidthGranularity": 0,
          "strictLines": false,
          "standardSampleLocations": true,
          "optimalBufferCopyOffsetAlignment": 1,
          "optimalBufferCopyRowPitchAlignment": 1,
          "nonCoherentAtomSize": 1
        },
        "sparseProperties": {
          "residencyStandard2DBlockShape": false,
          "residencyStandard2DMultisampleBlockShape": false,
          "residencyStandard3DBlockShape": false,
          "residencyAlignedMipSize": false,
          "residencyNonResidentStrict": false
        }
      },
      "extensions": [
        {
          "extensionName": "VK_KHR_bind_memory2",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_dedicated_allocation",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_descriptor_update_template",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_device_group",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_draw_indirect_count",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_driver_properties",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_get_memory_requirements2",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_incremental_present",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_maintenance1",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_push_descriptor",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_relaxed_block_layout",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_sampler_mirror_clamp_to_edge",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_storage_buffer_storage_class",
          "specVersion": 1
        },
        {
          "extensionName": "VK_KHR_swapchain",
          "specVersion": 68
        },
        {
          "extensionName": "VK_EXT_external_memory_dma_buf",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_index_type_uint8",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_post_depth_coverage",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_private_data",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_shader_stencil_export",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_transform_feedback",
          "specVersion": 1
        },
        {
          "extensionName": "VK_EXT_vertex_attribute_divisor",
          "specVersion": 3
        },
        {
          "extensionName": "VK_GOOGLE_decorate_string",
          "specVersion": 1
        },
        {
          "extensionName": "VK_GOOGLE_hlsl_functionality1",
          "specVersion": 1
        }
      ],
      "features": {
        "robustBufferAccess": false,
        "fullDrawIndexUint32": false,
        "imageCubeArray": false,
        "independentBlend": false,
        "geometryShader": false,
        "tessellationShader": false,
        "sampleRateShading": false,
        "dualSrcBlend": false,
        "logicOp": false,
        "multiDrawIndirect": false,
        "drawIndirectFirstInstance": false,
        "depthClamp": false,
        "depthBiasClamp": false,
        "fillModeNonSolid": false,
        "depthBounds": false,
        "wideLines": false,
        "largePoints": false,
        "alphaToOne": false,
        "multiViewport": false,
        "samplerAnisotropy": false,
        "textureCompressionETC2": false,
        "textureCompressionASTCLDR": false,
        "textureCompressionBC": false,
        "occlusionQueryPrecise": false,
        "pipelineStatisticsQuery": false,
        "vertexPipelineStoresAndAtomics": false,
        "fragmentStoresAndAtomics": false,
        "shaderTessellationAndGeometryPointSize": false,
        "shaderImageGatherExtended": false,
        "shaderStorageImageExtendedFormats": false,
        "shaderStorageImageMultisample": false,
        "shaderStorageImageReadWithoutFormat": false,
        "shaderStorageImageWriteWithoutFormat": false,
        "shaderUniformBufferArrayDynamicIndexing": false,
        "shaderSampledImageArrayDynamicIndexing": false,
        "shaderStorageBufferArrayDynamicIndexing": false,
        "shaderStorageImageArrayDynamicIndexing": false,
        "shaderClipDistance": false,
        "shaderCullDistance": false,
        "shaderFloat64": false,
        "shaderInt64": false,
        "shaderInt16": false,
        "shaderResourceResidency": false,
        "shaderResourceMinLod": false,
        "sparseBinding": false,
        "sparseResidencyBuffer": false,
        "sparseResidencyImage2D": false,
        "sparseResidencyImage3D": false,
        "sparseResidency2Samples": false,
        "sparseResidency4Samples": false,
        "sparseResidency8Samples": false,
        "sparseResidency16Samples": false,
        "sparseResidencyAliased": false,
        "variableMultisampleRate": false,
        "inheritedQueries": false
      },
      "featureSamplerYcbcrConversion": false,
      "featureProtectedMemory": false,
      "queueFamilies": [
        {
          "queueFlags": 7,
          "queueCount": 1,
          "timestampValidBits": 64,
          "minImageTransferGranularity": {
            "width": 1,
            "height": 1,
            "depth": 1
          }
        }
      ]
    }
  ]
