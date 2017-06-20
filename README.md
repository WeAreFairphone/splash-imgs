# splash-imgs
Build your own splash screens for the Fairphone 2 (FP2)

# Building the splash screen

## Requirements

- Python 2.7
- PIL

### Debian/Ubuntu

Install `python` and `python-imaging` from your distro software repositories:

```
sudo apt install python python-imaging
```

## Build the splash screen

Run:

```
python2 logo_gen.py <raster image file>
```

Raster image file can be PNG, JPEG, BMP and GIF, 1080x1920 pixels size (FP2's resolution)

Splash image will be saved to `./splash.img`


# Flashing the splash screen

> WARNING: Do at your own risk. I won't take any responsibility if this action bricks or damage your phone, although that seems unlikely. See the [Restoring original image](#restoring-original-image) section if your image does not work as expected.

## Requirements

- Fastboot Android SDK tool

### Debian/Ubuntu

Install `fastboot` or `android-sdk-platform-tools` if you want `adb` too

```
apt install android-sdk-platform-tools
```

## Flash the splash screen

Boot your Fairphone 2 in `fastboot` mode, either by `adb reboot bootloader` (if you installed `adb` too) or by holding `power down` while booting your Fairphone 2.

Then run this command:
```
fastboot flash splash splash.img
```

Replace `splash.img` with the path to your splash screen, if other.

To boot your phone again, run:

```
fastboot reboot
```

Alternatively, you can hold the power button for some seconds.

### Restoring original image

If your own splash screen didn't worked as expected, you can find official Fairphone 2 splash screens under the `official-splash-imgs` folder, here in the repo. `lp_splash.img` is the splash screen for Lollipop and `mm_splash.img` is the one for Marhsmallow. Take either file and flash it with the instructions provided above.
