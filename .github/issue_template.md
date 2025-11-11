## 📋 提交 Issue 前请阅读

> 点击上方的 **Preview** 来阅读以下内容，阅读完毕后切换至 **Write**，将包括本段在内的所有内容全部**清空**再提问。

---

### ⚠️ 提问前必读

- **环境要求**：本仓库专为 **macOS + TeX Live 2025** 设计。如果你使用的是 Windows 或 Linux，请移步 [XDUTS 官方仓库](https://github.com/note286/xduts)。
- **文档优先**：在提问前，请**认真阅读**以下文档：
  - [README.md](https://github.com/Ronchy2000/Xidian-LaTeX-Template-for-macOS/blob/master/README.md) - 主要使用指南
  - [MacTeX 安装指南](https://github.com/Ronchy2000/Xidian-LaTeX-Template-for-macOS/blob/master/MacTex_Installation_Settings/Readme.md) - 环境配置教程
  - [字体安装说明](https://github.com/Ronchy2000/Xidian-LaTeX-Template-for-macOS/blob/master/Font/Readme.md) - 字体配置

### ✅ 提交前检查清单

- [ ] 我已确认使用的是 **macOS** 系统
- [ ] 我已安装 **MacTeX 2025** 并执行了 `sudo tlmgr update --self --all`
- [ ] 我已按照 [Font/Readme.md](https://github.com/Ronchy2000/Xidian-LaTeX-Template-for-macOS/blob/master/Font/Readme.md) 安装了 Windows 字体
- [ ] 我已阅读了 [README.md](https://github.com/Ronchy2000/Xidian-LaTeX-Template-for-macOS/blob/master/README.md) 中的"常见问题"部分
- [ ] 我已尝试清理临时文件（`latexmk -C`）后重新编译

### 📝 Issue 提交规范

1. **一个 Issue 一个问题**：不同问题请分开提交，不要放在一个 Issue 里。
2. **标题简明扼要**：请用一句话概括问题（如："MacTeX 2024 无法编译" 或 "图片位置错乱"）。
3. **使用 Markdown 语法**：
   - 代码请放在代码块中（用三个反引号 \`\`\` 包裹）
   - 错误信息请完整贴出
   - 可以上传截图辅助说明（拖拽图片到文本框）
   - 不熟悉 Markdown？查看 [GitHub 文档](https://docs.github.com/cn/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
4. **提交前预览**：点击 **Preview** 确认格式无误后再提交。

### 🤝 互动礼仪

- ✅ 问题解决后，请**回复告知**是否解决，方便其他遇到相同问题的用户参考。
- ✅ 请使用**网页端**回复 Issue（邮件回复可能导致格式错乱或图片无法显示）。
- ❌ 如果不确定是否为 Bug，建议先在 [Discussions](https://github.com/Ronchy2000/Xidian-LaTeX-Template-for-macOS/discussions) 讨论区询问。

---

## 📝 Issue 模板（请在下方填写）

### 系统环境

- **macOS 版本**：（如 macOS 14.0 Sonoma）
- **MacTeX 版本**：（执行 `/Library/TeX/texbin/xelatex --version | head -1` 查看）
- **芯片架构**：（Intel / Apple Silicon M1/M2/M3）

### 问题描述

（清晰描述你遇到的问题）

### 重现步骤

1. 
2. 
3. 

### 预期行为

（描述你期望发生什么）

### 实际行为

（描述实际发生了什么）

### 错误信息

```
（请将完整的错误信息粘贴在这里）
```

### 相关文件（可选）

（如果需要，可以附上相关的 .tex 文件片段或编译日志）

---

**请删除本模板上方的所有说明文字，只保留"系统环境"及以下的内容进行填写。**
