Topics: [Installation](../_tags/installation.md) [Security](../_tags/security.md)

<a id="configure-hardware-backed-disk-encryption"></a>

# Configure hardware-backed disk encryption

On an Ubuntu installation where the hardware-backed disk encryption (TPM/FDE) is enabled, you can configure certain security options. You can also recover access to your disk in certain scenarios.

<a id="tpm-fde-set-passphrase"></a>

## Set a disk encryption PIN or passphrase

For an additional layer of security, you can add an encryption PIN or passphrase. You enter them every time your computer starts up to unlock the disk. A PIN or passphrase is also required on systems that don’t provide a hardware root of trust, though you can disable it afterward.

To learn when you might want to enable the PIN or passphrase, see [Encryption PIN and passphrase](../explanation/hardware-backed-disk-encryption.md#tpm-fde-encryption-passphrase).

### Graphical interface

1. Open the Security Center app.
2. Go to the Disk Encryption tab.
3. Click Add PIN or Add passphrase.
4. Enter a numeric PIN or an alphanumeric passphrase and confirm.

### Command line

1. Make sure that the `snap-tpmctl` tool is installed:
   `$ ``sudo snap install snap-tpmctl`
2. Add a PIN or passphrase:
   * PIN:
     `$ ``sudo snap-tpmctl add-pin`
   * Passphrase:
     `$ ``sudo snap-tpmctl add-passphrase`

Later, you can change your PIN or passphrase using the `replace-pin` and `replace-passphrase` subcommands.

The next time you reboot, your system asks for your PIN or passphrase. Alternatively, you can also enter the disk recovery key if you forget your PIN or passphrase.

<a id="tpm-fde-get-a-new-recovery-key"></a>

## Get a new recovery key

Ubuntu Desktop shows you your disk recovery key right after installation. If you lose your recovery key, replace it as soon as possible. Otherwise, you risk losing access to your data. You can’t retrieve the existing recovery key but you can get a new one.

To get the recovery key, you must be logged into your Ubuntu user account.

#### IMPORTANT
If you can’t log in, you have no way to get a new recovery key. In that case, follow [What to do if you don’t have a recovery key](#tpm-fde-no-recovery-key).

You need to be an administrator on your system to replace the recovery key.

### Graphical interface

1. Go to the Security Center ‣ Disk Encryption.
2. Select Replace recovery key….
3. The Security Center displays your new recovery key. The previous recovery key stops working as soon as you select Replace.
4. Store your new recovery key somewhere safe, such as in a password manager.

### Command line

1. Make sure that the `snap-tpmctl` tool is installed:
   `$ ``sudo snap install snap-tpmctl`
2. List the recovery keys on your system:
   `$ ``snap-tpmctl list-recovery-keys`
   ```text
   Recovery Keys:
   * default-recovery
   ```

   Usually, only one recovery key is active, and it’s called `default-recovery`. In an enterprise environment or a custom setup, you might find a secondary recovery key.
3. Replace the recovery key:
   `$ ``snap-tpmctl regenerate-recovery-key default-recovery`

   Replace `default-recovery` with the name of your recovery key.
4. The command displays your new recovery key.

   Store it somewhere safe, such as in a password manager.

## Manage recovery keys for an organization

You can centrally manage the recovery keys for multiple systems encrypted with TPM/FDE. This is useful if you’re the system administrator at an organization where you need centralized control over all encrypted systems (“escrow”). In this setup, TPM/FDE adds a secondary recovery key on each system. This secondary key is subject to central management.

#### WARNING
If the local user of the managed system has root privileges, they can modify both recovery keys on their system using the `snap-tpmctl` tool. The Security Center only gives access to the primary, local recovery key.

Recovery key management is integrated into the **Landscape** systems administration tool. For details, refer to the [Landscape documentation](https://documentation.ubuntu.com/landscape/).

Alternatively, you can build a custom central management solution based on the interfaces provided by the `snap-tpmctl` tool:

### Relevant commands

* List all recovery keys:
  `$ ``snap-tpmctl list-recovery-keys`
* Add a secondary recovery key:
  `$ ``snap-tpmctl create-recovery-key custom-key`

  Replace `custom-key` with a name for your recovery key.
* Replace a recovery key:
  `$ ``snap-tpmctl regenerate-recovery-key my-key-name`

  Replace `my-key-name` with the name of your selected recovery key.

For other options, refer to the `snap-tpmctl help` command.

<a id="tpm-fde-no-recovery-key"></a>

## What to do if you don’t have a recovery key

Your computer might be asking for a recovery key but you don’t have one.

If you’re logged into your Ubuntu user account, you can retrieve or reset your recovery key. See [Get a new recovery key](#tpm-fde-get-a-new-recovery-key).

If your computer is asking for your recovery key during startup, try undoing any [recent changes](../explanation/hardware-backed-disk-encryption.md#tpm-fde-when-ubuntu-asks-for-your-recovery-key) to your computer. For example:

1. Remove any new hardware components.
2. Undo any changes to boot settings.
3. Reboot your computer.
4. Try to log in again.

You can also check if the recovery key was automatically stored in the cloud:

* If your system is managed via Landscape, contact your Landscape administrator for your recovery key.
* Recovery keys for the Windows BitLocker encryption may be stored on your Microsoft Account or your organization account. See [Find your BitLocker recovery key](https://support.microsoft.com/en-us/windows/find-your-bitlocker-recovery-key-6b71ad27-0b89-ea08-f143-056f5ab347d6) in the Microsoft Windows documentation.

## Additional resources

- [Recover data from hardware-backed disk encryption](recover-data-from-hardware-backed-disk-encryption.md#recover-data-from-hardware-backed-disk-encryption)
