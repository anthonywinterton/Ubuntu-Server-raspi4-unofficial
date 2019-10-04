This is an initial testing pre-release of a unofficial build of Ubuntu Server 18.04.3 preinstalled server for the new (and currently unsupported officially) Raspberry Pi 4.<br>
<br>
I have included both the script to create it yourself from the official images as a base as well as a precompiled image that you can download and simply write straight to your SD card.  The included script makes the process of modifying the current official release to work on the Raspberry Pi 4 much easier.<br>
<br>
For more information visit https://jamesachambers.com/raspberry-pi-4-ubuntu-server-desktop-18-04-3-image-unofficial/ or including a walkthrough and lots of comments / discussion.<br>
<br>
All 4 GB of RAM are available in this preinstalled image.  WiFi, Bluetooth, and other drivers have been updated for the Raspberry Pi 4.<br>
<br>
This will hold the package so it doesn't break your installation while letting you fully update everything else until official support is released.<br>
<br>
To download the prebuilt image go to the "Releases" section to get the download.<br>
<br>
<strong>October 3rd 2019 - v10 Desktop Pre-Release</strong><br>
-Fixed issue with wireless not showing in v9<br>
-Fixed bad symlink creation (pull request #38)<br>
<br>
<strong>October 2nd 2019 - v9 Desktop Pre-Release</strong><br>
-Updated kernel and modules to rpi-4.19.75<br>
-start*.elf and fixup*.dat files (GPU firmware) are now updated with each release<br>
-Kernel .config has been updated with the latest default config and Sakiki-'s conform_config.sh parameters<br>
-New conform_config_jamesachambers.sh script added to better keep track of kernel config changes<br>
-SPI is now enabled<br>
-CPU bandwidth provisioning for FAIR_GROUP_SCHED is now enabled (CONFIG_CFS_BANDWIDTH=y)<br>
-Additional Ceph kernel config parameters enabled (see conform_config_jamesachambers.sh for all params)<br>
-A lot of additional hardware support has been enabled via the official Raspberry Pi default kernel config params -- if you were having trouble with a device try v9<br>
-Cleaned up build script by adding additional needed dependencies to apt-get commands, broke up some sections and added additional comments<br>
<br>
<strong>September 19th 2019 - v8 Desktop Pre-Release</strong><br>
-Updated kernel to rpi-4.19.73<br>
-Added hosts entry to prevent slow sudo command<br>
-Added CONFIG_CGROUP_PIDS=y to .config file<br>
-Committed extras folder to repository<br>
-Added forcefsck file to run fsck on first boot<br>
-Reduced image size substantially by running fstrim on .img<br>
<br>
<strong>September 8th 2019 - v7 Desktop Pre-Release</strong><br>
-Updated kernel to rpi-4.19.71<br>
-Added CONFIG_BLK_DEV_RBD=y to kernel .config file to enable Ceph support<br>
<br>
<strong>September 7th 2019 - v6 Desktop Pre-Release</strong><br>
-Updated kernel to rpi-4.19.71<br>
-Integrated all available updates from apt into the base image<br>
-Fixed display driver issue -- if you are running v5 you can fix it by commenting out dtoverlay=vc4-fkms-v3d from /boot/config.txt<br>
-Enabled Ceph support in the kernel .config<br>
-Added build flags to kernel build line to build a more complete device tree (dtbo files)<br>
-Integrated all upstream updates since v5 from raspberrypi-linux and firmware-nonfree including a 3d driver fix for aarch64<br>
<br>
<strong>September 3rd 2019 - v5 Desktop Pre-Release Test</strong><br>
-Desktop support added<br>
-Expect lots of warnings in the logs.  If you find solutions to them please leave a comment -- many commits come from the comments!<br>
-Be advised -- installing can take quite a while on a Pi -- overnight or when you have something to do is a good time<br>
-Type one the following commands to install your preferred flavor of Ubuntu Desktop:<br>
sudo apt-get install xubuntu-desktop # or<br>
sudo apt-get install kubuntu-desktop<br>
<br>
<strong>September 2nd 2019 - v4 Pre-Release Test</strong><br>
-Recompiled kernel to include support for Ubuntu features that are not present in Raspbian<br>
-Enabled USB UAS support<br>
-Fixed video driver by modifying config.txt and compiling with 3D support<br>
-System now boots clean and loads all modules (sudo systemd status)<br>
<br>
<strong>September 2nd 2019 - v3 Pre-Release Test</strong><br>
-Fixed IPV6 and several other modules not loading<br>
<br>
<strong>August 31st 2019 - v2 Pre-Release Test</strong><br>
-Boot time reduced from 100s to around 30s<br>
-Messing with apt-mark or flash-kernel is no longer necessary and the fix has been built into the image<br>
-Fixed bluetooth firmware bug that was looking in /etc/firmware instead of /lib/firmware<br>
-Fixed entropy bug causing slow startup<br>
-Fixed mdadm.conf RAID warning<br>
-Module.symvars is now available in /boot/firmware/ if you need it to build kernel modules<br>
-If you need the whole source tree check out the accompanying build script in the repository. It's exactly how the source tree used to build the kernel is built.<br>
-Various other fixes (special thanks to Joan at jamesachambers.com for contributing so many)<br>
