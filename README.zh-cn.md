“东湖”开源主板计划
===

[英文自述文件 >>](README.md)

![“东湖”开源主板计划头图]()

“东湖”是首款基于龙芯 3 号家族处理器的开源主板设计。

- 主要设计者：张恒瑞 (@Harry2005)
- 贡献者：@C-zitong, @MingcongBai, @snowpiaoling, @xry111, @yangwenqing 等
- 项目支持方：[龙芯爱好者社区](https://loongfans.cn/)

项目简介
---

本项目旨在推出一款可替代当前市面通行[龙芯 XB612B0_V1.2 主板](https://loongfans.cn/en/devices/loongson-xb612b0-v1.2)的设计。该主板同样搭载龙芯 3B6000 处理器，但增强了其供电电路，有实现超频功能的潜力。此外，该主板还搭载 4 个 DDR4 DIMM 插槽，以期实现更灵活的升级路径。更特别地，该主板“与众不同”地搭载了来自芯动科技的 IX7012 PCIe 3.0 桥，其物理尺寸和能耗都远小于龙芯 7A2000。

### 关键参数

- 处理器：龙芯 3B6000 (BGA)
- 板型：μATX (244×244mm)
- 关键设计目标
    - 增强供电：使用 7+1 相供电 (MP2975 + MP85956)
    - 无 7A：使用低功耗芯动科技 IX7012 PCIe 交换芯片提供 12 个 PCIe 3.0 下游通道
    - 内存扩展：4 个可支持 Registered ECC 模组的 DDR4 DIMM 插槽
    - Wi-Fi 集成：支持板载 Wi-Fi 模组，集成天线总成
    - 可定制性：可通过拨码绕过 IX7012 桥以换取一个额外的 PCIe 4.0 x4 NVMe 插槽（否则使用桥片提供的 PCIe 3.0 x2 通道）

项目进展
---

“东湖”项目尚未完工，当前进展如下：

- [x] 整板原理图
- [ ] PCB 布局（制作中）
- [ ] EC 固件（研发中）
- [ ] UEFI 固件（研发中）
- [ ] 手册与包装材料（研发中）

项目结构
---

``` 
.
├── docs/		~ 项目文档
│   └── DATASHEETS.md		~ 数据手册引用列表
├── firmware/           ~ 固件源码及二进制文件
├── hwdesign/           ~ 硬件设计文件
│   ├── pcb/                    ~ PCB 设计文件
│   └── schematics/             ~ 原理图
├── support/            ~ 最终用户文档
├── COPYING             ~ 许可文书 (CC BY-SA 4.0)
├── README.md           ~ 自述文档（英文）
└── README.zh-cn.md     ~ 自述文档（中文）
```

固件
---

“东湖”项目计划使用龙芯公版 UEFI 固件 (LsFwSdk)，该固件（尚未？）开源。但我们也在探索基于 U-Boot 实现该主板的固件，届时除 DDR/PHY 二进制外均可开源。

许可
---

该项目的所有资料均使用[《CC BY-SA 4.0 署名—相同方式共享 4.0 协议国际版》](https://creativecommons.org/licenses/by-sa/4.0/)授权。
