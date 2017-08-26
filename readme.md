## How i built pa_cheeseburger :

### [device tree](https://github.com/dekefake/android_device_oneplus_cheeseburger)

### [pocket judge kernel commit](https://github.com/dekefake/android_kernel_oneplus_msm8998-1/commit/5db3986f212fe92acead9cd244a0452675e0ec0b)

### [libcameraservice fix commit](https://github.com/dekefake/android_frameworks_av/commit/e238929654f52317ddc1cc49964c6fdebb85a6ff)
You need that commit onto AOSPA frameworks/av repo to get camera working.


#### TWRP flash :
flash pa_cheeseburger build, enjoy

#### Reboot and profit.

#### Status :
###### Working :
* Wifi
* Bluetooth
* RIL
* GPS
* NFC (no paying)
* Sensors
* Fingerprint
* Alert slider (Including awesome AOSPA implementation)
* Dash Charge (Including message on lock screen)
* Bluetooth A2DP
* Camera (built from source)
* Enforcing mode
* Video playing, mp4, flac, everything
* Gestures
* Pocket Judge

###### Not working :
* Seems NFC cant pay
* Tell me

![About Phone](https://raw.githubusercontent.com/dekefake/vendor_pa-cheeseburger/master/about.png)



