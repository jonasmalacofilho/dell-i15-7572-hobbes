# Notes and config files for Hobbes
_a Dell Inspiron 15 7572 laptop_

## Linux

 - multibootusb requires v9.3/git for archlinux
 - dual boot: fix time standard used in Windows
 - issues with the wireless adapter
    * driver: ath10k
    * updating the BIOS (1.1.8) _helps_
    * has difficulties connecting to open networks
 - PCIe AER errors on Intel Corporation Sunrise Point-LP PCI Express Root Port #6 (00:1c.5)
    * related to the wireless adapter
    * TODO try [`pcie_aspm=off`](https://askubuntu.com/a/863301)
    * TODO try a more recent BIOS
 - nouveau crashes
    * blacklist it
 - enable early KMS
    * needed after upgrading to Gnome 3.34 and Linux 5.3
    * add `i915` to `/etc/mkinitcpio.conf:MODULES`
    * regenerate the initramfs with `mkinitcpio -p linux`
 - lm-sensors
    * config file in linux/etc/sensors.d/dell-i15-7572.conf
 - otherwise working well with
    * Linux 5.3.1
    * Gnome 3.34.0 (including Wayland)

## Windows

 - fix time standard:
    * add `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation\RealTimeIsUniversal = QWORD, 1`
