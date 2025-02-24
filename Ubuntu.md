# Ubuntu setup playbook
This is just my personal preference to get started, your requirements may differ so follow at your own risk.

**Hypervisor:** VirtualBox

**Install type:** minimal Ubuntu desktop install with additional drivers


## VirtualBox Settings

Under the VM settings: `system > assign 8Gb RAM and 4 CPU cores`, `display > set video memory to 128mb` and `audio > set audio controller to "Intel HD Audio"`

If using a high resolution monitor, consider setting monitor scaling to `150%` in VirtualBox settings. The text will be slightly blurrier but VM performance I found to be better.


## Update all packages and snaps

```bash
sudo apt update && sudo apt full-upgrade
```
```bash
sudo snap refresh
```


## Enable firewall

```bash
sudo ufw enable
```


## Installing VirtualBox Guest Additions

```bash
sudo apt install virtualbox-guest-additions-iso
```
Navigate to the location `/usr/share/virtualbox/VBoxGuestAdditions.iso` and right click "mount" the image. Then run:

```bash
sudo ./VBoxLinuxAdditions.run
```
Once installed unmount the disk again by right clicking and selecting "unmount". Reboot the machine for the update to take effect.


## Enable dark mode and disable screen timeout 

```bash
gsettings set org.gnome.desktop.interface gtk-theme 'Yaru-dark'
```
```bash
gsettings set org.gnome.desktop.session idle-delay 0
```


## Install favourite packages and snaps

```bash
sudo apt install git flameshot vim cherrytree ffmpeg ghostwriter
```
Update the favourite pinned apps:
```bash
gsettings set org.gnome.shell favorite-apps "['firefox_firefox.desktop', 'org.gnome.Nautilus.desktop', 'cherrytree.desktop', 'org.flameshot.Flameshot.desktop']"
```


## Set a desktop wallpaper (optional)

User dwt1 on gitlab has a collection of [wallpapers](https://gitlab.com/dwt1/wallpapers) that may be of interest.
