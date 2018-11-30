## Realtek 802.11ac (rtl8812au)

This is a fork of the Realtek 802.11ac (rtl8812au) v4.2.2 (7502.20130507)
driver altered to build on Linux kernel version >= 3.10.

### Purpose

My Alfa AWUS036ACH adapter needs this driver compiled before it can be used under Kali linux or Raspbian as of 11/30-18

### Building

The Makefile is preconfigured to handle the Raspberry Pi.  If you are compiling for intel x86 architecture, you need to first select the platform, I386 to y and the ARM_RPI to n:
```sh
...
CONFIG_PLATFORM_I386_PC = y
...
CONFIG_PLATFORM_ARM_RPI = n
```

There are many other platforms supported and some other advanced options, e.g. PCI instead of USB, but most won't be needed.

The driver is built by running `make`, and can be tested by loading the

After loading the module, a wireless network interface named __Realtek 802.11n WLAN Adapter__ should be available.

### Installing

IT IS VERY IMPORTANT THAT YOU MAKE SURE TO HAVE THE KERNEL HEADERS BEFORE PROCEEDING!!!

sudo chmod +x install.sh

This next step is critical for getting the make to work. Before running make or install.sh you have to install raspberrypi kernel headers and build essential

$ sudo apt-get install raspberrypi-kernel-headers build-essential

then instead of manually running make, use the automated install file.

sudo ./install.sh <--- This is where the error occurred before. Now that you installed the RaspberryPi Kernel Headers it works.

Finally, shutdown the device. 


