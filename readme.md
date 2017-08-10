## How i built pa_cheeseburger :

### [device tree](https://github.com/dekefake/android_device_oneplus_cheeseburger)

#### SKIA will fail to compile. You need [that commit](https://github.com/AOSP-CAF/platform_external_skia/commit/9cd042619597a6d0ddf32adf7cb2574a07c033a7). 


#### Fix.zip :
contains boot.img from early august carbonrom weekly and permissive script, as i wasnt able to get a working kernel built from source. With built kernel, phone stays a minute on splash screen, and then black screen with the led notification lightning blue. Flashing carbonrom boot.img fixes that but as sepolicy might be different, you need permissive to boot.

#### camerafix.zip :
contains OOS 4.5.8 camera related binaries. I wasnt able to fix camera (missing shim _ZN7android18gClientPackageNameE), so i tried that random fix, witch worked.


#### TWRP flash :
flash pa_cheeseburger build, fix.zip, supersu2.82, (and camerafix.zip)


###### if you clean flashed, TWRP terminal emulator :

```
mkdir /supersu
mount -o loop /data/su.img /supersu
cp /system/su.d/permissive.sh /su/su.d/permissive.sh
chmod 777 /su/su.d/permissive.sh
```

#### reboot and profit

![About Phone](https://raw.githubusercontent.com/dekefake/vendor_pa-cheeseburger/master/about.png)

