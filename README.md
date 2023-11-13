# BeagleBone Black Yocto Project

This repository contains the Yocto Project configuration files (`local.conf`) for customizing the build for BeagleBone Black, including support for a WiFi USB adapter.

## Configuration Details

### WiFi USB Adapter

The `local.conf` file is configured to include the following components for WiFi support:

- **linux-firmware**: The necessary firmware for the WiFi USB adapter.
1. mt7601u
- **wpa-supplicant**: The package for managing WiFi connections.

### Kernel Configuration

To enable support for the WiFi USB adapter, follow these steps to create a layer and add the linux-yocto kernel configuration:

1. Clone the meta repository for your Yocto version:
   ```bash
   git clone -b kirkstone https://github.com/dogkeeper886/meta-mt7601u
2. Create a layer:
   ```bash
   bitbake-layers create-layer ../path/to/your/meta-mt7601u   
2. Add the newly created layer to your Yocto project:
   ```bash
   bitbake-layers add-layer ../path/to/your/meta-mt7601u
3. Build the image:
   ```bash
   bitbake <image-name>
4. Flash the image to your BeagleBone Black.
