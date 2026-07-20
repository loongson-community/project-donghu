Project Donghu
===

[简体中文自述文件 >>](README.zh-cn.md)

![Project Donghu Banner](/assets/header.webp)

Meet Project Donghu, the first open-source motherboard based on the Loongson 3
family of processors.

- Design Lead: Hengrui Zhang ([@Harry2005](https://github.com/Harry2005))
- Contributors: [@C-zitong](https://github.com/C-zitong),
  [@MingcongBai](https://github.com/MingcongBai), [@snowpiaoling](https://github.com/snowpiaoling),
  [@xry111](https://github.com/xry111), [@yangwenqing](https://github.com/yangwenqing),
  et. al.
- Project Support and Fundng: [Loongson Hobbyists' Community](https://loongfans.cn/)

Introduction
---

This project aims to develop a motherboard design that can serve as an alternative to the 
[Loongson XB612B0_V1.2](https://loongfans.cn/en/devices/loongson-xb612b0-v1.2)
motherboard currently available on the market. Like the existing model, this motherboard is equipped with a Loongson 3B6000 processor but features an enhanced core power supply circuit with the potential to support overclocking. It also comes with 4 DDR4 DIMM slots, providing a more flexible upgrade path. Most notably, the motherboard distinguishes itself by incorporating the IX7012 PCIe 3.0 bridge from Innosilicon, which has a significantly smaller physical footprint and much lower power consumption than the Loongson 7A2000.

### Key Specifications

- Processor: Loongson 3B6000 (soldered)
- Form Factor: μATX (244×244mm)
- Key design goals
    - Bolstered core power supply - 7+1 phases (MP2975 + MP85956)
    - Alternative bridge chip design based on the low-power InnoSilicon IX7012
      bridge chip, with 12 PCIe 4.0 downstream lanes.
    - Four DDR4 DIMM slots with support for Registered ECC modules.
    - Integrated slot for Wi-Fi module - m.2 NGFF + antenna assembly.
    - Southbridge bypass switch for an extra PCIe 4.0 x4 NVMe slot (or PCIe 3.0
      x2 as supplied by the southbridge).

Progress
---

Project Donghu is currently a work-in-progress.

- [x] Board Schematics
- [ ] PCB Layout (WIP)
- [ ] EC Firmware (WIP)
- [ ] UEFI Firmware (WIP)
- [ ] Manuals and Packaging (WIP)

Repository Structure
---

```
.
├── docs/				~ Project documentation
│   └── DATASHEETS.md		~ Datasheet references
├── firmware/			~ Firmware sources and binaries
├── hwdesign/			~ Hardware design files
│   ├── pcb/				~ PCB design files
│   └── schematics/			~ Schematics
├── support/			~ End-user-facing documentation
├── COPYING				~ License document (CC BY-SA 4.0)
├── README.md			~ Read-me document (English)
└── README.zh-cn.md		~ Read-me document (Simplified Chinese)
```

Firmware
---

Project Donghu plans on using the reference Loongson UEFI firmware (LsFwSdk),
which is not open-source (sadly... yet?). However, there is a possibility that
we would release a U-Boot-based firmware solution for this board, enabling a
open source firmware-to-boot stage, save for key DDR/PHY binaries.

License
---

All materials found in this repository are all licensed under the
[Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/)
license.
