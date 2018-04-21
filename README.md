
# antergos-rescue-beta
antergos :rescue a swiss-knife USB-Live-ISO #beta#
Modified version of Antergos-iso to build the Antergos_:rescue ISO (livecd)

## Dependencies
- antergos-gfxboot for a graphical boot (or isolinux/syslinux)
- arch-install-scripts
- cpio
- dosfstools
- gfxboot
- libisoburn
- mkinitcpio-nfs-utils
- make
- opendesktop-fonts
- patch
- squashfs-tools
- wget
- transifex-client

## Free space

Please, check that you have 5GB (or more) of free harddisk space in your root partition:
`df -h /`

## Instructions:

1. Install dependencies:
```
sudo pacman -S arch-install-scripts cpio dosfstools gfxboot libisoburn mkinitcpio-nfs-utils make patch squashfs-tools wget transifex-client
```
2. Clone this repository like this:
```
git clone https://github.com/killajoe/antergos-rescue-beta.git
```

3. Go to the `config` directory you wish to build from.
- The "official" iso is in the `rescue` folder.
```
cd /home/*user*/antergos-iso/configs/rescue
```
4. Check text configuration file `config` with your favourite text editor.
Here you can enable/disable support for Nvidia driuver, ZFS, package cache, and choose to build cnchi from github.

5. Build the iso:
```
sudo ./build.sh build
```

 **If you want to try to build the iso again, please remember to clean all generated files first:** 
 ```
 sudo ./build.sh clean
 ```

# Notes:
* **build.sh** will create **/work** as build space and **/out** where it saves the ready iso files.
* plymouth (boot animation logo) is removed, boot is verbose.
* Live environment is XFCE, starts without lightdm.
* CNCHI is included and starts and updates itself on login.
