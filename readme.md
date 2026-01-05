# ZJU LaTeX Resume Template
[![Build Resume](https://github.com/maksymilan/zju-resume-template/actions/workflows/build.yml/badge.svg)](https://github.com/maksymilan/zju-resume-template/actions/workflows/build.yml)

这是一个浙江大学 LaTeX 简历模板。

## 🥳 效果
![简历效果](CV.jpg)

## 📝 环境与依赖 (Environment & Dependencies)

### 1. TeX 发行版 (Distribution)

* **建议使用**: `TeX Live 2024`
* *使用其他发行版 (如 MiKTeX, MacTeX) 的最新版本通常也能成功，但需确保所有宏包为最新。*

### 2. 编译引擎 (Engine)

* **必须使用**: `XeLaTeX`
* *注意：本项目因使用了 `fontspec` (加载 OpenType/TrueType 字体) 和 `xeCJK` (处理中文) 宏包，**无法使用 `pdfLaTeX` 进行编译**。*

### 3. 项目文件结构 (Project Structure)

**本项目已包含所有必需的字体文件**，无需额外下载。请确保您的文件目录结构与下方完全一致，尤其是 `fonts` 文件夹和根目录下的 `fontawesomesymbols-*.tex` 文件。

```
├── CV.tex                           # LaTeX 主文件
├── Makefile                         # 编译脚本
├── README.md                        # 说明文件
├── avatar.jpg                       # 个人照片
├── CV.png                           # 简历预览图
├── zju.png                          # 学校 Logo
├── fontawesomesymbols-generic.tex   # (必须) FontAwesome 定义文件
├── fontawesomesymbols-pdftex.tex    # (必须) FontAwesome 定义文件
├── fontawesomesymbols-xeluatex.tex  # (必须) FontAwesome 定义文件
└── fonts/                           # (必须) 字体文件夹
    ├── fontawesome-webfont.ttf
    ├── fontawesome/
    │   └── opentype/
    │       └── FontAwesome.otf
    ├── hansans/
    │   ├── NotoSansSC-Bold.ttf
    │   └── NotoSansSC-Regular.ttf
    └── Main/
        ├── texgyretermes-bold.otf
        └── texgyretermes-regular.otf
```

### 4. 主要 LaTeX 宏包 (Key Packages)

本项目的正常运作依赖以下几个关键宏包，通常 TeX Live 发行版会内置：

* `fontspec` 和 `xeCJK`
* `fontawesome`
* `geometry`
* `titlesec`
* `tikz`
* `hyperref`

## 🚀 如何编译 (Compilation)

本项目已提供 `Makefile`，可以直接 `make` 命令进行操作。

### 1. 编译 PDF

在项目根目录下，打开终端并执行：

```bash
make
```

如果直接编译报错，可能是字体未安装，可以先双击fonts文件夹内的字体进行安装，然后重新编译

此命令成功后，会在目录下生成 `CV.pdf` 文件。

### 2. 清理辅助文件

如果您想清理编译过程中产生的临时文件 (如 `.aux`, `.log` 等)，可以执行 `Makefile` 中已定义好的清理命令：

```bash
make clean
```

## ☁️ 在线自动构建 (GitHub Actions)

本项目配置了 GitHub Actions 自动化构建流程。**您无需在本地安装庞大的 LaTeX 环境**，只需在 GitHub 上修改代码，即可自动生成 PDF 简历。

### 使用步骤：

1. **Fork 本项目**：点击右上角的 `Fork` 按钮，将项目复制到您的 GitHub 账号下。
2. **修改代码**：在您的仓库中，直接编辑 `CV.tex` 文件（或上传您的修改）。
3. **自动触发**：一旦您提交 (Commit) 并推送 (Push) 代码，GitHub Actions 会自动开始构建。
4. **下载简历**：
    *   点击仓库上方的 **Actions** 标签页。
    *   在左侧列表中点击 **Build Resume** 工作流。
    *   点击最新的那次运行记录（通常显示为绿色对勾 ✅）。
    *   在页面底部的 **Artifacts** 区域，点击 **CV-PDF** 即可下载生成的 PDF 文件。

## 参考与致谢 (Acknowledgements)

*   [billryan/resume](https://github.com/billryan/resume): 相关参考，

# License
[The MIT License (MIT)](http://opensource.org/licenses/MIT)。