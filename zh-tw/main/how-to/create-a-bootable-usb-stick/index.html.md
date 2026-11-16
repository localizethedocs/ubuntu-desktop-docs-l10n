Topics: [Installation](../_tags/installation.md) [Windows](../_tags/windows.md) [macOS](../_tags/macos.md)

<a id="create-a-bootable-usb-stick"></a>

# Create a bootable USB stick

You can convert your USB stick (USB flash drive) into Ubuntu installation media. This is different from copying a file to the USB stick. Instead, use a specialized application to rewrite your USB stick with Ubuntu. Select an application depending on the system that you’re currently using.

With a bootable Ubuntu USB stick, you can:

- Install or upgrade Ubuntu.
- Test out the Ubuntu Desktop experience without touching your PC configuration.
- Boot into Ubuntu on a borrowed machine.
- Use tools from the USB stick to repair or fix a broken configuration.

You need:

- An 8GB USB stick or larger.

  #### WARNING
  Back up your files on the USB stick. This process will overwrite and destroy all data stored there.
- An Ubuntu image file. See [Download Ubuntu Desktop](https://ubuntu.com/download/desktop).

  Take note of where your browser saves the downloaded file. This is normally a directory called *Downloads*. Don’t download the ISO image directly to the USB stick.

  Proceed only when the download has successfully finished.

## On Ubuntu and other Linux distributions

Ubuntu Desktop comes with the Disks application by default, which you can use to write the image. Other Linux distributions provide a wide range of different image writer applications. Choose the first one that’s available on your system.

### Using Disks

The Disks application is installed by default on Ubuntu Desktop and on most Linux distributions that use the GNOME desktop environment. We recommend choosing it if it’s available on your system.

Disks can also write images of any other operating system, including Linux distributions or Microsoft Windows.

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

### Using Startup Disk Creator

<!--
Originally a Tutorial: https://discourse.ubuntu.com/t/create-a-bootable-usb-stick-on-ubuntu/14011/
| Summary | Use your Ubuntu desktop to create a bootable USB stick that can be used to run and install Ubuntu on any USB-equipped PC. |
| Author | Canonical Web Team <webteam@canonical.com> |
-->

The Startup Disk Creator application is part of the extended Ubuntu Desktop installation. You can use it to write an Ubuntu image to a USB stick.

#### WARNING
Startup Disk Creator is intended for Ubuntu images and images of other distributions based on Ubuntu, such as flavors like Kubuntu or Xubuntu, or derived distributions. It might not work correctly with other Linux distributions and different operating systems.

1. Insert your USB stick.
    <!--
    If Ubuntu asks you what to do with it, select {guilabel}\`Do nothing\`.
    -->
2. Close all applications that access files or folders on the USB stick, including the file browser.
3. Search your applications for *Startup Disk Creator*.

   ![Launch Startup Disk Creator](images/launch-startup-disk-creator.png)
4. If the application isn’t available, install it in the App Center.

   Alternatively, you can install it on the command line:
   `$ ``sudo apt install usb-creator-gtk`
5. Open Startup Disk Creator.
6. Check the Source disc image and Disk to use fields.

   It’s likely that your Ubuntu image and the correct USB device have been detected. If not, use the Other button to locate your image file and select the USB device that you want to use from the list of devices.

   ![The Make Startup Disk window with Ubuntu 24.04 and a USB drive](images/startup-disk-creator.png)
7. Click Make Startup Disk and confirm that this is the correct USB device.

   Any data currently stored on this device will be **destroyed**.
8. The write process starts and a progress bar appears.

   When finished, the application announces “Installation Complete”.

### Using KDE ISO Image Writer

KDE ISO Image Writer is part of the KDE Plasma desktop environment. You can use it on distributions like Kubuntu. It’s available for Ubuntu and Kubuntu 26.04 LTS and later.

1. Go to the [releases.ubuntu.com](https://releases.ubuntu.com/) website and find the Ubuntu release that you’re writing on your USB stick, such as [Ubuntu 26.04 LTS (Resolute Raccoon)](https://releases.ubuntu.com/resolute/).
2. Download the `SHA256SUMS` and `SHA256SUMS.gpg` checksum files. In the file selector, make sure not to attach the `.txt` suffix to the `SHA256SUMS` file. Place the files in the same directory as the Ubuntu image.

   KDE ISO Image Writer uses these files to verify the Ubuntu image.
3. Insert the USB stick.
4. Close all applications that access files or folders on the USB stick, including the file browser.
5. Install KDE ISO Image Writer in the Discover app store or on the command line:
   `$ ``sudo apt install isoimagewriter`
6. Open KDE ISO Image Writer.
7. In the ISO image field, select the downloaded Ubuntu image. KDE ISO Image Writer starts verifying the image according to the checksum files.
8. In the USB drive field, make sure that the correct USB stick is selected.

   ![KDE ISO Image Writer with a selected USB drive and a verified ISO image. It says "The ISO image is valid"](images/kde-iso-image-writer.png)
9. Click Create to start writing the Ubuntu image to USB. Confirm with your password.
10. When KDE ISO Image Writer finishes writing, click Close.

### Using the Linux command line

The `dd` image writer is available on all Linux systems. You can use it even on minimal systems without any graphical environment.

#### WARNING
The `dd` tool is designed for advanced users. If you specify the wrong options, disk or file names, you might destroy your running system.

1. Insert your USB stick.
2. Make sure that the USB stick is large enough for the Ubuntu image. If it’s too small, the image writer might silently fail.
3. List storage devices on your system:
   `$ ``lsblk --scsi`
   ```text
   NAME
       HCTL       TYPE VENDOR   MODEL          REV SERIAL               TRAN
   sda 0:0:0:0    disk SanDisk  Ultra USB 3.0 1.00 4C530000010118116183 usb
   ```

   In this example, one USB stick is connected. Note down its device name at the start of the line, such as `sda` here.
4. Unmount all file systems on the USB stick:
   `$ ``sudo umount /dev/sda*`

   Replace `sda` with the USB device name.
5. Write the Ubuntu image to the USB stick:
   `$ ``sudo dd if=Downloads/ubuntu-26.04-desktop-amd64.iso of=/dev/sda bs=4M conv=fsync status=progress`

   Double-check the file paths in this command:
   * The `if` argument specifies the “input file”, or the path to the **Ubuntu image**.
   * The `of` argument specifies the “output file”, or the path to the **USB device**. Make sure that this is the correct device.

   The remaining arguments are optional: `bs=4M` increases the write performance, `conv=fsync` ensures that all data is written when the command finishes, and `status=progress` shows progress information.
6. The `dd` tool reports when the writing is finished:
   `$ ``sudo dd if=Downloads/ubuntu-26.04-desktop-amd64.iso of=/dev/sda bs=4M conv=fsync status=progress`
   ```text
   6337593344 bytes (6.3 GB, 5.9 GiB) copied, 143 s, 44.3 MB/s6345887744 bytes (6.3 GB, 5.9 GiB) copied, 143.302 s, 44.3 MB/s

   1512+1 records in
   1512+1 records out
   6345887744 bytes (6.3 GB, 5.9 GiB) copied, 286.923 s, 22.1 MB/s
   ```
7. Inform your running system of the changes on the USB stick if you want to examine the Ubuntu media:
   `$ ``sudo partprobe /dev/sda`

## On Windows

On Microsoft Windows, you have to install a third-party application for writing images to USB sticks.

<!--
Note: The built-in Disc Image Burner tool can only burn images to optical discs. It can't write to USB sticks.
-->

### Using Rufus

You can create a bootable USB stick using [Rufus](https://rufus.ie/), a free and open source USB stick writing tool.

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

## On macOS

On macOS, you have to install a third-party application for writing images to USB sticks. Alternatively, you can use the built-in `dd` tool on the command line.

The USB stick will work on **PC (Windows) hardware** and older Apple hardware based on **Intel CPUs**.

If you want to run Ubuntu on **Apple Silicon** hardware, such as recent Macs using M1 CPUs or later, refer instead to the [Ubuntu Asahi](https://ubuntuasahi.org/) community project, which isn’t supported by Canonical. The hardware support might be limited and depends on your specific machine. For example, Ubuntu Asahi 25.10 only runs on systems with M1 and M2 CPUs.

You can also install Ubuntu in a virtual machine on top of your current system using [Multipass](https://documentation.ubuntu.com/multipass/).

<!--
Unfortunately, Disk Utility doesn't seem to be able to write arbitrary images, only macOS disk images. Saving for future reference and reevaluation.

### Using the Disk Utility

The Disk Utility is preinstalled on macOS and you can use it to write any image to your USB stick.

1. Launch the \*Disk Utility\* app from {menuselection}\`Applications -> Utilities\` or from the Spotlight search.

1. Insert your USB stick. It appears in the sidebar. Select it there.

    You might need to enable the {menuselection}\`View -> Show All Devices\` option.

    :::{warning}
    Make sure to select the USB stick and \*\*not\*\* your internal macOS disk. Both are listed.
    :::

1. To ensure compatibility with Apple hardware, reformat the USB stick with the GUID partition table:

    Select {guilabel}\`Erase\` from the toolbar.

    Set the format to \*MS-DOS (FAT)\* and the scheme to \*GUID Partition Map\*.

    Check that you've chosen the correct device and click {guilabel}\`Erase\`.

1. Click {guilabel}\`Restore\` ({guilabel}\`↺\`) in the toolbar.

1. Click {guilabel}\`Image…\` and select the Ubuntu image file.

1. Click {guilabel}\`Restore\`.

1. Wait for the writing to finish.

1. After the write process has completed, macOS might inform you that "The disk you inserted was not readable by this computer".

    Select {guilabel}\`Eject\` and remove the USB device. Don't select {guilabel}\`Initialize\`.
-->

### Using balenaEtcher

You can create a bootable USB stick using [balenaEtcher](https://etcher.balena.io/), a free and open source USB stick writing tool.

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

<a id="macos-dd"></a>

### Using the macOS command line

If you feel confident using the macOS command line, you can follow a more manual approach using the `dd` tool.

#### WARNING
The `dd` tool is designed for advanced users. If you specify the wrong options, disk or file names, you might destroy your running system.

<!--
Migrated from a page in the Community Help Wiki:
https://help.ubuntu.com/community/How%20to%20install%20Ubuntu%20on%20MacBook%20using%20USB%20Stick
-->
1. Open the Terminal app.

<!--
This is no longer necessary, and in fact it produces an unusable image:

1. Convert the downloaded ISO image file to the UDRW format:

    \`\`\`{terminal}
    :copy:
    :user:
    :host:
    :dir:
    hdiutil convert Downloads/ubuntu-26.04-desktop-amd64.iso -format UDRW -o ubuntu.dmg
    \`\`\`
-->
1. List the current devices:
   `$ ``diskutil list`
2. Insert your USB stick.
3. List the current devices again. Determine the device name assigned to your USB stick, such as `/dev/disk2`:
   `$ ``diskutil list`
   ```text
     /dev/disk0 (internal, physical):
      […]
     /dev/disk2
      #: TYPE NAME SIZE IDENTIFY
      0: FDisk_partition_scheme *4.0 GB disk2
      1: DOS_FAT_32 USB CLE 4.0 GB disk2s1
   ```
4. Make sure that the USB stick is large enough for the Ubuntu image. If it’s too small, the image writer might silently fail.
5. Unmount the USB stick:
   `$ ``diskutil unmountDisk /dev/disk<N>`

   Replace `<N>` with the disk number from the last command, such as `2`.

   You might see this error: “Unmount of disk<N> failed: at least one volume could not be unmounted”. Open the Disk Utility and unmount the volume (don’t eject).
6. Write the Ubuntu image to the USB stick:
   `$ ``sudo dd if=Downloads/ubuntu-26.04-desktop-amd64.iso of=/dev/rdisk<N> bs=4m`

   #### TIP
   Drag and drop the image file from Finder to Terminal to paste the full path. This way, you prevent potential errors when typing the path.

   Double-check the file paths in this command:
   * The `if` argument specifies the “input file”, or the path to the **Ubuntu image**.
   * The `of` argument specifies the “output file”, or the path to the **USB device**. Make sure that this is the correct device.

     We’re using the `/dev/rdisk<N>` device here rather than `/dev/disk<N>`. This refers to a “raw device” interface to the same disk, which is faster.

   The `bs=4m` option increases the write performance and it’s optional.

   You might encounter these errors:

   `dd: Invalid number '4m'`
   : You’re using GNU `dd`. Use the same command but replace `bs=4m` with `bs=4M`.

   `dd: /dev/disk<N>: Resource busy`
   : Make sure that the disk is not in use. Open the Disk Utility and unmount the volume (don’t eject).
7. Unmount the USB stick:
   `$ ``diskutil eject /dev/disk<N>`
8. Remove the USB stick when the previous command completes.

## On multiple platforms

If the previous applications didn’t work or you have a special use case, we also suggest the following multi-platform image writers.

<a id="image-writers-ventoy"></a>

### Ventoy

[Ventoy](https://www.ventoy.net/) is an open-source tool that you install on your USB. You can then copy image files to the USB storage using your normal file browser. When you boot the system with the USB stick inserted, Ventoy lets you choose among all the image files stored on the USB.

For instructions, see the Ventoy documentation: [Start to use Ventoy](https://www.ventoy.net/en/doc_start.html).

Ventoy is available for Linux and Microsoft Windows.

#### WARNING
Ventoy 1.1.11 (released Apr 2026) has a [known issue](https://github.com/ventoy/Ventoy/issues/3567) that prevents Ubuntu from installing correctly. We recommend using a different Ventoy release or another USB creation tool.

<a id="image-writers-etcher"></a>

### balenaEtcher

[balenaEtcher](https://etcher.balena.io/) is a simple open-source USB stick writing tool. It’s available for Windows, macOS and Linux.

See the documentation at [etcher-docs.balena.io](https://etcher-docs.balena.io/).

<a id="image-writers-wonderiso"></a>

### WonderISO

[WonderISO](https://www.sysgeeker.com/iso-burner.html) is a versatile and easy-to-use tool that can write images to USB. WonderISO is available for Microsoft Windows and macOS as a proprietary (closed-source) application.

For instructions, see the [WonderISO product manual](https://www.sysgeeker.com/online-help/wonderiso.html).

## Next steps

Congratulations! You now have Ubuntu on a USB stick, bootable and ready to go.

To use it you need to insert the stick into your target PC or laptop and reboot the device. It should recognize the installation media automatically during startup but you may need to hold down a specific key (usually `F12`) to bring up the boot menu and choose to boot from USB.

For a full walkthrough of installing Ubuntu, take a look at our [Install Ubuntu Desktop](../tutorial/install-ubuntu-desktop.md#install-ubuntu-desktop) tutorial.

## Finding help

If you get stuck, help is always at hand:

* [Get support](https://ubuntu.com/support/community-support)
* [Join our Discourse forum](https://discourse.ubuntu.com/c/project/desktop/)
* [Join our online chat on Matrix](https://matrix.to/#/#desktop-dev:ubuntu.com)
