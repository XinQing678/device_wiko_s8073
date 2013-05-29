device_wiko_s8073
========================================
A vérifier :

BoardConfig.mk (partition size may diff)

recorvery.fstab (sdcard 2)

device_s8073.mk (LOCAL_KERNEL lines missing)


Get ready
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
	
android_device_wiko_s8073
=========================

Initialize repo:

	mkdir ~/bin
	PATH=~/bin:$PATH
	curl https://dl-ssl.google.com/dl/googlesource/git-repo/repo > ~/bin/repo
	chmod a+x ~/bin/repo

initialize repo with cm9 repository:

	mkdir ~/CM9
	cd ~/CM9
	repo init -u git://github.com/CyanogenMod/android.git -b ics

Now retrieve Wiko cink slim repositories:

	mkdir -p .repo/local_manifests
	wget https://github.com/wiko-repo/android_device_wiko_common/raw/ics/manifests/local_manifest.xml -O .repo/local_manifests/local_manifest.xml
	wget https://github.com/wiko-repo/android_device_wiko_s8073/raw/ics/ss8073_manifest.xml -O .repo/local_manifests/s8073_manifest.xml

And download:

	repo sync
	
Now prepare to build

	. build/envsetup.sh
	brunch s8073
