Topics: [Introduction](../_tags/introduction.md)

<a id="try-ubuntu-desktop"></a>

# Try Ubuntu Desktop

In this tutorial, you’ll try Ubuntu Desktop 26.04 LTS on your computer without making any permanent changes. Ubuntu Desktop will run from a USB drive and your data will be safe.

What you’ll need:

* A laptop or PC.
* A flash drive, 8GB or above recommended.

## Will Ubuntu work on my computer?

You can test Ubuntu from a USB drive on any computer to see if it works.

You can also try to find your computer on the [Ubuntu certified hardware](https://ubuntu.com/certified?q=&amp;category=Laptop&amp;category=Desktop&amp;limit=20) page. These devices have been tested and confirmed to work well with Ubuntu.

If you want to run Ubuntu on **Apple Silicon** hardware, such as recent Macs using M1 CPUs or later, refer instead to the [Ubuntu Asahi](https://ubuntuasahi.org/) community project, which isn’t supported by Canonical. The hardware support might be limited and depends on your specific machine. For example, Ubuntu Asahi 25.10 only runs on systems with M1 and M2 CPUs.

You can also install Ubuntu in a virtual machine on top of your current system using [Multipass](https://documentation.ubuntu.com/multipass/).

For guidance on installing Ubuntu on platforms based on architectures other than x86 (including **ARM** or **RISC-V** boards, such as **Raspberry Pi**), see [Ubuntu hardware support documentation](https://ubuntu.com/hardware/docs/).

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

The Ubuntu Desktop installer opens. We’ll use it to set a couple of options. Then we’ll close it without installing anything on your computer.

1. Choose your language.

   ![The Choose your language page](images/installer/choose-your-language.png)
2. Select any accessibility settings that your require.

   ![The Accessibility page](images/installer/accessibility.png)
3. Select your keyboard layout.

   ![The Keyboard layout page](images/installer/keyboard-layout.png)
4. Connect to your network.

   This allows Ubuntu to download updates and third party drivers, such as NVIDIA graphics drivers, during installation.

   It also allows you to use a web browser in the Ubuntu preview.

   ![The Internet connection page](images/installer/internet-connection.png)

   The network connection is optional. If you can’t connect, the Ubuntu preview will still work.
5. The installer gives you the choice to try or install Ubuntu.

   Click Try Ubuntu so that you can preview Ubuntu without making any changes to your PC.

   ![The Try or install Ubuntu page](images/installer/try-or-install-ubuntu.png)

## Test the Ubuntu preview

The installer closes. Use the preview to test if your hardware works correctly with Ubuntu.

Note that this preview of Ubuntu only uses open-source drivers. If your hardware requires proprietary drivers, such as for NVIDIA graphics cards, they are missing in this environment. You can enable them during the Ubuntu installation or later.

Look around the interface. Try out how Ubuntu is controlled. See what applications are available.

## Install Ubuntu or return to your system

If you decide to install Ubuntu, return to the installer menu at any time by clicking the Install Ubuntu shortcut on the desktop. See [Install Ubuntu Desktop](install-ubuntu-desktop.md#install-ubuntu-desktop) to proceed with the installation. If you have any data on your computer that you want to keep, make sure to [back up your data](install-ubuntu-desktop.md#installation-back-up-your-data) first.

When you’re done testing Ubuntu and you don’t want to install it, you can reboot the computer and return to your regular system:

1. Click the menu in the upper right corner of the screen on the top bar.
2. Click the power button.
3. Select Restart and confirm.
4. Ubuntu asks you to remove your USB flash drive from the device. Once you’ve done this, press Enter.

   ![The Remove the installation medium prompt](images/installer/remove-the-installation-medium.png)
5. Your computer restarts and loads your regular system.
