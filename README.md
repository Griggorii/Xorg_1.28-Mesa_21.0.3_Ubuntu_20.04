# Xorg_1.28-Mesa_23.0.1_libmesa_dri_Ubuntu_20.04
Mesa+Xorg full my build , ubuntu 20.04 , libc-2.31 , new libmesa_dri , wayland speed fast +50% , mesa proc self build , libmesa_dri build flag cpp_std=c++2a module

                      Ubuntu 20.04 special edition video driver architect Griggorii

Download mesa+xorg new videodriver: https://github.com/Griggorii/Xorg_1.28-Mesa_23.0.1_libmesa_dri_Ubuntu_20.04/releases/tag/libmesa_dri

Deb kernel recomendation support all nvidia , touchpad , zfs , bbswitch: https://github.com/Griggorii/linux-image-unsigned-5.6.0-1020-oem-kernel-mod-rpm-deb/releases/tag/linux-image-unsigned-5.6.0-1020-fedora

Test run video driver chromium/chrome/opera/brave/and analog engine browser replace (chromium-browser) flag: https://github.com/Griggorii/Chromium_OS_77



                         ________________________________________________
                        |                                                |
                        | Test fbdev new video driver architect Griggorii|
                        |_______________________________________________ |


The text of the settings on the Internet page FBDEV is not correctly displayed. Downloads readme.md to see the correct settings and correct setting copy alternative raw page https://raw.githubusercontent.com/Griggorii/Xorg_1.28-Mesa_23.0.1_libmesa_dri_Ubuntu_20.04/main/README.md 

Monitor support 60-75 replace string  (VertRefresh 60-75) example support  monitor 110-120 ? , danger experiment monitor not support blackscreen (VertRefresh 110-120)

$ sudo mkdir /etc/X11/xorg.conf.d

$ cd /etc/X11/xorg.conf.d

$ sudo cat << EOF > xorg.conf
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
