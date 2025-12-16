<div align="center">

# 西电 LaTeX 模板 macOS 使用指南

[![LaTeX](https://img.shields.io/badge/LaTeX-TeX%20Live%202025-008080.svg)](https://www.tug.org/texlive/) [![License](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE) [![macOS](https://img.shields.io/badge/macOS-Compatible-success.svg)](https://www.apple.com/macos/)

[🇨🇳 中文](./README.md) | [🇺🇸 English](./README_EN.md)

</div>

## 🎯 适用范围

- 支持：博士学位论文、学术型硕士、专业型硕士（含工程硕士等）；本科版未验证，如需使用请自行对照学校规范校对。
- 完整撰写规范与样例：请参阅根目录 `xduts.pdf`，内含章节结构、格式要求和排版示例。


## 🙏 致谢

- 感谢 **[wjm-jimmy](https://github.com/wjm-jimmy)** 师兄贡献的博士论文模板。
- 本项目基于 **[XDUTS](https://github.com/note286/xduts)** 西电 TeX 模板套件。


---

## 📖 概述

本模板专为 **macOS + TeX Live 2025** 环境设计，帮助西电学子高效撰写学位论文。同时，本模板也支持 **Windows** 环境（无需安装额外字体）。

### ✨ 核心工作流

- **macOS**: `解压模板（字体已内置）→ 配置 MacTeX 2025 → 更新宏包 → 编译论文`
- **Windows**: `解压模板（字体已内置）→ 安装 TeX Live → 更新宏包 → 编译论文`

### ⚠️ 重要提示

若跳过任何环节，可能出现：图片位置异常、PDF 盒子错位、宏包缺失等问题。请严格按照以下步骤操作。

---

## 📥 下载模板

推荐直接下载打包好的 Release 版本，根据你的操作系统选择：

👉 **[点击前往 Releases 页面下载](https://github.com/Ronchy2000/Xidian-LaTeX-Template-for-macOS/releases)**

| 版本 | 文件名 | 说明 |
| :--- | :--- | :--- |
| **macOS** | `Xidian-LaTeX-Template-macOS.zip` | ✅ 包含字体文件和 MacTeX 配置脚本 |
| **Windows** | `Xidian-LaTeX-Template-Windows.zip` | ✅ 包含字体文件（移除仅 macOS 需要的脚本） |

---

## 💻 Windows 用户

Windows 用户请直接参考专门的指南：

👉 **[Windows 使用指南 / Windows User Guide](./WINDOWS_README.md)**

> Windows 版本已包含 `Font` 目录字体，解压即可使用，无需额外安装字体或配置 MacTeX。

---

## 🚀 快速开始 (macOS)

### 步骤 1：字体说明（已内置）

本模板默认使用 `font-type = file` 加载 `Font/` 目录中的 Windows 版宋体/黑体/楷体，因此 **macOS 用户无需手动安装字体即可获得与 Windows 一致的排版**。

如需在系统层面（例如 Pages、Word 等软件）使用这些字体，可参考 [Font/Readme.md](./Font/Readme.md) 进行可选安装。

> 💡 字体仅供论文排版测试使用，请遵循 [Font/Readme.md](./Font/Readme.md) 中的版权提示。

#### 字体使用免责声明

`Font/` 目录中的字体文件版权归原权利人所有，仅供学习与论文排版测试。请在下载后 24 小时内删除，勿用于商业用途或传播。使用者如产生任何侵权或纠纷，由本人自行承担，与本仓库及作者无关。

---

### 步骤 2：配置 MacTeX 2025 环境

#### 2.1 检查当前版本

```bash
/Library/TeX/texbin/xelatex --version | head -1
```

**判断结果：**
- ✅ 输出包含 `TeX Live 2025`：已正确配置，跳到 [步骤 2.3](#23-更新宏包必做)
- ⚠️ 输出其他年份或命令不存在：需要安装/切换，继续步骤 2.2

#### 2.2 安装或切换到 2025

详细的安装和切换教程请查看：

👉 **[MacTex_Installation_Settings/Readme.md](./MacTex_Installation_Settings/Readme.md)**

该文档提供：
- 📥 MacTeX 2025 下载与安装指南
- 🔄 多版本切换脚本使用方法
- 🔧 完整的故障排查方案

**快速操作**：
```bash
# 如果系统中已有 2025 但未激活，快速切换：
cd MacTex_Installation_Settings
./switch-texlive.sh 2025
```

#### 2.3 更新宏包（必做）

> ⚠️ **关键步骤**：作者曾因遗漏此步骤导致编译出的图片位置错乱！

无论是新安装还是版本切换，都必须执行：

```bash
sudo tlmgr update --self --all
```

**作用**：
- 更新 `tlmgr` 工具本身
- 同步所有宏包到最新版本
- 修复已知 bug（如 `xdvipdfmx` 图片定位问题）

> 💡 每次模板更新前建议重新执行一次。

**至此，环境配置完成！** 接下来可以开始编译论文。

---

## 📝 编译论文

### 方式 1：命令行编译（推荐）

在项目根目录执行：

```bash
# 编译论文（XeLaTeX + BibTeX）
latexmk -xelatex -bibtex -synctex=1 -interaction=nonstopmode main.tex

# 清理临时文件（保留 .bbl）
latexmk -c

# 完全清理（包括 .bbl）
latexmk -C
```

**编译成功后**，会在根目录生成 `main.pdf`。

---

## ⚙️ 论文信息配置

本模板的详细使用说明书为项目根目录下的 `xduts.pdf`。

论文的元数据（如标题、作者、学位类型等）均在 `main.tex` 的 `info` 字段配置，这是切换博士/硕士、学术/专业的唯一入口；其他排版细节请对照 `xduts.pdf` 的章节要求。常用字段示例如下：

```tex
info = {
    graduate-type = {博士},              % 毕业类型：博士/硕士
    degree-type = {学术},                % 学位类型：学术/专业
    degree = {工学博士},                 % 学位名称
    title = {自适应学习平台排版流程示例},   % 中文标题
    title* = {Sample Workflow...},      % 英文标题
    department = {信息工程学院},          % 学院
    major = {智能系统与工程},             % 专业
    major* = {Intelligent Systems...},  % 专业英文
    submit-date = {2024-9},             % 提交日期
    author = {西电示例同学},              % 作者中文名
    author* = {Sample Student},         % 作者英文名
    supervisor = {示例导师},              % 导师中文名
    supervisor* = {Sample Advisor},     % 导师英文名
    student-id = {2024000000},          % 学号
    % ... 其他配置请参考 main.tex
}
```

---

### 方式 2：使用 TeXstudio

如果你习惯使用图形界面编辑器，可以配置 TeXstudio：

#### 配置步骤

打开 `Options → Configure TeXstudio → Build`，设置：

| 选项 | 配置值 |
|------|--------|
| Default Compiler | `XeLaTeX` |
| Default Bibliography Tool | `BibTeX` |
| PDF Viewer | `Internal PDF Viewer (Embedded)` |
| Quick Build | `txs:///latexmk` |

在 `Commands → Latexmk` 中填入：
```
latexmk -xelatex -bibtex -synctex=1 -interaction=nonstopmode %.tex
```

#### 添加清理命令（可选）

在 `Tools → User Commands` 中添加：
```
latexmk -c %.tex        # Clean
latexmk -C %.tex        # Clean Full
```

#### 锁定主文档

确保 TeXstudio 顶部已锁定 `main.tex` 为 Root 文档。

**配置完成后**，点击 "Build & View" 即可编译并预览论文。

---

## 🔧 进阶配置

### 输出文件集中管理

如果希望保持项目根目录整洁，可将编译输出集中到 `build/` 目录：

```bash
latexmk -xelatex -bibtex -synctex=1 \
  -outdir=build \
  -auxdir=build/aux -emulate-aux-dir \
  -interaction=nonstopmode main.tex
```

**清理命令**：
```bash
latexmk -c -outdir=build -auxdir=build/aux -emulate-aux-dir
latexmk -C -outdir=build -auxdir=build/aux -emulate-aux-dir
```

> 📌 `-emulate-aux-dir` 功能需要 TeX Live 2025。

---

### 使用 latexmkrc 简化命令

在项目根目录创建 `latexmkrc` 配置文件：

```perl
$pdf_mode = 1;
$pdflatex = 'xelatex -interaction=nonstopmode -file-line-error -synctex=1 %O %S';
$bibtex   = 'bibtex %O %S';
$out_dir         = 'build';
$aux_dir         = 'build/aux';
$emulate_aux_dir = 1;
$clean_ext       = 'synctex.gz xdv run.xml';
$clean_full_ext  = 'bbl';
```

**配置后**，只需运行：
```bash
latexmk        # 编译
latexmk -c     # 清理
latexmk -C     # 完全清理
```

**查看 PDF**（可选）：
```bash
ln -sf build/main.pdf ./main.pdf
```

---

## 📂 项目结构与资源管理

### 目录结构

```
.
├── main.tex              # 主文档
├── chapters/             # 各章节内容
├── figures/              # 图片资源
│   ├── ch2/             # 第2章图片
│   ├── ch3/             # 第3章图片
│   └── ...
├── Font/                 # Windows 字体文件
├── MacTex_Installation_Settings/  # MacTeX 管理工具
└── build/                # 编译输出（可选）
```

### 图片管理

- 所有图片统一存放在 `figures/` 目录
- 每章使用独立子目录（如 `ch2/`、`ch3/`）
- 在正文中引用：`\includegraphics{figures/ch2/example.pdf}`

### Git 忽略建议

在 `.gitignore` 中添加：

```gitignore
build/
*.synctex.gz
*.xdv
*.aux
*.log
*.out
```

---

## ❓ 常见问题

### 问题 1：PDF 显示 "tagged" 警告

**错误信息**：`PDF file is tagged...` 或 `Object @page.n already defined.`

**原因**：旧版 PDF 图片的 metadata 问题。

**解决方案**：
- 保持 TeX Live 为最新版本（执行 `sudo tlmgr update --self --all`）
- 或在 `\includegraphics` 中添加参数：`pagebox=cropbox` 或 `trim=...`

---

### 问题 2：中文标点报错

**错误信息**：`Missing character: There is no ， in font cmr12!`

**原因**：中文标点符号不能直接放在数学模式中。

**解决方案**：使用 `\text{，}` 包裹中文标点。

```latex
% 错误
$x = 1，y = 2$

% 正确
$x = 1\text{，}y = 2$
```

---

### 问题 3：编译后图片位置错误

**原因**：未执行宏包更新。

**解决方案**：立即执行 `sudo tlmgr update --self --all`。

---

## 📚 关于 XDUTS

**XDUTS**（Xidian University TeX Suite）是西电官方认可的本科/研究生论文 LaTeX 模板，支持多平台：

- ✅ Windows / macOS / Linux
- ✅ Overleaf 在线编辑
- ✅ XeLaTeX 编译

### 模板文件

- `xdufont.sty` - 字体配置宏包
- `xdupgthesis.cls` - 研究生论文文档类
- `xduugthesis.cls` - 本科生论文文档类
- `xduugtp.cls` - 本科生课程论文文档类

### 更多资源

- 📖 完整文档：`xduts.pdf`
- 🔗 上游项目：[XDUTS on GitHub](https://github.com/note286/xduts)
- 📦 CTAN 发布：[CTAN Package](https://www.ctan.org/pkg/xduts)

---

## ⚡ 一句话工作流

```bash
# 1️⃣ 更新宏包
sudo tlmgr update --self --all

# 2️⃣ 编译论文
latexmk -xelatex -bibtex -synctex=1 main.tex

# 3️⃣ 清理临时文件
latexmk -c
```

**祝各位论文写作顺利！** 🎓
