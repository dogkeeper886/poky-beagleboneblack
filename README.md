# BeagleBone Black Yocto Project

This repository contains the Yocto Project configuration files (`local.conf`) for customizing the build for BeagleBone Black, including support for a WiFi USB adapter.

## Configuration Details

### WiFi USB Adapter

The `local.conf` file is configured to include the following components for WiFi support:

- **linux-firmware**: The necessary firmware for the WiFi USB adapter.
- **wpa-supplicant**: The package for managing WiFi connections.

### Kernel Configuration

To enable support for the WiFi USB adapter, follow these steps to create a layer and modify the linux-yocto kernel configuration:

1. Clone the meta repository for your Yocto version:
   ```bash
   git clone -b <yocto-version> https://git.yoctoproject.org/git/poky.git
2. Add the newly created layer to your Yocto project:
   ```bash
bash
Copy code
bitbake-layers add-layer ../path/to/your/layer
Inside your layer, create a kernel configuration fragment file, e.g., wifi-usb.cfg, to enable the necessary kernel configuration options for your WiFi USB adapter.

Edit conf/layer.conf in your layer to include the kernel configuration fragment:

conf
Copy code
BBFILE_PATTERN += "^${LAYERDIR}/"
BBFILE_PRIORITY_${PN} = "8"
LAYERVERSION_wifi-usb = "1"
Build the image:

bash
Copy code
bitbake <image-name>
Flash the image to your BeagleBone Black.
