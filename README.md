#  Recovery tree for realme GT Neo5 and realme GT Neo 5SE
Based on TWRP 16.0. For devices released with an Android 12 vendor with Snapdragon 8+ Gen 1 (SM8475) and Snapdragon 7+ Gen 2 (SM7475) processors

## Building

```bash
mkdir twrp && cd twrp
repo init -u https://github.com/TWRP-Test/platform_manifest_twrp_aosp.git -b twrp-16.0
repo sync --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j4
git clone https://github.com/MisterZtr/recovery_device_realme_senna.git device/realme/senna
. build/envsetup.sh
breakfast twrp_pineapple-bp2a-eng
make installclean
mka adbd recoveryimage -j6
```

## To use it:

```
fastboot flash recovery out/target/product/senna/recovery.img
```
