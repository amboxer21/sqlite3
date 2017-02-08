# sqlite3
sqlite3 cross compiled for Android with PIE enabled
 
This is the sqlite3 pkg source code. 

A LINK TO a prebuilt binary:

https://drive.google.com/open?id=0B9WIkGjcMwgDUktaaTV3RjA0WTg

BUILDING ON YOUR OWN:

I cross compiled it to use on my Nexus 6 running 7.1.1. You must cross compile with the pie flags. The pie flags are used for systems where only position independent executables are supported.

The configure options I passed:
./configure --host=arm CC="/home/anthony/android-ndk-r13b/toolchains/arm-linux-androideabi-4.9/prebuilt/linux-x86_64/bin/arm-linux-androideabi-gcc-4.9 --sysroot=$SYSROOT" CFLAGS="-fPIE -pie"

If configure runs with no errors, then run make. Now you can push the exectuable to your device.

USING THE PREBUILT BINARY:

There is a pre-built binary file for sqlite3 in the source. I compiled and built this program, "THEN" uploaded. The one above works fine and was compiled with the PIE flag. Enjoy!

adb push sqlite3 /system/xbin/
chmod 775 /system/xbin/sqlite3

NOTE: Your system might not support PIE binary. If this is the case, set up a standalone toolchain to cross compile. I reccomend the NDK or you can email me at amboxer21@gmail.com
