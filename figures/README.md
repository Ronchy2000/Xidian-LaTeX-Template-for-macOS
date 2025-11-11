# Figures 目录说明

[🇨🇳 中文](#figures-目录说明) | [🇺🇸 English](#figures-directory-guide)

此目录用于存放可公开的示例图片。模板按章节划分子目录（如 `ch2/`、`ch3/` ...），并在每个子目录中默认放置 `xdulogo.pdf` 作为占位图，方便在对应章节引用。编写真实论文时，请将章节相关的插图放入相同的子目录中，或根据需要新增目录；在正文中使用 `\includegraphics{figures/chX/filename}` 的形式调用。

存图建议：
- 统一使用 PDF/SVG/PNG 等矢量或高分辨率位图；
- 不要放入含有敏感信息或受限版权的素材；
- 如果需要额外子目录，可继续沿用 `figures/<子目录>/文件名` 的方式引用；无需全局 `\graphicspath`。

---

# Figures Directory Guide

[🇨🇳 中文](#figures-目录说明) | [🇺🇸 English](#figures-directory-guide)

This directory is for storing publicly shareable example images. The template organizes subdirectories by chapter (e.g., `ch2/`, `ch3/` ...), with each subdirectory containing a default `xdulogo.pdf` as a placeholder for easy reference in the corresponding chapter. When writing your actual thesis, place chapter-related figures in the same subdirectory or create new directories as needed. Use `\includegraphics{figures/chX/filename}` in your text to reference them.

Image Storage Recommendations:
- Use PDF/SVG/PNG or other vector/high-resolution bitmap formats consistently;
- Do not include materials with sensitive information or restricted copyrights;
- For additional subdirectories, continue using the `figures/<subdirectory>/filename` reference format; no need for global `\graphicspath`.
