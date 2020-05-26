# Hackintosh for AMD 3900X using OpenCore

## Specification

> CPU: AMD Ryzen9 3900X 12 Core 24 Thread
> Motherboard: MSI X570-A Pro
> Cooler: Noctua NH-D15S
> Memory: Asgard Loki RGB 8GB * 2 DDR4 3200
> Storage: WD SN750 500G
> GPU: RX580 4G with MSI vBIOS
> Power Supply: Seasonic Focus 750 / Antec 750

## Preparation

### Bios Settings
Due to different Bios version, some settings may differ. If your motherboard is different from me, just give a try.

* EHCI Handoff -> Enabled
* XHCI Handoff -> Enabled
* Serial and Parallel ports -> Disabled
* SATA Port -> AHCI
* CSM -> Disabled
* Secure Boot -> Disabled

> Note: CSM should be disabled. If your graphic card displays "support UEFI Launch", but when you disable the CSM option, your system won't boot, then you should flash the vBios in the repo to enable true UEFI in your GPU

### Start

You should prepare a mouse, a keyboard and a USB Stick(16G or larger is better)

#### Download macOS image

1. Get [gibMacOS](https://github.com/corpnewt/gibMacOS.git) from Github.
2. Run gibMacOS.bat as Admin. Upon first run of gibMacOS it'll download and install some requirements. This is normal.
3. gibMacos will allow you to choose the macOS version, We type *1R* to choose macOS Catalina with Recovery-Only image.(the whole Catalina image is too large and will slow the process depending on you internet speed)
4. Once downloaded you can proceed to the next step.

#### Creating the Installer

1. Run *MakeInstall* as Admin from within the gibMacOS folder.
2. We choose our usb's number and append the letter *O* (not the number zero).
3. Then press "y" to continue.
4. We go to the *gibMacOS/macOS Downloads/publicrelease/"Version you selected"/* and then hold *Shift* and right click on `RecoveryHDMetaDMG.pkg` and choose `Copy as Path`.
5. Now back to the last cmd window, and right click to paste the path and hit *Enter*
6. The script will take some time(due to your usb's speed), after completion we hit *Enter* to end the process.

#### Config OpenCore
If your computer is as same as mine, you can just copy the *EFI* folder into your USB drive.

If there are some differences in your hardware, you can check [reference sites](#Reference) to match your config.

### Boot macOS

When you hit the power botton, it will guide you to boot opencore, Then you can choose which Operating system to start. We Choose macOS Recovery option.
You should connect your keyboard and mouse in USB 2.0 ports, then select *Disk Utility* to format your ssd to *APFS*, then install the macOS. It will download macOS image from the Internet, time will depend on your internet speed and reliability.

## Reference
[vanilla](vanilla.amd-osx.com)
[OpenCore](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/)
[Kext Repo](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455036&cid=FE4038DA929BFB23)