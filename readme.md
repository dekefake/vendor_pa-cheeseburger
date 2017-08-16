## How i built pa_cheeseburger :

### [device tree](https://github.com/dekefake/android_device_oneplus_cheeseburger)
### [pocket judge kernel commit](https://github.com/dekefake/android_kernel_oneplus_msm8998/commit/e16f9b2c39b0d6b0e173c0193b2fb5f6c157bb80)


#### cameraservice.so :
libs dumped from OOS 4.5.8. I wasnt able to fix camera (missing shim _ZN7android18gClientPackageNameE), so i tried to replace these binaries, which ficed camera


#### TWRP flash :
flash pa_cheeseburger build, enjoy

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
* Bluetooth A2DP
* Camera
* Enforcing mode
* Video playing, mp4, flac, everything
* Gestures
* Pocket Judge

###### Not working :
* Tell me

![About Phone](https://raw.githubusercontent.com/dekefake/vendor_pa-cheeseburger/master/about.png)



