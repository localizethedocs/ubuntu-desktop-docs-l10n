Topics: [Security](../_tags/security.md)

<a id="recover-data-from-hardware-backed-disk-encryption"></a>

# Recover data from hardware-backed disk encryption

If you know your [recovery key](../explanation/hardware-backed-disk-encryption.md#tpm-fde-recovery-key), you can access the data on your disk secured with [hardware-backed disk encryption](../explanation/hardware-backed-disk-encryption.md#hardware-backed-disk-encryption) (TPM/FDE) even from a different system. For example, you can unlock the disk while a live Linux session is running on your computer, or after you’ve connected the disk to another computer.

## What you’ll need

- You must know the recovery key to your disk.
- You must access the disk using a Linux system that can install snaps, such as using Ubuntu.
- The disk must not be corrupted.

## Unlock the disk

1. Check if the `snap` command is available on your system. If not, [install it](https://snapcraft.io/docs/tutorials/install-the-daemon/#tutorials-install-the-daemon-index).
2. Install the `snap-tpmctl` tool. You can either use the App Center or the following command:
   `$ ``sudo snap install snap-tpmctl`
3. Examine the partitions on your encrypted disk. On Ubuntu Desktop, you can use the Disks application.

   Note down the device path of the partition that you want to recover, such as `/dev/nvme0n1p4`.
4. Mount the encrypted partition:
   `$ ``sudo snap-tpmctl mount-volume /dev/nvme0n1p4 /mnt`

   Replace `/dev/nvme0n1p4` with your device path. Replace `/mnt` with the directory where you want to mount the partition.
5. Enter your recovery key when prompted.
6. In your file browser, open the mount point (such as `/mnt`) to access the data on the encrypted partition.

## Additional resources

- [Configure hardware-backed disk encryption](configure-hardware-backed-disk-encryption.md#configure-hardware-backed-disk-encryption)
