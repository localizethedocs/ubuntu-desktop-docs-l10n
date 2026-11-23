Topics: [Updates](../_tags/updates.md) [Support](../_tags/support.md)

<a id="switch-between-an-lts-and-interim-release"></a>

# Switch between an LTS and interim release

Ubuntu releases come in two types with different life cycles: Long Term Support (LTS) releases and interim releases. You can reconfigure your system from one type to another.

## The difference between release types

LTS releases such as Ubuntu 26.04 LTS are recommended for users looking for a stable environment. LTS releases receive five years of support and security updates.

Interim releases are supported for nine months. They give you a chance to preview new features and updates ahead of the next LTS release.

To learn more about the life cycle of Ubuntu releases, see [The Ubuntu lifecycle and release cadence](https://ubuntu.com/about/release-cycle).

#### NOTE
To extend the support lifetime of your Ubuntu LTS system, consider enabling [Ubuntu Pro](https://ubuntu.com/pro) in the Security Center. You also receive security updates to community-maintained packages and get access to certain enterprise features.

Ubuntu Pro is free for personal use on up to 5 machines.

## Determine your current release

Before you start upgrading, you need to know which version of Ubuntu you’re currently using and whether it’s an LTS or interim release.

### Graphical interface

On Ubuntu Desktop, open the Settings application. Navigate to System ‣ About. Your Ubuntu version is listed in the Operating System field. For example, it might say “Ubuntu 26.04 LTS”.

On earlier Ubuntu versions, the information was located on the Details tab.

### Command line

`$ ``lsb_release --description`
```text
Description:	Ubuntu 26.04 LTS
```

<a id="switch-to-interim"></a>

## Switch to interim

If you’re currently using an LTS release such as Ubuntu 26.04 LTS, you can configure your system to follow interim releases instead.

### Graphical interface

1. Install the Software & Updates application, which is available from the `software-properties-gtk` Deb package.
2. Open the Software & Updates application.
3. Go to the Updates tab.
4. In the menu labeled Notify me of a new Ubuntu version, select For any new version, which includes interim releases.
5. Close the application.

### Command line

1. Edit the `/etc/update-manager/release-upgrades` configuration file.
2. Set the `Prompt=normal` option.

An upgrade to an interim release becomes available now, unless you’re using an LTS release that’s just come out and there’s no recent interim release yet. Follow the instructions in the [Upgrade Ubuntu Desktop](upgrade-ubuntu-desktop.md#upgrade-ubuntu-desktop) guide. You might have to upgrade several times until you reach the latest interim release.

<a id="switch-to-lts"></a>

## Switch to LTS

If you’re using an interim release of Ubuntu, you can reconfigure your system to be an LTS release. However, you can only do this at certain points in time:

* When you’re using an interim release that directly precedes an LTS release, such as on Ubuntu 25.10 before Ubuntu 26.04 LTS.
* When you upgrade to an Ubuntu release that’s an LTS release, such as after your upgrade to Ubuntu 26.04 LTS.

### Graphical interface

1. Install the Software & Updates application, which is available from the `software-properties-gtk` Deb package.
2. Open the Software & Updates application.
3. Go to the Updates tab.
4. In the menu labeled Notify me of a new Ubuntu version, select For long-term support versions.
5. Close the application.

### Command line

1. Edit the `/etc/update-manager/release-upgrades` configuration file.
2. Set the `Prompt=lts` option.

Your installation now stops offering upgrades to new interim releases, and instead, it stabilizes on the current or upcoming LTS release. When a new LTS release becomes available, follow the instructions in the [Upgrade Ubuntu Desktop](upgrade-ubuntu-desktop.md#upgrade-ubuntu-desktop) guide to upgrade your system.
