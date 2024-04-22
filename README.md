### OpenWRT for M3
This is an openwrt fork for the UCSD M3 project (http://m3.ucsd.edu/sdr/). M3 is the first mmWave massive MIMO software radio platform. 

### Supported Devices
[Mikrotik wAP 60G](https://mikrotik.com/product/wap_60g#fndtn-specifications)
[Mikrotik wAP 60G AP](https://mikrotik.com/product/wap_60g_ap#fndtn-specifications)
[Mikrotik wAP 60Gx3 AP](https://mikrotik.com/product/wap_60gx3_ap#fndtn-specifications)
[Mikrotik Wireless Wire Dish](https://mikrotik.com/product/wireless_wire_dish#fndtn-specifications)

### Flashing the Mikrotik router with OpenWRT-m3
The compiled OpenWRT Image can be found in <>.
A tutorial of how to flash the Mikrotik routers with OpenWRT can be found here.
[IMDEA Networks](https://github.com/IMDEANetworksWNG/Mikrotik-researcher-tools)

### Modification and Re-Complication
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

## License

OpenWrt is licensed under GPL-2.0
