device_wiko_s8073
========================================
A vérifier :

BoardConfig.mk (partition size may diff)

Kernel

recorvery.fstab (sdcard 2)
<<<<<<< HEAD
device_s8073.mk (LOCAL_KERNEL lines missing)
=======

s8073.mk (LOCAL_KERNEL lines missing)


Get ready
>>>>>>> ba594f53492ec33443dd6ccbf81d27d4a80c49c3
========================================


initialize repo with cm9 repository:
	
	repo init -u git://github.com/CyanogenMod/android.git -b ics

Now retrieve Wiko Cink SLIM repositories (Should be using local_manifests.xml instead):

	for folder in device kernel vendor;
	do
		mkdir -p $folder/wiko/s8073;
		git clone "http://github.com/Pdroid/android_"$folder"_wiko_s8073.git" -b ics $folder/wiko/s8073;
	done


Now prepare to build

	. build/envsetup.sh
	brunch s8073
	
	
