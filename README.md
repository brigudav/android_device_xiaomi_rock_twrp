# Device Tree for building TWRP for Poco M5 (rock)

1.Getting Started
---------------
**Initialize local repo**
```
mkdir twrp-12
repo init -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
```
**Sync up with this command:**
```bash
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune --force-sync -j$(nproc --all)
```

2.Preparing device for building
---------------
**Clone this repo**
```bash
git clone https://github.com/brigudav/android_device_xiaomi_rock_twrp -b android-12.1 device/xiaomi/rock
```

3.Build
---------------
**Set up environment**
```bash
. build/envsetup.sh
```
**Build the recovery**
```bash
lunch twrp_rock-eng
mka vendorbootimage
```

* If also that is successful, congratulation!
* Go to `out/target/product/rock/` and you will find your vendor_boot.img
