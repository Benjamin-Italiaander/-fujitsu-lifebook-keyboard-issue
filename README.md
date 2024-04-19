---
title: "Fujitsu lifebook keyboard issue"
author: [Benjamin Italiaander]
date: "2021"
keywords: [Linux, fujitsu, lifebook, keyboard]
---
#fujitsu lifebook keyboard issue

## keyboard was not working Linux fujitsu lifebook
So the after installing Fedora Linux 36 on my fujitsu lifebook u7410 my keyboard was not working anymore. I fixed this by editing grub. 

Just add at the bottom of /etc/default/grub the following line
```sh
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash i8042.reset i8042.nomux i8042.nopnp i8042.noloop"
```

After editing the grub file update the grubfile

```sh
grub2-mkconfig -o "$(readlink -e /etc/grub2.cfg)"
```

reboot after changes, and the keyboard is working again.


