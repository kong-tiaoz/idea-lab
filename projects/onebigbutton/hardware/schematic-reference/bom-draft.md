# BOM 草案（阅读版）

在 VS Code 打开本文件后，按 Ctrl+Shift+V，即可显示排版好的表格。

每行代表一个元件，数量均为 1。位号用于在图中定位；型号/参数用于选料；封装用于核对焊盘。

本文件由 [原始 CSV](bom-draft.csv) 转成阅读版，未改变电路或选型；仍为 A0 草案。

| 位号 | 型号 / 参数 | 封装 |
| --- | --- | --- |
| U1 | RP2040 | QFN-56 + exposed pad 57 |
| U2 | AP2112K-3.3TRG1 | SOT-25 / SOT-23-5 |
| U3 | W25Q16JVSNIQ / 2 MB | SOIC-8 150 mil |
| U4 | ST USBLC6-2SC6 | SOT-23-6 |
| J1 | USB-C USB2.0 receptacle | 16-contact logical pinout / footprint TBD |
| J2 | External NO momentary button | 2-pin connector TBD |
| J3 | SWD header / pads | 4-pin 2.54 mm or test pads |
| R1 | 5.1k 1% | 0603 |
| R2 | 5.1k 1% | 0603 |
| R3 | 27R 1% | 0603 |
| R4 | 27R 1% | 0603 |
| R5 | 10k 1% | 0603 |
| R6 | 1k 1% | 0603 |
| R7 | 1k 1% | 0603 |
| R8 | 10k 1% | 0603 |
| R9 | 10k 1% | 0603 |
| R10 | 1k 1% | 0603 |
| R11 | 1k 1% | 0603 |
| C1 | 1uF / 10V | 0603 |
| C2 | 4.7uF / 10V | 0603 |
| C3 | 100nF / 10V | 0603 |
| C4 | 1uF / 6.3V | 0603 |
| C5 | 1uF / 6.3V | 0603 |
| C6 | 100nF / 6.3V | 0603 |
| C7 | 100nF / 6.3V | 0603 |
| C8 | 100nF / 6.3V | 0603 |
| C9 | 100nF / 6.3V | 0603 |
| C10 | 100nF / 6.3V | 0603 |
| C11 | 100nF / 6.3V | 0603 |
| C12 | 100nF / 6.3V | 0603 |
| C13 | 100nF / 6.3V | 0603 |
| C14 | 100nF / 6.3V | 0603 |
| C15 | 100nF / 6.3V | 0603 |
| C16 | 100nF / 6.3V | 0603 |
| C17 | 15pF C0G / 50V | 0603 |
| C18 | 15pF C0G / 50V | 0603 |
| C19 | 10nF / 6.3V | 0603 |
| Y1 | ABM8-272-T3 / 12 MHz / CL=10pF | 3.2 x 2.5 mm |
| SW1 | BOOTSEL NO momentary | 2-terminal logical switch |
| SW2 | RESET NO momentary | 2-terminal logical switch |
| D1 | Green status LED optional | 0603 |
