### OpenWRT for M3
This is an openwrt fork for the UCSD M3 project (http://m3.ucsd.edu/sdr/). M3 is the first mmWave massive MIMO software radio platform. 

### Supported Devices
[Mikrotik wAP 60G](https://mikrotik.com/product/wap_60g#fndtn-specifications)

[Mikrotik wAP 60G AP](https://mikrotik.com/product/wap_60g_ap#fndtn-specifications)

[Mikrotik wAP 60Gx3 AP](https://mikrotik.com/product/wap_60gx3_ap#fndtn-specifications)

[Mikrotik Wireless Wire Dish](https://mikrotik.com/product/wireless_wire_dish#fndtn-specifications)


### Installing OpenWRT-M3 on Mikrotik Routers
The compiled OpenWRT Image can be found in [here](https://github.com/kaizheng28/openwrt-m3/files/15083623/openwrt-m3-image.zip).

openwrt-m3-initramfs.bin is the RAM-based image that is used for initial temporary OS installation. 

openwrt-m3-sysupgrade.bin is the flash image that can be used to make the OS permanent.  

A detailed tutorial of installing OpenWRT on the Mikrotik routers can be found in [IMDEA Mikrotik Research Tools](https://github.com/IMDEANetworksWNG/Mikrotik-researcher-tools).

Notably, for Ubuntu 22.04, the tftp server folder is located at /srv/tftp/ . 

### Modification and Re-Compilation
You need the following tools to compile OpenWrt, the package names vary between
distributions. A complete list with distribution specific packages is found in
the [Build System Setup](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem)
documentation.

```
binutils bzip2 diff find flex gawk gcc-6+ getopt grep install libc-dev libz-dev
make4.1+ perl python3.7+ rsync subversion unzip which
```

1. Run `./scripts/feeds update -a` to obtain all the latest package definitions
   defined in feeds.conf / feeds.conf.default

2. Run `./scripts/feeds install -a` to install symlinks for all obtained
   packages into package/feeds/

3. Run `make menuconfig` to select your preferred configuration for the
   toolchain, target system & firmware packages.

4. Run `make` to build your firmware. This will download all sources, build the
   cross-compile toolchain and then cross-compile the GNU/Linux kernel & all chosen
   applications for your target system.

### References
Renjie Zhao, Timothy Woodford, Teng Wei, Kun Qian, and Xinyu Zhang. 2020. M-Cube: a millimeter-wave massive MIMO software radio. In Proceedings of the 26th Annual International Conference on Mobile Computing and Networking (MobiCom '20). Association for Computing Machinery, New York, NY, USA, Article 15, 1–14. DOI:https://doi.org/10.1145/3372224.3380892

## License
OpenWrt is licensed under GPL-2.0
