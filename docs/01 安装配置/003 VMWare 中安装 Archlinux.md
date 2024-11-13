# VMWare 中安装 Archlinux

> https://www.bilibili.com/video/BV1Pi4y1K7DS

下载地址：

> https://archlinux.org/download/

安装指导：

> https://wiki.archlinux.org/title/Installation_guide

查看 ip 地址：

    ip addr show

重启 sshd:

    systemctl restart sshd

设置 root 密码：

    passwd


源配置:

> https://archlinux.org/mirrorlist/

下载 mirrorlist:

    curl -o /etc/pacman.d/mirrorlist "https://archlinux.org/mirrorlist/?country=CN&protocol=https&ip_version=4"

或者，安装 wget，然后再下载 mirrorlist：

    pacman -S wget

    wget "https://archlinux.org/mirrorlist/?country=CN&protocol=https&ip_version=4" --output-document=/etc/pacman.d/mirrorlist

安装 archlinux:

    archinstall


内核 [^linux] 选项：

- linux: Vanilla Linux kernel and modules, with a few patches applied.
- linux-hardened: A security-focused Linux kernel applying a set of hardening patches to mitigate kernel and userspace exploits. It also enables more upstream kernel hardening features than linux.
- linux-lts: Long-term support (LTS) Linux kernel and modules with configuration options targeting usage in servers.
- linux-zen [^zen-kernel]: Result of a collaborative effort of kernel hackers to provide the best Linux kernel possible for everyday systems.

## openssh

安装 openssh

    pacman -S openssh

设置 sshd 开启启动：

    systemctl enable sshd

known_hosts 问题：

    C:\Users\[username]\.ssh\known_hosts

[^linux]: https://wiki.archlinux.org/title/Kernel
[^zen-kernel]: https://github.com/zen-kernel/zen-kernel
