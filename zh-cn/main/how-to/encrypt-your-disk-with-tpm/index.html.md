Topics: [Installation](../_tags/installation.md) [Security](../_tags/security.md)

<a id="encrypt-your-disk-with-tpm"></a>

# Encrypt your disk with TPM

Hardware-backed disk encryption protects the data on your disk using the Trusted Platform Module (TPM) chip. It encrypts your Ubuntu installation and your whole disk. Compared to traditional encryption methods such as LUKS, hardware-backed disk encryption can provide more convenience or more security, depending on your configuration.

To learn how this encryption works, see [Hardware-backed disk encryption](../explanation/hardware-backed-disk-encryption.md#hardware-backed-disk-encryption).

## Enable the encryption during installation

You can enable hardware-backed encryption when you install Ubuntu Desktop. You cannot enable or disable it after installation.

To install Ubuntu with hardware-backed encryption:

1. Follow the instructions in [Install Ubuntu Desktop](../tutorial/install-ubuntu-desktop.md#install-ubuntu-desktop) until Disk setup.
2. On the Disk setup screen, select Erase disk and install Ubuntu ‣ Use hardware-backed disk encryption.

   #### IMPORTANT
   **Back up your data.** In this setup, Ubuntu overwrites your whole disk. All files will be deleted on the device where you’re installing Ubuntu.
3. Check if the installer reports any errors.

   Your system might not support all the required security features. In that case, the installer doesn’t allow you to proceed with TPM/FDE, or it requires that you set a PIN or a passphrase. For more information, refer to [Hardware-backed disk encryption requirements](../reference/hardware-backed-disk-encryption-requirements.md#hardware-backed-disk-encryption-requirements).

   In some cases, your system isn’t configured for TPM/FDE but it’s possible to reconfigure it. The Ubuntu installer suggests automated or manual actions to resolve this. Some actions might require you to reboot the system to apply the modifications in the firmware.
4. On the Create your account screen, set a secure password for all user accounts. Without an encryption passphrase, your data is only as safe as the weakest of the user passwords.
5. When the installation is done, the installer shows your recovery key for your encrypted disk.

   You can save the recovery key as a text file on another USB stick. You can also load the QR code with your phone or take a photo of the screen showing the recovery key.

   **Store it somewhere safe**, such as in a password manager.

   #### IMPORTANT
   If you lose your recovery key, you might lose access to your data in certain scenarios. While you’re logged in, replace the existing recovery key as soon as possible. See [Get a new recovery key](configure-hardware-backed-disk-encryption.md#tpm-fde-get-a-new-recovery-key).
6. After starting your new Ubuntu Desktop system, you can [configure a disk encryption PIN or passphrase](configure-hardware-backed-disk-encryption.md#tpm-fde-set-passphrase).

## Configure the encryption after installation

Refer to [Configure hardware-backed disk encryption](configure-hardware-backed-disk-encryption.md#configure-hardware-backed-disk-encryption).
