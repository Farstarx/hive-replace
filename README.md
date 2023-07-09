# hive-replace
Modified hive-replace script to run on Ubuntu 20.04

Based on https://github.com/minershive/hiveos-linux/blob/master/hive/sbin/hive-replace
Original script was mentioned in the official OS live replacement guide - https://hiveon.com/knowledge-base/guides/hive_replace/
Some day I needed to change a mining OS on a remote rig. The rig was working on Ubuntu 20.04 with manual installed NVIDIA drivers, overclock utilities and lolMiner.
I had no phisical access to that machine, but only ssh.

I made local tests with Ubuntu 18.04 and 20.04 LTS in Virtualbox. The original script worked with Ubuntu 18.04 only and without LVM partitions.
I added simple code trying to detect LVM root partition.

Second issue was broken chroot process at Ubuntu 20.04. Mainly because of symlinks /bin, /sbin, /lib and so on to corresponding /usr directories.
I also added plain if-statement detecting Ubuntu 20.04 which makes correct symlinks as well.

After I noticed at download page https://download.hiveos.farm/ pointing to a new hive-replace script https://download.hiveos.farm/hive-replace, version 2.1 (not synced with git one).
But I didn't test that.

Use it on your own risk. Check this on a test environment before applying on a remote machine.
