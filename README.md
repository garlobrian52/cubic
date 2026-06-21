# Cubic

<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/cubic_512x512.png" height="128"/>

**[Cubic](https://github.com/PJ-Singh-001/Cubic) ([Custom Ubuntu ISO Creator](https://github.com/PJ-Singh-001/Cubic)) is a GUI wizard to create a customized Live ISO image for Ubuntu and Debian based distributions.**

Cubic permits effortless navigation through the ISO customization steps and features an integrated virtual command line environment to customize the Linux file system. You can create new customization projects or modify existing projects. Important parameters are dynamically populated with intelligent defaults to simplify the customization process.

Cubic runs on distributions based on:
- Ubuntu 18.04.5 Bionic Beaver and above
- Debian 11 Bullseye and above

Cubic can be used to customize the Live ISOs for:
- All versions of Ubuntu from 14.04 Trusty Tahr and above
- Most distributions based on Ubuntu
- Many versions of Debian (tested on Debian 11 Bullseye and above)
- Many distributions based on Debian

## Fund Cubic
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/donate_to_cubic_with_paypal.png" alt="Donate to Cubic with Paypal" height="64"/>](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=5WJL2ZE3AWGQQ&currency_code=USD&source=url)    [<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/donate_to_cubic_with_venmo_334x156.png" alt="Donate to Cubic with Paypal" height="64"/>](https://venmo.com/code?user_id=2990984925282304946&created=1639368328.1588511&printed=1)

## Install Cubic

Cubic runs on distributions based on Ubuntu 18.04.5 Bionic and above.

    sudo apt-add-repository universe
    sudo apt-add-repository ppa:cubic-wizard/release
    sudo apt update
    sudo apt install --no-install-recommends cubic

<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/ubuntu-logo.png" width="18"/> [Detailed Ubuntu installation instructions](https://github.com/PJ-Singh-001/Cubic/wiki/Install-Cubic#-ubuntu-and-derivatives)

<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/debian-logo.png" width="18"/> [Detailed Debian installation instructions](https://github.com/PJ-Singh-001/Cubic/wiki/Install-Cubic#-debian-and-derivatives)

## Screenshots

[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Start%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Start-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Project%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Project-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Extract%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Extract-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Terminal%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Terminal-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Prepare%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Prepare-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Packages%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Packages-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Options%20Page%20Kernel%20Tab.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Options-Page#Kernel-Tab)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Options%20Page%20Preseed%20Tab.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Options-Page#Preseed-Tab)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Options%20Page%20Boot%20Tab%201.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Options-Page#Boot-Tab)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Compression%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Compression-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Generate%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Generate-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Finish%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Finish-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Finish%20Test%20Page.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Finish-Test-Page)
[<img src="https://github.com/PJ-Singh-001/Cubic/blob/release/screenshots/Cubic%20Emulator.png" width="256"/>](https://github.com/PJ-Singh-001/Cubic/wiki/Emulator)

## Repository Notes

This `release` branch is a documentation and asset repository for Cubic. It tracks:

- `README.md` and GitHub issue templates.
- `screenshots/*.png` images used by this README and the project wiki.
- `qemu-system-x86_0.0_all.deb`, a small dummy Debian package.

The Cubic application source is not built from this branch. Cubic is installed from the Launchpad PPA shown above, so there are no local build, lint, test, or package-manager commands to run from this checkout.

### Dummy QEMU package

`qemu-system-x86_0.0_all.deb` satisfies Cubic's `qemu-system-x86` dependency for installations that do not need the full QEMU package. It declares package `qemu-system-x86` at version `0.0` and contains only files under `/usr/share/doc/qemu-system-x86/`.

Inspect the package without installing it:

```
dpkg-deb -I qemu-system-x86_0.0_all.deb
dpkg-deb -c qemu-system-x86_0.0_all.deb
```

Verify the installed package state after installing it:

```
sudo dpkg -i qemu-system-x86_0.0_all.deb
dpkg-query -W -f='${Package} ${Version} ${Status}\n' qemu-system-x86
```

Expected output:

```
qemu-system-x86 0.0 install ok installed
```

### Documentation workflow

Keep changes to this branch focused on documentation, issue templates, screenshots, and the dummy Debian package. When documenting Cubic behavior, verify it against the installed Cubic package or the project wiki before changing this README, because this checkout does not contain the application code.
