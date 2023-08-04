###

<div align="center"><img src="images/OpenCore.png" width="200" height="48"/> EFI</div>
<div align="center">
 <a href="https://www.apple.com/macos">
  <img src="https://img.shields.io/badge/Ventura-13.4.1-informational.svg">
 </a>
 <a href="https://www.apple.com/macos">
  <img src="https://img.shields.io/badge/Sonoma-14.0%20beta3-informational.svg">
 </a>
 <a href="https://github.com/acidanthera/OpenCorePkg">
  <img src="https://img.shields.io/badge/OpenCore-0.9.3-informational.svg">
 </a>
 <a href="https://github.com/saeidex/Ryzentosh/blob/main/LICENSE">
  <img src="https://img.shields.io/github/license/saeidex/Ryzentosh">
 </a>
</div>

##

## Table Of Contents

- [⚙️ Hardware](#-hardware)
- [🖥️ Full Build](#-full-build)
    - [CPU](#cpu)
    - [MOTHERBOARD](#motherboard)
    - [RAM](#ram)
    - [SSD](#ssd)
    - [HDD](#hdd)
    - [CASING](#casing)
    - [MONITOR](#monitor)
    - [PSU](#psu)
    - [MOUSE](#mouse)
    - [KEYBOARD](#keyboard)
- [🔧 BIOS](#-bios)
- [🛠️ Functional](#-functional)
- [🪚 Change it for youself](#-change-it-for-youself)
- [🧰 Tools](#-tools)
- [📃 Scripts](#-scripts)
- [💡 Tips](#-tips)
- [🏞️ Screenshot](#-screenshot)

##

> **Warning**
>
> Use at your own risk. I built this EFI for myself and it does not guarantee 100% work with your hardware.
>
> MLB, ROM, Serial Number, SystemUUID sections are specifically left empty. Use GenSMBIOS to generate SMBios.
>
> I recommend using an iMac20,1, if you are using an iGPU. Otherwise use [these](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html#platforminfo)

## ⚙️ Hardware

| **Category**     | **Component**               |
| ---------------- | --------------------------- |
| **CPU**          | AMD RYZEN 5 5600G           |
| **Graphics**     | Radeon™ Graphics `iGPU`     |
| **Motherboard**  | GIGABYTE B550M AORUS PRO AX |
| **Chipset**      | AMD B550                    |
| **Memory**       | CORSAIR VENGEANCE LPX       |
| **OS Drive**     | HP EX900 `SSD`              |
| **Other Drives** | TOSHIBA P300 1TB `HDD`      |
| **Audio**        | REALTEK ALC1200 CODEC       |
| **LAN**          | REALTEK 2.5GbE LAN CHIP     |
| **Wireless**     | INTEL Wi-Fi 6 AX200         |

> **Note** \
> Instead of dGPU, you can use iGPU in the processor thanks to NootedRed, but then you will have problems with DRM, iServices and sleep.

## 🖥️ Full Build

#### CPU

```txt
    Brand: AMD
    Model: RYZEN 5 5600G
    Codename: CEZANNE
    Cores: 6
    Threads: 12
    Max. Boost Clock: 4.4GHX
    Base Clock: 3.9GHZ
    L2 Cache: 3MB
    L3 Cache: 16MB
    Cpu Socket: AM4
    PCIe: V3.0
    Memory Type: DDR4
    Memory Spec.: MAX. 3200MHZ
    Graphics Model: Radeon™ Graphics
    Graphics Core Count: 7
    S/N: 9LG4349020022
```

#### MOTHERBOARD

```txt
    Brand: GIGABYTE
    Model: B550M AORUS PRO AX
    Chipset: AMD B550
    Cpu Socket: AM4
    PCIe: V4.0/3.0
    Audio: REALTEK ALC1200 CODEC
    Lan: REALTEK 2.5GbE LAN CHIP (2.5 Gbit/1 Gbit/100 Mbit)
    Wireless: INTEL WI-FI 6 AX200
    Form-Factor: MICRO ATX
    S/N: SN220750077930
```

#### RAM

```txt
    Brand: CORSAIR
    Model: VENGEANCE LPX
    Capacity: 8GB
    Speed: 3200MHZ
    Type: DDR4
    S/N(1): 223103322293154
    S/N(2): 223103322293389
```

#### SSD

```txt
    Brand: HP
    Model: EX900
    Form-Factor: PCIe NVMe
    Type: M.2
    Capacity: 250GB
    S/N: HASE22300900487
```

#### HDD

```txt
    Brand: TOSHIBA
    Model: P300
    Form-Factor: SATA
    Type: HDD
    Capacity: 1TB
    Speed: 7200RPM
    S/N: VGH8HE1NS9WG
```

#### CASING

```txt
    Brand: ANTEC
    Model: NX292
    Form-Factor: MID TOWER
    RGB: TRUE
```

#### MONITOR

```txt
    Brand: SAMSUNG
    Model: LF22T350
    Panel: IPS
    Size: 21.5"
    Resoulation: FULL HD
    Refresh-Rate: 75HZ
    S/N: CXWBH4ZT503366IT

    [Warranty]: MINIMUM 3 OR MORE DEAD PIXEL IS REQUIRED TO
    CLAIM WARRANTY. ANY PANEL RELATED PROBLES NEED TO BE
    VALID AND MUST BE VISIBLE TO GENERAL VISION
```

#### PSU

```txt
    Brand: Corsair
    Model: CV450
    Power: 450W
    Certification: 80 Plus Bronze
    Type: Non-Modular
    #CP-9020209-UK/CP-9020209-IN 55.01.470.58
    Warranty: 5 Years
```

#### MOUSE

```txt
    Brand: RAZER
    Model: VIPER MINI
```

#### KEYBOARD

```txt
    [No Data Found]
```

## 🔧 BIOS

<details markdown="1">
    <summary><b>🔌 Settings</b></summary>

| **Component**                  | **Model**          |
| ------------------------------ | ------------------ |
| Fast boot                      | Disabled           |
| SVM Mode                       | Enabled            |
| Above 4G Decoding              | Disabled           |
| Resizable BAR                  | Disabled           |
| Integrated Graphics Controller | Auto               |
| IOMMU                          | Disabled           |
| Initiate Graphic Adapter       | Int Graphics (IGD) |
| UMA Frame buffer Size          | Disabled\*         |
| XHCI Hand-off                  | Enabled            |
| Boot Mode                      | UEFI               |
| Secure Boot and TPM            | Disabled           |

> **Note**
>
> \*If you use iGPU, set minimum 512 mb. There may be artifacts on some PCs/laptops if 512 MB of VRAM is set. To prevent this from happening, you need to set at least 1 GB of VRAM

</details>

**🏞️ More details of my settings can be found [here](https://imgur.com/a/Q2ssS6q)**

**⚠️ You can read more about the BIOS settings in [the guide](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html#amd-bios-settings)**

## 🛠️ Functional

- [x] macOS Ventura thanks to [dortania](https://dortania.github.io/OpenCore-Install-Guide/)
- [x] CPU by [AMD-Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
- [x] Audio by [AppleALC](https://github.com/acidanthera/AppleALC)
  <!-- - [x] Ethernet by RealtekRTL8111 -->
  <!-- - [x] dGPU by [WhateverGreen](https://github.com/Acidanthera/WhateverGreen) -->
- [x] iGPU by [NootedRed](https://github.com/NootInc/NootedRed)
- [ ] iServices & DRM
- [x] Sleep
- [ ] Airdrop / Handoff (there is no way to check)

> **Note**
>
> If you use iGPU: iServices will not work. There are small graphical artifacts when working with browsers on the Chromium engine. The developer of NootedRed is aware of the problem. A crutch is built into the config, which reduces the number of graphic artifacts

## 🪚 Change it for youself

Edit the core count patch to match your CPU

See [AMD Vanilla OpenCore](https://github.com/AMD-OSX/AMD_Vanilla/tree/master) or [OpenCore-Install-Guide](https://dortania.github.io/OpenCore-Install-Guide/extras/ventura.html#amd-patches)

<details>
    <summary>📖 Mini-Guide</summary>
    Find the three `algrey - Force cpuid_cores_per_package`

    - `kernel -> Patch -> 0  -> Replace` for macOS 10.13.x, 10.14.x
    - `kernel -> Patch -> 1  -> Replace` for macOS 10.15.x, 11.x
    - `kernel -> Patch -> 2  -> Replace` for macOS 12.x, 13.0 to 13.2.1
    - `kernel -> Patch -> 3  -> Replace` for macOS 13.3

    ```
    B8000000 0000 => B8 <core count> 0000 0000
    BA000000 0000 => BA <core count> 0000 0000
    BA000000 0090 => BA <core count> 0000 0090
    BA000000 00 => BA <core count> 0000 00
    ```

    | CoreCount | Hexadecimal |
    | --------- | ----------- |
    | 6 Core    | 06          |
    | 8 Core    | 08          |
    | 12 Core   | 0C          |
    | 16 Core   | 10          |
    | 32 Core   | 20          |
    | 64 Core   | 40          |

    For example 5600G has 6 cores

    ```
    B8 06 00000000
    BA 06 00000000
    BA 06 00000090
    BA 06 000000
    ```

</details>

## 🧰 Tools

1. [Hackintool](https://github.com/benbaker76/Hackintool)
2. [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/)
3. [CPU Name](https://github.com/corpnewt/CPU-Name)

## 📃 Scripts

> **Warning**
>
> All scripts must be used with elevated rights! To do this, use
> `sudo bash <name_script>.sh`

1. **hostname.sh** - change the name of your computer's name or local hostname on Mac
2. **clear-network-interfaces.sh** - helps to solve problems with en0 ethernet

## 💡 Tips

1. If you want to change the processor name, use [this](https://github.com/corpnewt/CPU-Name)
2. If you have a 1-in-1 CPU and motherboard configuration like mine, you can use this config. If it is different, I advise you to assemble it yourself according to [the guide](https://dortania.github.io/OpenCore-Install-Guide/). This way you will spend less time solving problems and everything will work fine. 🫡

## 🏞️ Screenshot

![](https://i.imgur.com/qBf9Km2.png "macOS Ventura")
![](https://i.imgur.com/fpN7SS7.png "macOS Ventura")
![](https://i.imgur.com/y12giX0.png "macOS Ventura")
