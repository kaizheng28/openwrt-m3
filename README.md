### OpenWRT for M3

This is an openwrt fork for the UCSD M3 project. The modified OS provides support for Mikrotik wAP 60Gx3 router. A python server file is also provided to control the 60GHz wil6210 firmware. 

This is not an official openwrt branch. Please contact the Kai Zheng (kaizheng28@gmail.com) if you have any questions.

### Flashing the Mikrotik router with OpenWRT-m3
The compiled OpenWRT Image can be found in ... 
TO BE UPDATED LATER. 

### Compilation Requirement and Procedure

To modify and re-compile OpenWRT, see the following procedure.

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
