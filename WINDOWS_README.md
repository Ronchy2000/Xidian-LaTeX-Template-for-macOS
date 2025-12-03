# Windows 使用指南 / Windows User Guide

[🇨🇳 中文](#windows-使用指南) | [🇺🇸 English](#windows-user-guide)

本模板在 Windows 10/11 下经过测试，可正常编译使用。Windows 用户**不需要**安装 `Font` 目录下的字体文件（模板会自动调用系统自带的中文字体）。

---

## 🚀 Windows 使用指南

### 1. 安装 TeX Live
请访问 [TeX Live 官网](https://www.tug.org/texlive/) 下载并安装最新版的 TeX Live（推荐安装完整版）。

### 2. 更新宏包（必做）
安装完成后，请打开命令提示符（CMD）或 PowerShell（管理员模式），执行以下命令以更新所有宏包：

```bash
tlmgr update --all --self
```

> ⚠️ **注意**：此步骤至关重要，否则可能会出现编译错误或排版异常。

### 3. 编译论文

#### 方式一：使用命令行（推荐）
在项目根目录下打开终端，运行：

```bash
latexmk -xelatex -bibtex -synctex=1 -interaction=nonstopmode main.tex
```

#### 方式二：使用 TeXstudio / VS Code
- **TeXstudio**: 确保编译器设置为 `XeLaTeX`。
- **VS Code**: 安装 `LaTeX Workshop` 插件，并使用 `Recipe: latexmk (xelatex)` 进行编译。

---

# Windows User Guide

[🇨🇳 中文](#windows-使用指南) | [🇺🇸 English](#windows-user-guide)

This template has been tested and works correctly on Windows 10/11. Windows users **do NOT** need to install fonts from the `Font` directory (the template automatically uses system-installed Chinese fonts).

---

## 🚀 Windows Usage Guide

### 1. Install TeX Live
Please visit the [TeX Live official website](https://www.tug.org/texlive/) to download and install the latest version of TeX Live (Full installation is recommended).

### 2. Update Packages (Required)
After installation, open Command Prompt (CMD) or PowerShell (as Administrator) and run the following command to update all packages:

```bash
tlmgr update --all --self
```

> ⚠️ **Note**: This step is critical. Skipping it may cause compilation errors or layout issues.

### 3. Compile Thesis

#### Method 1: Command Line (Recommended)
Open a terminal in the project root directory and run:

```bash
latexmk -xelatex -bibtex -synctex=1 -interaction=nonstopmode main.tex
```

#### Method 2: Using TeXstudio / VS Code
- **TeXstudio**: Ensure the compiler is set to `XeLaTeX`.
- **VS Code**: Install the `LaTeX Workshop` extension and use the `Recipe: latexmk (xelatex)` to compile.
