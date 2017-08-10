## How i built pa_cheeseburger :

### [device tree](https://github.com/dekefake/android_device_oneplus_cheeseburger)



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
cp /system/su.d/permissive.sh /supersu/su.d/permissive.sh
chmod 777 /supersu/su.d/permissive.sh
```

#### Reboot and profit.

#### Status :
###### Working :
* Wifi
* Bluetooth
* RIL
* GPS
* Sensors
* Fingerprint
* Alert slider (Including awesome AOSPA implementation)
* Dash Charge (Including message on lock screen)

###### Not working :
* Bluetooth A2DP
* Camera (Video doesnt works, camera only works using fix zip)
* Enforcing mode
* Gestures

![About Phone](https://raw.githubusercontent.com/dekefake/vendor_pa-cheeseburger/master/about.png)



