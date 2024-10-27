# 006 Gnome 可选配置

- 配置代理
- Gnome 默认 200% 缩放 [^hidpi] [^dconf]
- terminal 字体
- grub 开机延迟 [^grub]
- firefox 浏览器
- extensions [^extensions]
- 声音卡顿
- 中文输入法
- gnome-software

## 配置代理

```sh
cat << EOF > ~/.http_proxy
export http_proxy=http://192.168.111.1:10083
export https_proxy=http://192.168.111.1:10083
EOF
```

启动代理：

    source ~/.http_proxy

## Gnome 默认 200% 缩放

安装 dconf-editor:

    sudo pacman -S dconf-editor

然后修改变量：

    org.gnome.desktop.interface scaling-factor=2

> 目前 scaling-factor 只能设置为整数

----

或者 [^scale]，创建文件 `/usr/share/glib-2.0/schemas/93_hidpi.gschema.override`：

写入：

```
[org.gnome.desktop.interface]
scaling-factor=2
```

或者直接使用命令行：

```sh
cat << EOF > /usr/share/glib-2.0/schemas/93_hidpi.gschema.override
[org.gnome.desktop.interface]
scaling-factor=2
EOF
```

重新编译：

    sudo glib-compile-schemas /usr/share/glib-2.0/schemas

## terminal 字体

安装字体：

    sudo pacman -S ttf-fira-code

然后修改字体设置 firacode，字号 18。

然后关闭所有 terminal，重新打开 terminal。

## grub 开机延迟

编辑文件 `/etc/default/grub` 修改 `GRUB_TIMEOUT=0`，可以直接启动；

    sudo gnome-text-editor /etc/default/grub

当然 `gnome-text-editor` 可以替换为任意编辑器，不过图形界面的方式应该更容易理解。

然后执行命令，重新生成 grub 配置文件：

    sudo grub-mkconfig -o /boot/grub/grub.cfg

然后重启即可：

    sudo reboot

## firefox

安装火狐浏览器

    sudo pacman -S firefox

卸载 Web(Gnome 默认浏览器)

    sudo pacman -R epiphany

安装文泉驿字体：

    sudo pacman -S wqy-zenhei

配置代理；

## Extensions


1. 进入网页： https://extensions.gnome.org/
2. 安装浏览器扩展；
3. 安装 gnome-browser-connector

        sudo pacman -S gnome-browser-connector

### 默认扩展

- Extension List
- Date Menu Formatter
- Blur my Shell
- Dash to Dock
- Dash to Panel
- App Icons Taskbar
- Coverflow Alt-Tab
- Clipboard History
- Desktop icons NG
- Input Method Panel
- Lunar Calendar
    - cpio [^cpio]

## 声音卡顿

根据 [^pipewire] 解决播放声音卡顿的问题：

安装一些包，可能出现 pipewire-jack 与 jack2 冲突的情况，继续安装：

    sudo pacman -S pipewire pipewire-audio pipewire-pulse pipewire-alsa pipewire-jack wireplumber rtkit

拷贝配置文件：

    sudo cp /usr/share/pipewire/pipewire.conf /etc/pipewire/

修改配置文件 /etc/pipewire/pipewire.conf，去掉前面的注释 #

    sudo gnome-text-editor /etc/pipewire/pipewire.conf

```conf
default.clock.rate          = 48000
default.clock.allowed-rates = [ 48000 ]
default.clock.quantum       = 1024
default.clock.min-quantum   = 32
default.clock.max-quantum   = 2048
default.clock.quantum-limit = 8192
```

然后重启服务

    systemctl --user restart wireplumber pipewire pipewire-pulse

----

如果还没解决卡顿的问题，根据 [^crackling]：

创建目录

    mkdir -p ~/.config/wireplumber/wireplumber.conf.d/
    cd ~/.config/wireplumber/wireplumber.conf.d

拷贝配置文件到当前目录：

    cp /usr/share/wireplumber/wireplumber.conf.d/alsa-vm.conf .

然后编辑当前目录的文件 `alsa-vm.conf`

    api.alsa.period-size   = 1024
    api.alsa.headroom      = 8192

然后重启服务

    systemctl --user restart wireplumber pipewire pipewire-pulse


[^crackling]: https://bbs.archlinux.org/viewtopic.php?id=280654
[^pipewire]: https://gitlab.freedesktop.org/pipewire/pipewire/-/wikis/Troubleshooting#stuttering-audio-in-virtual-machine

## 中文输入法

根据 [^input]，设置支持拼音输入法。

[^input]: https://wiki.archlinux.org/title/Input_method

安装 fcitx5：

    sudo pacman -S fcitx5 fcitx5-chinese-addons fcitx5-configtool fcitx5-qt fcitx5-gtk

安装 Input Method Panel 扩展，另外可配置快捷键。

## gnome-software

替换国内源 [^flatpak]：

    sudo flatpak remote-modify flathub --url=https://mirror.sjtu.edu.cn/flathub

## 其他

- 全局快捷键：
    - hide all normal windows
    - super + space
    - gnome-system-monitor
- VMWare：
    - 全屏时显示工具栏边缘
    - 禁用侧通道缓解

## References

[^grub]: https://wiki.archlinux.org/title/GRUB
[^hidpi]: https://wiki.archlinux.org/title/HiDPI
[^dconf]: https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/8/html/using_the_desktop_environment_in_rhel_8/configuring-gnome-at-low-level_using-the-desktop-environment-in-rhel-8#managing-system-settings_configuring-gnome-at-low-level
[^extensions]: https://extensions.gnome.org/
[^gnome-browser-connector]:https://discourse.gnome.org/t/error-no-such-native-application-org-gnome-chrome-gnome-shell/15199
[^cpio]: https://www.gnu.org/software/cpio/
[^scale]: https://askubuntu.com/questions/906797/scaling-gnome-login-screen-on-hidpi-display
[^flatpak]: https://www.jianshu.com/p/764af257ab25
