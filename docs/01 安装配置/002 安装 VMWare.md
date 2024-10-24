# 安装 VMWare

VMWare [^vmware] 是一种常见的虚拟机软件，常见的虚拟机软件还有 VirtualBox，qemu，bochs 等。

VMware Workstation 现在对个人用户免费 [^free]。

软件下载地址：

> https://softwareupdate.vmware.com/cds/vmw-desktop/

Windows Hypervisor Platform [^whp]，允许不同的 Hypervisor（虚拟机底层）同时运行在 Windows 之上。比如 VMware ESXi，Microsoft Hyper-V。

Vmware Enhanced Keyboard Driver [^vmkeybaord] 增强型虚拟键盘功能可更好地处理国际键盘和带有额外按键的键盘。此功能只能在 Windows 主机系统中使用。由于增强型虚拟键盘功能可尽可能快地处理原始键盘输入，所以能够绕过 Windows 按键处理和任何尚未出现在较低层的恶意软件，从而提高安全性。使用增强型虚拟键盘功能时，如果按下 Ctrl+Alt+Delete，只有客户机操作系统会做出反应。

SCSI 控制器的解释 [^vscsi]：

- BusLogic：是 VMWare 最初的虚拟化实现，有很多限制；
- LSI Logic (Parallel)：另一个 VMWare 最初的虚拟化实现，大多数操作系统都支持队列深度为32的驱动程序，所以成为了推荐的选择；
- LSI Logic SAS：这是 LSI Logic 的改进版，以支持新的面向未来的标准，在 Windows 2008 支持 MSCS(Microsoft Cluster Service 微软集群服务) 之后比较流行；
- VMWare ParaVirtual(PVSCSI)：被设计为以最小的处理成本支持非常高的吞吐量，因此是最高效的驱动程序。但是如果虚拟机没有很高的吞吐量，可能会有问题，据说问题已经被解决了；

磁盘类型的解释：

- IDE：Integrated Drive Electronics 电子集成驱动器，也叫做 ATA(Advanced Technology Attachment)；
- SATA：Serial ATA，串行 ATA；
- SCSI：Small Computer System Interface（小型计算机系统接口）
- NVMe：NonVolatile Memory express，快速非易失存储器，现在(2024) 常见的固态硬盘都是这种协议；

## References

[^vmware]: https://en.wikipedia.org/wiki/VMware
[^free]: https://blogs.vmware.com/workstation/2024/05/vmware-workstation-pro-now-available-free-for-personal-use.html
[^whp]: https://learn.microsoft.com/en-us/virtualization/api/#windows-hypervisor-platform
[^vmkeybaord]: https://docs.vmware.com/cn/VMware-Workstation-Pro/15.0/com.vmware.ws.using.doc/GUID-D7E859A1-AD77-41A0-9B20-8B15744056E1.html
[^vscsi]: https://blogs.vmware.com/vsphere/2014/02/vscsi-controller-choose-performance.html
