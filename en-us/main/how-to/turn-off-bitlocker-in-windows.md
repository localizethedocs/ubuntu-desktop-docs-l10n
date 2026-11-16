Topics: [Installation](../_tags/installation.md) [Security](../_tags/security.md) [Windows](../_tags/windows.md)

<a id="turn-off-bitlocker-in-windows"></a>

# Turn off BitLocker in Windows

You can disable the BitLocker disk encryption used by Windows so that Ubuntu can access the data. This might be necessary to install Ubuntu alongside Windows.

To learn more about BitLocker and its implications for Ubuntu, see [BitLocker during Ubuntu installation](../reference/bitlocker-during-ubuntu-installation.md#bitlocker-during-ubuntu-installation).

#### WARNING
Certain versions of Windows will no longer allow you to re-enable BitLocker after disabling it.

If you wish to re-encrypt your Windows partition after installing Ubuntu alongside it, check that your version of Windows supports this.

1. Back up your data:

   Any encryption procedure, hard drive structure change or installation of new operating systems on a hard drive that already contains data can potentially lead to a data loss. Make sure that your personal data is safe. Even simply copying the important files to an external drive minimizes the risk of data loss.
2. Disable encryption:

   ### On Windows 11

   Open the Settings app and go to Privacy & Security ‣ Device Encryption.

   Toggle it off.

   ### On earlier Windows releases

   Go to Control Panel ‣ System and Security ‣ BitLocker Drive Encryption.

   #### NOTE
   If the status is “BitLocker waiting for activation”, it means that BitLocker is enabled but your data isn’t encrypted yet. Enable BitLocker first by clicking Turn on BitLocker.

   Click Turn off BitLocker to disable encryption.

   ![The BitLocker Drive Encryption settings in Windows](images/bitlocker-drive-encryption.png)
3. Windows informs you that it is going to decrypt the data.

   ![The Turn off BitLocker dialog](images/turn-off-bitlocker.png)

   Wait until it’s done.

   ![The BitLocker decryption progress dialog](images/bitlocker-decryption-progres.png)

   ![The BitLocker decryption notice](images/bitlocker-decryption-complete.png)
4. Once the decryption is complete, reboot the computer.
5. Log into Windows. Make sure everything works correctly and that all your data is intact.
6. The Windows data is now accessible to Ubuntu.

   If you’re installing Ubuntu, you can now reboot your computer and launch the Ubuntu installer. The hard disk configuration step can proceed.
