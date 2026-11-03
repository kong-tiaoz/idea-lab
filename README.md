# 创意实验室 · Idea Lab

把随手记下的创意，逐步变成可以展示和使用的项目。

## 在 VS Code 中打开

双击 `idea-lab.code-workspace`，或在终端运行 `code F:\idea-lab\idea-lab.code-workspace`。
打开本文件，按 Ctrl+Shift+V 预览，点击相对链接进入各目录。

- [创意收集箱](ideas/README.md)：还没有开始实现的点子。
- [项目总览](projects/README.md)：正在实现和已经完成的项目。
- [开源学习库](references/README.md)：项目链接、来源和学习笔记。
- [可复用模板](templates/README.md)：新创意、新项目和学习记录。
- [VS Code 与同步说明](docs/vscode-and-git.md)
- [归档区](archive/README.md)

## 第一个项目

[001 · onebigbutton](projects/onebigbutton/README.md)

当前已在嘉立创EDA绘制 CH552G 原理图，器件标准化与 USB1 符号/封装映射问题待处理；固件、PCB 和外壳尚未完成。

## 目录约定

```text
idea-lab/
├── ideas/                 创意收集
├── projects/              自己实现的项目
│   └── onebigbutton/
│       ├── docs/          需求、方案、进度
│       ├── hardware/      原理图、PCB、接线、物料
│       ├── firmware/      设备固件
│       ├── software/      电脑端辅助程序（需要时）
│       ├── enclosure/     外壳、尺寸、模型
│       ├── assets/        图片与演示素材
│       └── test-results/  实测记录
├── references/            开源参考与学习笔记
├── templates/             通用模板
├── docs/                  仓库使用说明
├── archive/               暂停或结束的内容
├── .vscode/               VS Code 工作区设置
└── idea-lab.code-workspace
```

## 从创意到成品

1. 用 [创意模板](templates/idea.md) 在 ideas 中记录想法。
2. 决定开始后，复制 templates/project 到 projects，改成 `002-short-name` 等名称。
3. 更新项目总览，记录需求、实现过程、运行方法和实测结果。
4. 在 VS Code 的源代码管理中提交，再点“同步更改”。

Markdown、代码、配置均可在 VS Code 中编辑和提交。固件运行需要对应开发板与工具链；原理图、PCB 和三维模型需要各自的设计工具，VS Code 负责统一管理文件。

## 公开内容与授权

本仓库公开。仅提交愿意公开的创意与资料；账号管理资料、密钥和本地配置不要放入。
参考项目先记录链接与学习笔记。若以后引入源码，保留原作者署名、许可证与来源版本。
原创内容的开源许可证尚未选定；公开可见不代表已授予任意复用授权。
