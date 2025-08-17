# 黑苹果 - Opencore EFI for Asrock B660M-ITX/ac

支持 macOS Sequoia 15.6

## 硬件

| **组件**  | **型号**                                                                       |
|---------|------------------------------------------------------------------------------|
| CPU     | Intel Core i5 12400                                                          |
| 主板      | [Asrock B660M-ITX/ac](https://www.asrock.com/mb/Intel/B660M-ITXac/index.asp) |
| 内存      | 32 GB 2400 MHz DDR4                                                          |
| 显卡      | AMD Radeon RX 6600 8 GB                                                      |
| 系统盘     | WD_BLACK SN770 1TB                                                           |
| WiFi/蓝牙 | Intel Wireless AC 9462 and Bluetooth                                         |
| 显示器     | Mi Monitor 3440 x 1440（UWQHD - 超宽四倍高清）                                       |

![Sonoma](./doc/images/sequoia.png)

## BIOS 设置

参考 - [黑苹果华擎 Asrock 主板 BIOS 详细截图设置教程](https://www.bilibili.com/read/cv12293964)

### 先决条件

在BIOS中, 使用 `F6` 切换到 `Advanced Mode`.

### OC Tweaker

- Intel Turbo Boost Max Technology 3.0: **Enabled**

### Advanced - CPU Configuration

- Intel Hyper-Threading Technology: **Enabled**
- **CFG Lock**: **Disabled**
- Intel Virtualization Technology: **Enabled**
- **Software Guard Extensions (SGX)**: **Disabled**

### Advanced - Chipset Configuration

- Primary Graphics Adapter: **PCIe**
- Above 4G Decoding: **Enabled**
- **C.A.M (Clever Access Memory)**: **Enabled**

### Advanced - Storage Configuration

- SATA Mode Selection: **AHCI**

### Advanced - USB Configuration

- Legacy USB Support: **Enabled**
- XHCI Hand-off: **Enabled**

### Advanced - ACPI Configuration

- PS/2 Keyboard S4/S5 Wakup Support: **Enabled**
- USB Keyboard/Remote Power On: **Enabled**
- USB Mouse Power On: **Enabled**

### Advanced - Trusted Computing

- Security Device Support: **Disabled**

### Advanced - Super IO Configuration

- Serial Port: **Enabled**

### Security

- **Secure Boot**: **Disabled**

### Boot

- Fast Boot: **Disabled**
- **CSM**: **Disabled**

## Installation

See [Installation notes](./doc/INSTALLATION.md).

## Notes

- Until now (9/20), we have to use itlwm and HeliPort to use AX201 WiFi.

- To enable OTA update, you have to include [RestrictEvents](https://github.com/acidanthera/RestrictEvents) kext and add boot flag:

  ```text
  revpatch=auto,sbvmm,asset
  ```

- There was an issue about OpenCore will repeatly reboot until successfully get into the macOS. Removing `-v` in `boot-args` seems fix the issue.

## Reference

- [Dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [OpenCore Alder Lake (12th-Gen Intel) Hackintosh Guidance](https://www.reddit.com/r/hackintosh/comments/sp1zgv/opencore_alder_lake_12thgen_intel_hackintosh/)
- [Fix shutdown and restart](https://github.com/Koala166/The-TLDR-Guide-of-Fixing-Shutdown-Restart)
- [OC Sanity Checker](https://sanitychecker.ocutils.me/)
