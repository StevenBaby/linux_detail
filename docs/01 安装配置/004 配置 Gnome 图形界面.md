# 配置 Gnome 图形界面

- VMWare；
    - 界面缩放
    - 快照
- Gnome 图形界面；

## VMWare 快照

快照[^snapshots]包括虚拟机内存的内容、虚拟机设置以及所有虚拟磁盘的状态。还原到快照时，将虚拟机的内存、设置和虚拟磁盘恢复到快照时的状态。

## Gnome

安装 gnome [^gnome_wiki]:

    sudo pacman -S gnome

开机启动：

    sudo systemctl enable gdm

- [x] gdm [^gdm]
- [x] gnome-tweaks
- [x] gnome-terminal
- [x] gnome-console
- [x] nautilus：文件管理器
- [x] keyboard shortcut
    - [x] gnome-terminal
    - [x] nautilus

## References

[^snapshots]: https://docs.vmware.com/en/VMware-Workstation-Pro/17/com.vmware.ws.using.doc/GUID-7CF19099-D200-4972-B6A2-48DCDE1F3B15.html
[^gnome_wiki]:https://wiki.archlinux.org/title/GNOME
[^gdm]: https://wiki.archlinux.org/title/GDM
