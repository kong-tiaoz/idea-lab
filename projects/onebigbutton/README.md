# 001 · onebigbutton

## 创意

制作一个放在桌面上的独立大按钮，按一下切换中英文输入，减少寻找键盘切换键的动作。

## 当前状态

目录和需求已建立，尚未选定器件、编写固件或验证切换效果。

首版：USB 有线，Windows 11 + 微信输入法，模拟 Ctrl + 空格；直接制作 PCB 原型，跳过面包板。

- [需求与待确认事项](docs/requirements.md)
- [USB 自研版设计草案](../../docs/superpowers/specs/2026-11-02-onebigbutton-usb-design.md)
- [实现路线与里程碑](docs/roadmap.md)
- [相关开源项目](../../references/onebigbutton.md)

## 文件放哪里

| 目录 | 内容 |
| --- | --- |
| docs | 需求、方案、决定和进度 |
| hardware | 接线图、原理图、PCB、物料清单 |
| firmware | 按钮设备上的程序 |
| software | 需要时加入的电脑端辅助程序 |
| enclosure | 大按钮外观、尺寸、外壳模型 |
| assets | 图片、照片、演示 |
| test-results | 不同输入法、软件和连接条件的实测记录 |

## 运行入口

本阶段只有项目说明，没有可烧录或可运行的按钮程序。
在 VS Code 打开整个工作区即可编辑、预览文档并提交。
选定主控与固件路线后，在 firmware 中补齐工具链配置、编译和烧录任务。
