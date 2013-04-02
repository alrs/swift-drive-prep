# swift-drive-prep

swift-drive-prep prepares a drive for use by a Swift object storage node.  Care 
is taken to create a GPT partition table with a partition correctly aligned 
along native drive boundaries.  The importance of GPT partition alignment is 
described in the [sgdisk documentation](http://www.rodsbooks.com/gdisk/advice.html#alignment).

swift-drive-prep creates a single XFS partition across the entire drive.

swift-drive-prep is intended to be used as part of a larger automation scheme.
Care has been taken to be sure that it will not proceed if:

* The chosen disk is already mounted
* The chosen disk is already in fstab (currently only checks for device name, not UUID)


## usage

    swift-drive-prep <device>


## requirements

The following binaries are required:

* egrep
* mkfs.xfs
* mount
* partprobe
* sgdisk
* which
