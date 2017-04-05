# openwrt-3g-mwan3

Build for TP-Link MR-3220 v2:<br>
Downloading ImageBuilder (already done): 
```bash
cd ~
mkdir openwrt && cd openwrt
wget https://downloads.openwrt.org/chaos_calmer/15.05.1/ar71xx/generic/OpenWrt-ImageBuilder-15.05.1-ar71xx-generic.Linux-x86_64.tar.bz2
tar -xvjf OpenWrt-ImageBuilder-15.05.1-ar71xx-generic.Linux-x86_64.tar.bz2
cd OpenWrt-ImageBuilder-15.05.1-ar71xx-generic.Linux-x86_64
```

Adding customizations (already done): 
 - modifying Makefile to use of files_remove file
 - adding files_remove
 - adding configs

Building (already done, but needed for further customizations): 
```bash
make image PROFILE=TLMR3220 PACKAGES="kmod-usb-core kmod-usb2 usb-modeswitch libusb-1.0 \
     chat comgt kmod-usb-serial kmod-usb-serial-option mwan3 ip ipset luci luci-proto-3g luci-app-mwan3 \
     -ip6tables -kmod-ip6tables -kmod-ipv6 -odhcp6c -luci-proto-ipv6 -libip6tc" \
     FILES_REMOVE="files_remove" FILES=files/
```

Links:<br>
https://wiki.openwrt.org/doc/howto/obtain.firmware.generate <br>
https://eko.one.pl/?p=openwrt-3g <br>
http://eko.one.pl/forum/viewtopic.php?id=9836 <br>
