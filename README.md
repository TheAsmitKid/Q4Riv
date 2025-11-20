# q4Riv
A minimal, sleek Plymouth theme for **Q4OS**. q4Riv elegantly conceals the boot process while presenting a smooth, luminous animation for the system’s first glance.

---

## Building the `.deb` Package

If you want to build the `.deb` package from the source theme files:

1. Make sure you have `dpkg-deb` installed:

```bash
sudo apt install dpkg-dev
```

2. Navigate to the folder containing the theme directory (`usr/share/plymouth/themes/q4sz`) and `DEBIAN` control folder.

3. Run the build command:

```bash
dpkg-buildpackage -b -uc -us -tc
```
---

## Installation

1. Install the `.deb` package:

```bash
sudo apt install ./setuzuna-q4sz-plymouth-1.0-anylinux.deb
```

2. You may need to tweak **GRUB** settings. Edit:

```bash
sudo nano /etc/default/grub
```

* Comment out or modify the existing line:

```text
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash loglevel=3 systemd.log_color=1 systemd.show_status=1"
```

* Replace with:

```text
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
```

> **Note:** On some systems, you might also need to add `i915.modeset=1` at the end of `GRUB_CMDLINE_LINUX_DEFAULT` to get Plymouth to work. Test on your own hardware — this is **not a q4Riv issue**.

3. Set q4Riv as the default theme and update:

```bash
sudo plymouth-set-default-theme -R q4Riv
```

---

## Feedback

Your feedback is appreciated! :p

Please share your thoughts, issues, or improvement suggestions on the [Q4OS Forum – q4Riv Discussion](https://q4os.org/forum/viewtopic.php?id=5793).
