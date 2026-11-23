Topics: [Installation](../_tags/installation.md)

<a id="install-ubuntu-desktop"></a>

# Install Ubuntu Desktop

<!--
Original source: <https://discourse.ubuntu.com/t/install-ubuntu-desktop/25312/>
Original author: Oliver Smith <oliversmith@canonical.com>
-->

In this tutorial, we’ll download and install Ubuntu Desktop 26.04 LTS on your laptop or PC.

If you’ve never installed an operating system, don’t worry: Ubuntu makes the process very easy. You’ll encounter a guided installer that will ask you a couple of questions. Whenever you’re not sure what to pick, you can just select the default option, which ensures that you end up with a fully usable Ubuntu installation. No deep technical knowledge is required.

What you’ll need:

* A laptop or PC with at least 25GB of storage space.
* A flash drive, 8GB or above recommended.

## Will Ubuntu work on my computer?

While Ubuntu works on a wide range of devices, it’s best to use a device listed on the [Ubuntu certified hardware](https://ubuntu.com/certified?q=&amp;category=Laptop&amp;category=Desktop&amp;limit=20) page. These devices have been tested and confirmed to work well with Ubuntu.

If you can’t see your device there, you can always just [Try Ubuntu Desktop](try-ubuntu-desktop.md#try-ubuntu-desktop) and check if everything works as expected.

If you want to run Ubuntu on **Apple Silicon** hardware, such as recent Macs using M1 CPUs or later, refer instead to the [Ubuntu Asahi](https://ubuntuasahi.org/) community project, which isn’t supported by Canonical. The hardware support might be limited and depends on your specific machine. For example, Ubuntu Asahi 25.10 only runs on systems with M1 and M2 CPUs.

You can also install Ubuntu in a virtual machine on top of your current system using [Multipass](https://documentation.ubuntu.com/multipass/).

For guidance on installing Ubuntu on platforms based on architectures other than x86 (including **ARM** or **RISC-V** boards, such as **Raspberry Pi**), see [Ubuntu hardware support documentation](https://ubuntu.com/hardware/docs/).

<a id="installation-back-up-your-data"></a>

## Back up your data

If you’re installing Ubuntu on a PC or laptop that you’ve used previously, back up your data before you start the installation:

* Move any **files** that you want to keep to another storage device, such as an external disk or a USB drive.
* To back up your **web browser**, connect your browser to an online account, such as a Firefox account or a Google account. After the Ubuntu installation, your browser synchronizes your data when you log into your account. Note that the Safari browser doesn’t work on Ubuntu.

Back up your files from the **USB flash drive**. The drive will be erased.

<!--
The docs/reuse/boot-ubuntu-from-usb.txt file is reused between the live system tutorial and the installation tutorial.
-->

## Download an Ubuntu image

Get the Ubuntu installation image from the [Download Ubuntu Desktop](https://ubuntu.com/download/desktop) page. Save it to a memorable location on your PC. The downloaded file is called `ubuntu-26.04-desktop-amd64.iso` or similar.

![The Download Ubuntu Desktop page](images/download-an-ubuntu-image.png)

## Create a bootable USB stick

Write the downloaded Ubuntu image to a USB stick to create the installation media. This is not the same as copying the downloaded image file: you have to use special software.

#### WARNING
This will erase your USB stick. Back up your files first.

The application that we’ll use depends on the system that you’re currently using.

### On Ubuntu

<!--
The docs/reuse/usb-using-gnome-disks.txt file is reused between the live system tutorial, the installation tutorial and the bootable USB how-to guide.
-->
1. Open the Disks application. You can find it in the applications menu or by searching for “Disks”.
2. Insert your USB stick. It appears in the sidebar. Select it there.

   #### WARNING
   Make sure to select the USB stick and **not** the disk with your running system. Both are listed.

   ![A USB stick selected in Disks](images/usb-in-gnome-disks.png)
3. Close all applications that access files or folders on the USB stick, including the file browser.
4. In the Disks window header, click Drive Options (⋮) and select Restore Disk Image…

   ![Restore Disk Image in the menu](images/restore-disk-image-menu.png)
5. Next to Image to Restore, select the downloaded Ubuntu image file.
6. Click Start Restoring… and confirm. The application asks for your password.

   ![The Restore Disk Image dialog](images/restore-disk-image-dialog.png)
7. A progress bar appears while Disks is writing the image.

   ![Disks writing the image to USB](images/gnome-disks-restoring-image.png)
8. When the progress bar finishes, click Eject this disk (⏏).

   ![Writing finished. Partitions are listed on the USB](images/gnome-disks-finished-writing.png)

### On Windows

<!--
The docs/reuse/usb-using-rufus.txt file is reused between the live system tutorial, the installation tutorial and the bootable USB how-to guide.
-->
<!--
Originally a Tutorial: https://discourse.ubuntu.com/t/create-a-bootable-usb-stick-with-rufus-on-windows/14020
| Summary | How to write a USB stick with Windows. |
| Author |  <oliversmith@canonical.com> |
-->
1. Download and install the latest version of Rufus from the [rufus.ie](https://rufus.ie/) website.

   If you’re using Windows 7, install [version 3.22](https://github.com/pbatard/rufus/releases/download/v3.22/rufus-3.22.exe) of Rufus. On Windows XP or Vista, install [version 2.18](https://github.com/pbatard/rufus/releases/download/v2.18/rufus-2.18.exe).
2. Launch Rufus. If prompted, allow online updates.

   #### NOTE
   Rufus presents many options in its interface. It’s safe to leave most of them with their default values.
3. Insert your USB stick. It appears in the Device field.

   If Device shows the wrong USB device, select the correct one from the drop-down menu.

   ![Selected a USB drive in Rufus](images/rufus/rufus-detects-usb.png)
4. Click SELECT next to Boot selection. Choose the Ubuntu image file that you’ve downloaded and confirm by clicking Open.

   If the button reads DOWNLOAD instead, click the dropdown and change it to SELECT first.

   ![Selected the ISO file in Rufus](images/rufus/rufus-iso-selected.png)
5. If you’ve already tried Rufus and the USB stick failed to boot on your system, change Partitioning scheme to GPT and check that Target system is set to UEFI (non CSM). This works on modern systems that disable legacy compatibility.
6. Click START to write the image to USB.
7. Rufus tells you that the Ubuntu image is an *ISOHybrid image*. This means that the same image file can be used as the source for both a USB stick and a DVD.

   Confirm the *Write in ISO Image mode* option.

   !["ISOHybrid image detected" dialog](images/rufus/rufus-isohybrid-image.png)
8. If Rufus asks to download additional files to complete writing the image, select Yes to continue.
9. Rufus warns you that all data on the USB device is about to be destroyed. Double-check that you’ve selected the correct device and confirm by clicking OK.

   ![Rufus warning you about data loss](images/rufus/rufus-data-warning.png)
10. Rufus is now writing the image to USB. This usually takes around 10 minutes.

    ![Rufus copying ISO files](images/rufus/rufus-copying-iso-files.png)
11. When Rufus has finished writing to the USB device, the Status bar says READY.

    Click CLOSE to complete the write process.

    ![Rufus finished writing the ISO](images/rufus/rufus-finished-writing.png)

### On macOS

<!--
The docs/reuse/usb-using-balena-etcher-on-macos.txt file is reused between the live system tutorial, the installation tutorial and the bootable USB how-to guide.
-->
<!--
Originally a Tutorial: https://discourse.ubuntu.com/t/create-a-bootable-usb-stick-on-macos/14016
| Summary | How to write a USB stick with macOS. |
| Author | Canonical Web Team <webteam@canonical.com> |
-->
<!--
This part no longer applies because the Scheme option no longer exists in recent macOS (since 2020).

To ensure compatibility with Apple hardware, reformat the USB stick with the GUID partition table. You can skip this part if you intend to use the USB stick only with PC hardware:

1. Launch the \*Disk Utility\* app from {menuselection}\`Applications -> Utilities\` or from the Spotlight search.

1. Insert your USB stick. It appears in the sidebar. Select it there.

    You might need to enable the {menuselection}\`View -> Show All Devices\` option.

    :::{warning}
    Make sure to select the USB stick and \*\*not\*\* your internal macOS disk. Both are listed.
    :::

1. Select {guilabel}\`Erase\` from the toolbar.

1. Set the format to \*MS-DOS (FAT)\* and the scheme to \*GUID Partition Map\*.

1. Check that you've chosen the correct device and click {guilabel}\`Erase\`.

1. Close the Disk Utility.

Write the Ubuntu image to the USB stick:
-->
1. Insert the USB stick.
2. At the [balenaEtcher website](https://etcher.balena.io/), download **Etcher for macOS (arm64)** if you’re using an Apple Silicon machine, or download **Etcher for macOS** if you’re using an Intel Mac.

   ![The Download Etcher page](images/download-etcher.png)
3. Install and open balenaEtcher.
4. Click Flash from file and select the downloaded Ubuntu image.

   By default, the image file will be in your Downloads folder.
5. Click Select target and choose your USB stick.

   ![The Select target step in Etcher](images/macos-usb-etcher-config.jpg)
6. Click Flash! to write the image to USB.

### Other

See the [exhaustive how-to guide](../how-to/create-a-bootable-usb-stick.md#create-a-bootable-usb-stick) for other platforms and alternative image writers.

Now you have a USB stick that works as Ubuntu installation media.

## Boot from the USB flash drive

1. Insert the USB stick into the laptop or PC where you want to install Ubuntu.
2. Restart the computer.
3. Your device should recognize the installation media and launch the Ubuntu installer.
4. If Ubuntu doesn’t launch, restart your computer again. This time, hold a key during startup:
   * On a **PC or Windows** computer, `F12` is the most common key for bringing up the system boot menu but `Escape`, `F2` and `F10` are common alternatives. If unsure, look for a brief message when your system starts: this often informs you which key to press to access the boot menu. You can also find the right key in the documentation for your laptop or PC.

     In the boot menu that appears, select your USB device.
   * To start Ubuntu on **Apple hardware**, restart or power-on the Mac with the USB stick inserted while you hold the `Option` or `Alt` (`⌥`) key.

     This launches the Startup Manager, which shows bootable devices connected to the machine. Your USB stick should appear as gold or yellow and be labeled **EFI Boot**. Select it to proceed to the standard Ubuntu boot menu.

     ![Boot device selection](images/macos-usb-efi-boot.png)

## Follow the installer

The Ubuntu Desktop installer opens.

1. Choose your language.

   ![The Choose your language page](images/installer/choose-your-language.png)
2. Select any accessibility settings that your require.

   ![The Accessibility page](images/installer/accessibility.png)
3. Select your keyboard layout.

   ![The Keyboard layout page](images/installer/keyboard-layout.png)
4. Connect to your network.

   This allows Ubuntu to download updates and third party drivers, such as NVIDIA graphics drivers, during installation.

   ![The Internet connection page](images/installer/internet-connection.png)

   The network connection is optional. If you can’t connect, the Ubuntu installation will still work.
5. The installer gives you the choice to try or install Ubuntu.

   If you click Try Ubuntu, you can preview Ubuntu without making any changes to your PC. You can use the preview to test if your hardware works correctly with Ubuntu. You can then return to the installer menu at any time by clicking the Install Ubuntu shortcut on the desktop.

   ![The Try or install Ubuntu page](images/installer/try-or-install-ubuntu.png)

   To proceed, click Install Ubuntu.

#### WARNING
Some PCs use Intel RST (Rapid Storage Technology), which is not supported by Ubuntu. If this is the case, you won’t be able to proceed with the installation unless you disable RST on your machine.

If you encounter this alert, see [Reconfigure Windows to use AHCI](../how-to/reconfigure-windows-to-use-ahci.md#reconfigure-windows-to-use-ahci) to resolve the issue. To learn more, see [Intel RST during Ubuntu installation](../reference/intel-rst-during-ubuntu-installation.md#intel-rst-during-ubuntu-installation).

## Type of installation

Here, you can select how you want to be guided through the installation and what software you want to install.

1. Choose between an interactive and automated installation.

   The **interactive** option is the standard route for most users.

   With the **automated** installation options, advanced users can define their installation beforehand to standardize multiple systems and add further customization. These options require you to load a configuration file from another USB stick, from a web server or from the [Landscape](https://ubuntu.com/landscape) administration tool. An example tutorial for an automated installation is available at [Getting started with Autoinstall on Ubuntu Desktop 24.04 LTS](https://blog.local-optimum.net/getting-started-with-autoinstall-on-ubuntu-desktop-24-04-lts-147a1defb2de).

   ![The Type of installation page](images/installer/type-of-installation.png)

   In this tutorial, we’ll follow the **interactive** installation.
2. Choose between the Default selection and Extended selection options.

   The default installation comes with the basic essentials to get started, which you can then expand on after install using the App Center. The extended selection contains additional office tools and utilities.

   You can always install all these applications later if you have an internet connection.

   ![The Applications page](images/installer/applications.png)
3. Here, you can install third-party software. It can improve device support and performance (for example, NVIDIA graphics drivers) and adds support for additional media formats.

   We recommend that you enable both options.

   ![The Optimise your computer page](images/installer/optimise-your-computer.png)

## Disk setup

Select how Ubuntu should be installed on the disk:

* If you’d like Ubuntu to be the only operating system on your hard drive, select Erase disk and install Ubuntu. This is the easiest option.
* Manual installation is intended for expert users.
* If your device currently has another operating system installed, you also have the options to install Ubuntu alongside that system.

![The Disk setup page](images/installer/disk-setup.png)

Let’s take a moment to review all of the above options in detail.

### Erase disk and install Ubuntu

If you select this option, Ubuntu takes up the entire disk space on the selected drive.

If your PC has multiple hard drives, you can select where Ubuntu is installed. This option allows you to install Ubuntu alongside an existing OS as long as they each have their own drive.

#### WARNING
Ensure that you’re selecting the right drive in this case.

### Encrypt your data

If you want to encrypt your data, you can enable disk encryption after you select the Erase disk and install Ubuntu option:

![The Encryption and file system page](images/installer/encryption-and-file-system.png)

Select a disk encryption method:

- Encrypt with a passphrase is the recommended encryption option.
- Use hardware-backed encryption is a more convenient encryption method that only works on recent PCs.

  See [Hardware-backed disk encryption](../explanation/hardware-backed-disk-encryption.md#hardware-backed-disk-encryption).
- Other encryption options are available when you click Advanced options.

  See [Advanced disk setup features](../reference/advanced-disk-setup-features.md#advanced-disk-setup-features).

Depending on which encryption you’ve selected, the installer might ask you to create a passphrase that you’ll need to enter during every system startup to unlock the disk.

![The Disk passphrase page](images/installer/disk-passphrase.png)

#### WARNING
Keep your passphrase safe and don’t lose it. Write it down and store it in a safe place outside of your local system. **You won’t be able to recover your data without the password.**

### Manual partitioning

Manual partitioning is designed for **advanced users** who want to create a specific configuration for their use case. If that’s you, we assume that you know what you’re doing and that you’re comfortable with the installer interface.

Here, you can see all existing drives and partitions. You can create and manage new partition tables and configurations.

![The Manual partitioning page](images/installer/manual-partitioning.png)

If the interface doesn’t make sense, we recommend that you pick one of the automated disk setup options instead.

### Installing Ubuntu alongside another operating system

If you select this option, you’ll be able to select the drive where you want to install Ubuntu and the amount of disk space that you’d like Ubuntu to use. The available space is limited by the size that the files on the disk occupy. Ubuntu will preserve all existing files.

This view automatically selects the largest partition on the drive. For more control, you can switch to the Manual partitioning option.

![The Install Ubuntu alongside other partitions page](images/installer/install-ubuntu-alongside-other-partitions.png)

### Alert: Windows BitLocker is enabled

If your device has Windows BitLocker Drive Encryption enabled, the installer can’t access the encrypted Windows installation. Because of that, it can’t install Ubuntu safely alongside Windows.

<!--
If the installer detects BitLocker, it points you to the help.ubuntu.com/bitlocker URL.

This is a redirect to the last page of the installation tutorial, which explains BitLocker.

The redirect is configured in the .htaccess file in the Help repository:
https://code.launchpad.net/~ubuntu-core-doc/help.ubuntu.com/help.ubuntu.com
-->

![The BitLocker is enabled page](images/installer/bitlocker-is-enabled.png)

You can either erase Windows and replace it with Ubuntu, or you can disable BitLocker and install Ubuntu alongside Windows. To disable BitLocker, see [Turn off BitLocker in Windows](../how-to/turn-off-bitlocker-in-windows.md#turn-off-bitlocker-in-windows). To learn more, see [BitLocker during Ubuntu installation](../reference/bitlocker-during-ubuntu-installation.md#bitlocker-during-ubuntu-installation).

Alternatively, you can install Ubuntu to a separate, unencrypted disk if it’s available on the system.

## User and password

On this screen, enter your name and pick a name for your computer as it will appear on the network. Enter your user name and a strong password.

You can choose to log in automatically or require a password. If you use your device while traveling, it’s recommended to keep Require my password to log in enabled.

![The Create your account page](images/installer/create-your-account.png)

## Select your timezone

Select your location and timezone from the map screen. Ubuntu can detect your location automatically if you’re connected to the internet.

![The Select your timezone page](images/installer/select-your-timezone.png)

## Ready to install

Here, you can see a summary of your installation configuration. Review  your setup before clicking Install.

![The Ready to install page](images/installer/ready-to-install.png)

#### NOTE
If you choose to import an autoinstall configuration at the start of the installation process, the installer takes you directly to this screen to confirm that your configuration is correct.

Once you proceed, Ubuntu begins the installation process.

## Complete the installation

Sit back and enjoy the slideshow as Ubuntu installs in the background.

![The installation slideshow](images/installer/slideshow.png)

Alternatively, you can watch a detailed output of the installation process by clicking the icon in the lower right corner of the window.

When the installation has completed, the installer prompts you to restart your machine. Click Restart Now.

![The Installation complete page](images/installer/installation-complete.png)

When you restart, Ubuntu asks you to remove your USB flash drive from the device. Then, press Enter.

![The Remove the installation medium prompt](images/installer/remove-the-installation-medium.png)

## Your new system is starting

Enter your disk encryption passphrase if you created one.

![The disk passphrase prompt](images/installer/unlock-disk.png)

At the login screen, enter your user name and password.

![The Ubuntu login screen](images/installer/login-screen.png)

And that’s it. Welcome to your new Ubuntu Desktop!

![The Ubuntu 26.04 desktop](images/installer/ubuntu-26-04-desktop.png)

The Initial Setup app will help you with some additional setup options:

* Enabling location services.
* Opting into sending device information to Canonical to help improve Ubuntu.

  By default, Canonical doesn’t collect device information.
* Customizing the color scheme.
* Downloading additional apps from App Center.

## Don’t forget to update

It’s always good practice to ensure your system is up to date, especially after a fresh install.

The easiest way to do this is via the **Software Updater** app. Search for Software Updater via the app menu (the Ubuntu icon in the bottom corner of your screen). It will check for updates and apply them.

![The Ubuntu Software Updater](images/software-updater.png)

You can also update Ubuntu using the terminal:

1. Press `Ctrl+Alt+T` to bring up a Terminal window.
2. Type in:
   `$ ``sudo apt update`

   You will be prompted to enter your login password.

   This will check for updates and tell you if there are any that need applying.
3. To apply any updates, type:
   `$ ``sudo apt upgrade`
4. Type **Y**, then press `Enter` to confirm to finish the update process.

For details, see [Updating the system with APT](https://documentation.ubuntu.com/server/tutorial/managing-software/#updating-the-system-with-apt) in the Ubuntu Server documentation.

## You’ve installed Ubuntu

We hope you enjoy your new desktop.

If you backed up your data, you can now move them back into Ubuntu. If you backed up your web browser account, log in to synchronize your data.

Keep your system safe. Consider enabling [Ubuntu Pro](https://ubuntu.com/pro) in the Security Center to receive extended security updates. Ubuntu Pro is free for personal use on up to 5 machines.

If you have any issues, please contact us via the [Ubuntu Discourse](https://discourse.ubuntu.com/).

You can also read the latest news about Ubuntu Desktop on the [Ubuntu Blog](https://ubuntu.com/blog/desktop).

If you need to run both Ubuntu and Windows, you can [install Ubuntu on Windows Subsystem for Linux (WSL)](https://documentation.ubuntu.com/wsl/stable/).
