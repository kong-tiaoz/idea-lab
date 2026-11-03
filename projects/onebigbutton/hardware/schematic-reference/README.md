# onebigbutton 原理图接线参考 · A0

**历史方案：本目录为 RP2040 参考图，已于 2026-11-03 被 CH552G 方案取代，不适用于当前原理图。**

日期：2026-11-02。用户自行在嘉立创EDA选料、放置和连接；本交付没有写入或修改嘉立创EDA工程。

这是原理图参考草案，不是电气仿真结果、EDA 原生工程或可直接投板文件。

## 查看图纸

| 图页 | 可放大矢量图 | 图片 |
| --- | --- | --- |
| USB-C、ESD 与 3.3V 电源 | [SVG](01-usb-power.svg) | [PNG](01-usb-power.png) |
| RP2040、Flash 与晶振 | [SVG](02-mcu-flash-clock.svg) | [PNG](02-mcu-flash-clock.png) |
| 电源去耦、按钮与下载调试 | [SVG](03-power-button-debug.svg) | [PNG](03-power-button-debug.png) |

SVG 可用浏览器打开、任意放大，或在 VS Code 编辑；PNG 可在 VS Code 直接查看。

## 怎么照着连接

1. 按 [BOM 草案阅读版](bom-draft.md) 选择相同型号和封装，逐项核对库符号及封装。此表没有宣称当前库存、价格或装配资格已核验。
2. 按图中的位号、物理脚号和网名连接。同名网络跨图页相连；U1A/U1B 是同一颗 RP2040 的分组表示。
3. 用 [逐脚连接表阅读版](pin-connections.md) 对账。U1 包含全部 57 个物理连接点，57 为底部裸露焊盘。
4. `noConnect=True` 表示该脚独立悬空，在 EDA 中加非连接标记；**不要创建名为 NC 的网络把这些脚连起来**。
5. C6–C13、C14–C15 在图中合并展示，但每个编号均为独立电容，按第 03 页的电源脚对应说明就近放置。

J1 目前采用标准 USB-C USB2.0 插座的逻辑触点名。具体型号未定，不能把图中的 A/B 触点名当作任意库器件的焊盘编号。
J2 是两线按钮接口，暂不绑定大按钮尺寸。SW1、SW2 是独立的 BOOTSEL / RESET 常开开关；实际四脚轻触开关应核对内部并联脚。
J3 的 3.3V 是调试器电平参考，主板由 USB 供电，不默认从调试器反向供电。
D1 和 R11 为可选运行指示灯，不代表电脑输入法真实状态；不装时 GPIO25 保持未使用。
常用阻容建议 0603；电容需按 BOM 耐压及 X5R/X7R 选型，晶振负载电容使用 C0G/NP0。

## 关键连接

- USB：DP / DM 经各自 27Ω 到 U1.47 / U1.46。两根 CC 各用独立 5.1kΩ 下拉。
- ST USBLC6-2SC6：1/6 同为 DP；3/4 同为 DM；2 接地；5 接 VBUS。不得以其他厂商同名料号未经核对替换。
- U1.45 输出 +1V1，只供 U1.23 / U1.50 及对应去耦；不能短接到 +3V3。U1.19 与 U1.57 接地。
- 按钮：J2.1 → R10 → BTN_N → GPIO0；J2.2 接地。BTN_N 由 R9 上拉、C19 滤波，仍需固件消抖。
- BOOTSEL 与外置大按钮不同：SW1 通过 1kΩ 拉低 QSPI_CS_N。
- 晶振：使用 ABM8-272-T3；XOUT 经 1kΩ 后接晶振一端，XIN 接另一端，两端各 15pF 对地。

## 数据与验证范围

[circuit.json](circuit.json) 保存元件和逐脚连接，CSV 与图片来自同一版设计。
已核对数据结构、RP2040 物理脚覆盖、关键网络与图片排版。
没有 EDA ERC/DRC、SPICE 仿真、PCB 布线或实板验证结果。

## 依据

- [RP2040 硬件设计指南](https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040.pdf)：最小系统、USB、BOOTSEL、晶振与电源。
- [RP2040 芯片手册](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)：物理引脚。
- [Diodes AP2112 手册](https://www.diodes.com/datasheet/download/AP2112.pdf)：SOT25 引脚和输入/输出电容。
- [ST USBLC6-2 手册](https://www.st.com/resource/en/datasheet/usblc6-2.pdf)：SC6 引脚。
- [Abracon ABM8-272-T3 手册](https://abracon.com/datasheets/ABM8-272-T3.pdf)：指定晶体参数；负载外围参考 RP2040 指南。
- [Winbond W25Q16JV 原厂手册，立创托管](https://datasheet.lcsc.com/datasheet/pdf/6af339d9cd67c493284703db48d902aa.pdf?productCode=C377853)：SOIC-8 引脚及 SNIQ 封装。该 PDF 由另一封装商品页托管，选型使用文档内明确列出的 SNIQ，不采用 URL 的商品 C 号。
