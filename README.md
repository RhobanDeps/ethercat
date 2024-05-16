# IGH Ethercat master

This is forked from: https://gitlab.com/etherlab.org/ethercat/
Branch `stable-1.5` is used.

## Installing

Run the [following commands](https://gitlab.com/etherlab.org/ethercat/-/blob/stable-1.5/INSTALL.md):

```bash
./bootstrap
./configure # or, on the ZOTAC: ./configure --enable-r8169 
make all modules
```

As root:

```bash
make modules_install install
depmod
ln -s /usr/local/etc/init.d/ethercat /etc/init.d/ethercat
cp /usr/local/etc/sysconfig/ethercat /etc/sysconfig/ethercat
```

## Configuring

Edit the `/etc/sysconfig/ethercat` configuration file, and set:

* `MASTER0_DEVICE` to the MAC address of the ethernet device you want to use
* `DEVICE_MODULES` to the module (e.g: `generic`)

