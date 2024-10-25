# 005 配置 VMWare 工具

根据 [^vmware] 来配置 VMWare，使得虚拟机能够自适应分辨率。与主机之间可以进行复制粘贴，拖拽等操作。

- open-vm-tools [^vm-tools]
- gtkmm3 [^gtkmm3]

安装工具：

    sudo pacman -S open-vm-tools
    sudo pacman -S gtkmm3

开机启动：

    sudo systemctl enable vmtoolsd
    sudo systemctl enable vmware-vmblock-fuse

其中 vmtoolsd [^vmtoolsd] 用于设置客户机信息元数据，用户数据和供应商数据等。

## References

[^vmware]: https://wiki.archlinux.org/title/VMware/Install_Arch_Linux_as_a_guest
[^vm-tools]: https://github.com/vmware/open-vm-tools/
[^gtkmm3]: https://www.gtkmm.org/en/index.html
[^vmtoolsd]: https://vmware.github.io/photon/assets/files/html/3.0/photon_troubleshoot/Troubleshooting-vmtoolsd.html
