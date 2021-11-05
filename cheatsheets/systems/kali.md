# Kali Linux 2021.3 with VirtualBox

Kali Linux is a distribution for professional penetration testers.  
The download can be found here: <https://www.kali.org/get-kali/>

## Quotes

> If you need to ask, then Kali Linux is not the right distribution for you.

&mdash; [Gilles on UnixExchange](https://unix.meta.stackexchange.com/a/5361/224262)

> The more quieter you become, the more able you are to hear.

&mdash; [Rumi](https://www.goodreads.com/quotes/6822193-the-quieter-you-become-the-more-you-are-able-to)

## Shared Folder

How to add a shared folder in VirtualBox running `Kali Linux 2021.3` as guest and `Windows 10` as host:

1. In Windows, create a folder called `shared`

1. In VirtualBox, go to `Devices > Shared Folders > Shared Folder Settings`:

   ![vb-settings][1]

   Add a new share with the checkboxes `Auto-mount` and `Make permanent` enabled:

   ![vb-settings][2]

1. In Kali, allow access to the shared folder and then reboot the system for the changes to take effect, via:

   ```sh
   sudo adduser kali vboxsf && reboot
   ```

   (Without the `vboxsf` user group, a `permission denied` error will be shown when trying to access the shared folder)

1. In Kali, add a symbolic link to the desktop for the shared folder, via:

   ```sh
   ln -s /media/sf_shared /home/kali/Desktop
   ```

[1]: ./imgs/kali_1.png
[2]: ./imgs/kali_2.png
