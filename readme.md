## How i built pa_cheeseburger :

### [device tree](https://github.com/dekefake/android_device_oneplus_cheeseburger)

### [kernel commits](https://github.com/dekefake/oneplus5/commits/7.1.x-flash-custom) (Gestures commit only applicable to Flash kernel)

### [libcameraservice fix commit](https://github.com/dekefake/android_frameworks_av/commit/e238929654f52317ddc1cc49964c6fdebb85a6ff)
You need that commit onto AOSPA frameworks/av repo to get camera working.

#### Build PA for the Oneplus 5
First, repo sync [AOSPA](https://github.com/AOSPA/manifest).
Once your sources are up, navigate to vendor/pa.
In their vendorsetup, add the Oneplus 5 line from [my vendorsetup.sh](https://raw.githubusercontent.com/dekefake/vendor_pa-cheeseburger/master/vendorsetup.sh).
In their vendor/pa/products/AndroidProducts.mk, add the line from [my AndroidProduct.mk](https://raw.githubusercontent.com/dekefake/vendor_pa-cheeseburger/master/products/AndroidProducts.mk) file, or just use mine and totally remplace their one. Create a folder vendor/pa/products/cheeseburger and add [my files](https://github.com/dekefake/vendor_pa-cheeseburger/tree/master/products/cheeseburger) inside the folder.

At this time you can launch building by running "./rom-build.sh cheeseburger" from your ANDROID_BUILD_TOP folder. This will sync the dependencies you need. Then it will start building. I recommend you to stop the building process once the dependencies are synced using CRTL+C or CRTL+Z (You may need to tap the command twice)
Therefore, my repo's are all synced, but you miss the frameworks_av commit, and the kernel commits. Fell free to cherry-pick them from my repositories available [here](https://github.com/dekefake?tab=repositories).

In build/kernel/tasks.mk you will need to change the CROSS_COMPILE variable for arm64 from that :
````
KERNEL_CROSS_COMPILE := $(ANDROID_BUILD_TOP)/prebuilts/gcc/$(HOST_OS)-x86/aarch64/aarch64-linux-android-4.9/bin/aarch64-linux-androidkernel-
````
to that one :
````
KERNEL_CROSS_COMPILE := $(ANDROID_BUILD_TOP)/prebuilts/gcc/$(HOST_OS)-x86/aarch64/lianro-7.x/bin/aarch64-linaro-linux-androidkernel-
````

Now, run an "rm -rf out" and "./rom-build.sh cheeseburger" again. Should build without hiccup.


#### TWRP flash :
flash pa_cheeseburger build, enjoy

#### Reboot and profit.

#### Status :
###### Working :
* Wifi
* Bluetooth
* RIL
* GPS
* NFC (including paying !)
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
* Tell me

![About Phone](https://raw.githubusercontent.com/dekefake/vendor_pa-cheeseburger/master/about.png)



