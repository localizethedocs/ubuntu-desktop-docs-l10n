<!--
Previously linked: https://help.ubuntu.com/community/Repositories/Ubuntu, https://help.ubuntu.com/community/Repositories/CommandLine
-->

Topics: [Software](../../_tags/software.md)

<a id="add-a-software-repository"></a>

# Add a software repository

In addition to official Ubuntu sources, software is also available from third-party, community-maintained sources. If you want to install software from a third-party software repository, you must add it to Ubuntu’s list of available repositories.

#### WARNING
Only add software repositories from **sources that you trust**.

Third-party software repositories are **not checked for security or reliability** by Ubuntu members, and may contain software which is harmful to your computer. By enabling the repository, you’re giving access to your system to the repository owners.

If possible, install [snap packages](../../explanation/snap-and-deb-packages.md#snap-and-deb-packages) instead. These are confined for security.

## Add a PPA

Personal Package Archives (PPAs) are software repositories designed for Ubuntu users and are easier to install than other third-party repositories. PPAs are often used to distribute pre-release software so that it can be tested.

#### NOTE
For other use cases, we recommend that you install confined [snap packages](../../explanation/snap-and-deb-packages.md#snap-and-deb-packages) instead.

### Graphical interface

1. On the PPA’s overview page, look for the Adding this PPA to your system heading. Copy the PPA’s location, which should look similar to: `ppa:mozillateam/firefox-next`.
2. Install the `software-properties-gtk` package, which provides the Software & Updates application.
3. Open the Software & Updates application.
4. Switch to the Other Software tab.
5. Click Add and enter the PPA’s location that you copied earlier.
6. Click Add Source. Enter your password.
7. Close the Software & Updates window. App Center will then check your software sources for new software, including the PPA that you’ve just added.

### Command line

1. On the PPA’s overview page, look for the Adding this PPA to your system heading. Copy the PPA’s location, which should look similar to: `ppa:mozillateam/firefox-next`.
2. Enable the PPA using the `add-apt-repository` tool:
    <!--
    Should be installed by default. On older or minimal Ubuntu releases, you may have to install software-properties-common and/or python-software-properties first:
    sudo apt-get install python-software-properties
    -->
   `$ ``sudo add-apt-repository ppa:<user>/<repo-name>`

   Replace `ppa:<user>/<repo-name>` with the PPA’s location that you copied earlier.
3. Check your software sources for new software, including the PPA that you’ve just added:
   `$ ``sudo apt update`

You can now install software from the PPA.

## Add a third-party repository other than PPA

You can find many software repositories for Ubuntu outside of the PPA platform. These are managed using standard Debian tools, and they require more manual steps.

#### NOTE
Before you enable a third-party repository, we recommend that you check if the software is available as a confined [snap packages](../../explanation/snap-and-deb-packages.md#snap-and-deb-packages) instead.

1. Install the `software-properties-gtk` package, which provides the Software & Updates application.
2. Open the Software & Updates application.
3. Switch to the Other Software tab.
4. Click Add and enter the APT line for the repository. This should be available from the website of the repository, and should look similar to:
   ```text
   deb http://archive.ubuntu.com/ubuntu/ questing main
   ```
5. Click Add Source. Enter your password.
6. Close the Software & Updates window. App Center will then check your software sources for new software.
7. Check if the repository provides a signing key (GPG key) to be able to verify downloaded packages. Follow possible instructions on how to download and install the signing key.
