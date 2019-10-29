# ozm
https://www.hackintosh-forum.de/forum/thread/43396-ozmosis-mit-macos-catalina-10-15-oz167x-xmax-extended/

MacOS Catalina的新核心补丁：

对于带有Ozmosis的MacOS Catalina的引导，原则上只要使用Oz-Xmax，就只需要更新核心补丁：
由于macos版本传输的更改，几乎所有ueftw驱动程序都需要更新macos catalina:
ueftw macos catalina commit [url：https://github.com/cecekpawon/UEFTW/commit/550d9b45ebd6a9b899baff3735d203f00ea85886]

与catalina兼容的kernextpatcher作为efi驱动程序：kernextpatcher.efi（源代码：https://github.com/cecekpawon/UEFTW/commit/550d9b45ebd6a9b899baff3735d203f00ea85886）


此外，kernextpatcher.plist 必须通过macos catalina的条目进行扩展。
（还安装了竞争条件修补程序：kxidumap）
这是新的MacOS 10.15 kernextpatcher.plist（向后兼容）：
kernextpatcher.plist [https://www.hackintosh-forum.de/attachment/107536-kernextpatcher-plist-zip/]

因此，对于catalina，可以使用rom中的以下kernel extpatcher ffs（ueftw update&new patch）：
kernextpatcher.ffs [https://www.hackintosh-forum.de/attachment/107537-kernextpatcher-ffs-zip/]

这里提供的xmax版本仍然可以在catalina下使用：macos mojave ozmosis beta oz167x-xmax
此外，现在还有一个修订版xmax，发布日期为2019-07-01，具有以下更改/功能：

1.
补丁 4:

与所有xmax版本一样：禁用内部kext注入-->为kext injection提供kernextpatcher
补丁 4 [url:https://gist.github.com/cecekpawon/fe55262ff5ad60a2fdd9a21709a2b917#patch-4]

Load external patches list (eg: from Clover, with UEFTW-KernextPatcher), by disabling internal Kext inject patches.
[url:https://sourceforge.net/p/cloverefiboot/code/4969/tree/rEFIt_UEFI/Platform/kext_inject.c#l593]
[url:https://github.com/cecekpawon/UEFTW/wiki/Releases-Driver-KernextPatcher]

C: (4.1) Disable internal Kext inject patch
F: 488BC4488958084889681048897018488978204154415641574883EC30803DE795000000
R: C390C4488958084889681048897018488978204154415641574883EC30803DE795000000

C: (4.2) Disable internal Kext inject patch
F: 488BC44889580848896810488970184889782041564883EC30803D0697000000
R: C390C44889580848896810488970184889782041564883EC30803D0697000000


2. 
补丁 2:
HD4600的修复：过时的内部设备属性模块已被禁用。ozmosis注入，因此不再可以同时使用任何设备props和igpu以及专用gpu。
补丁 2 [url:https://gist.github.com/cecekpawon/fe55262ff5ad60a2fdd9a21709a2b917#patch-2]

应使用ACPI修补程序（DSM）或 devprop-ueft [url:https://github.com/cecekpawon/UEFTW/wiki/Releases-Driver-DevProp] 驱动程序（devprop guide [url:https://github.com/cecekpawon/UEFTW/wiki/Releases-Driver-DevProp]）替换内部设备属性模块。


以下devprop.plist 和devprop.ffs 可以用作HD4600的模板，但应进行调整：
devprop.plist.zip [url:https://www.hackintosh-forum.de/attachment/107539-devprop-plist-zip/]
DevProp.ffs.zip [url:https://www.hackintosh-forum.de/attachment/107558-devprop-zip/]

devprop的使用还需要
DevicePathPropertyDatabase.zip  [url:https://www.hackintosh-forum.de/attachment/107553-devicepathpropertydatabase-zip/]

Patch (2)

Load external Devprop driver (Apple-DevicePathPropertyDatabase driver), by disabling internal Devprop module.
Load external properties list (with UEFTW-DevProp), by disabling internal injected properties.
[url:https://github.com/cecekpawon/UEFTW/wiki/Releases-Driver-DevProp]
C: (2.1) Disable internal Devprop
F: 405553574157488D6C24C1
R: C390909090909090909090

C: (2.2) Disable internal Devprop
F: E861430200E8C8240000
R: 9090909090E8C8240000

3. 
补丁 1:

对过时的ozmosis aptio fix的修复：过时的内部aptiofix已被停用，从而创造了使用替代aptio修复驱动程序的可能性。这个ozmosis版本没有包含aptiofix就不能工作！
补丁 1 [url:https://gist.github.com/cecekpawon/fe55262ff5ad60a2fdd9a21709a2b917#patch-1]

应该测试已知的aptiofix驱动程序（不同的硬件需要不同的驱动程序）。

建议使用AptiomeMoryFix或Osxaptiofix2DRV。

Aptiofix变异体（EFI和FFS）（01.07级）：
AptiomeMoryfix r26.zip（来源:[url:https://github.com/acidanthera/AptioFixPkg]）
osxaptiofix2drv 01.07.2019.zip（来源:[url:https://sourceforge.net/p/cloverefiboot/code/HEAD/tree/OsxAptioFixDrv/]）
osxaptiofixdrv 01.07.2019.zip（来源:[url:https://sourceforge.net/p/cloverefiboot/code/HEAD/tree/OsxAptioFixDrv/]）

Patch (1)

Load another AptioFix variants externally (Clover / Acidanthera), by disabling internal AptioFix module.
[url:https://sourceforge.net/p/cloverefiboot]
[url:https://github.com/acidanthera/AptioFixPkg]
C: (1.1) Disable internal AptioFix
F: C6050C5D020001
R: C6050C5D020000

C: (1.2) Disable internal AptioFix
F: 488D05C903010049894128
R: 9090909090909090909090

4. xmax的第一个版本中缺少的ozmosis ffs驱动程序depex部分再次添加到ffs文件中。

对于感兴趣的人，这里有一个在dxe依赖部分构建自己的包（包括兼容的ozm ffs compile kext2ffs）：depex package.zip

这是修改后的xmax ozmosis版本（在日志中按发布日期区分：2019-07-01）：

电喷驱动器：Ozmosis XMAX EFI 2019-07-01（推荐测试）url: [url:https://www.hackintosh-forum.de/attachment/107559-ozmosis-xmax-efi-2019-07-01-zip/]

ffs版本：Ozmosis XMAX FFS 2019-07-01（fv推荐ffs压缩版本）url: [url:https://www.hackintosh-forum.de/attachment/107559-ozmosis-xmax-ffs-2019-07-01-zip/]

测试风险自负！


MacOS Catalina的其他文件和驱动程序：

defaults.plist：与MacOS Catalina兼容。SMBIOS:IMAC14,2（展位：2019年7月1日）[OzmosisDefaults14.2.zip]

apfsdriverloader.rev-2.0.7.zip: apfsdriverloader版本2.0.7（来源:https://github.com/acidanthera/ApfsSupportPkg）

hfsplus.zip: hfs驱动程序（可选）（展位号：01.07.2019）

darboot.zip：启动项驱动程序，与MacOS Catalina兼容。集成darboot.plist（来源：https://github.com/cecekpawon/UEFTW/wiki/Releases-Driver-DarBoot）

fakesmc.rev-1800.zip: fakesmc版本6.26-357-gceb835ea.1800（来源：https://bitbucket.org/RehabMan/os-x-fakesmc-kozlek/）
fakesmc 与 virtualsmc 二选一
virtualsmc.rev-1.0.4.zip: virtualsmc.kext作为ffs版本1.0.4（来源：https://github.com/acidanthera/VirtualSMC）

ozmosishftthes.zip: ozmosis hackintosh 论坛主题（来源：https://www.hackintosh-forum.de/index.php/Thread/34158-Neue-Themes-Ozmosis-GUI-BootMenü-UserInterface/）

其他可选驱动程序：acpipatcher（acpi header fix）、partitiondxe（文件系统支持）、dbounce（不要从rom加载驱动程序）（也可以重新发送）

其他信息：macos mojave ozmosis beta oz167x-xmax