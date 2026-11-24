# 3D Gaussian Splatting 技术综述

使用 XeLaTeX 编译的中文技术综述。主文件是 `main.tex`，近期研究的参考文献在 `recent-papers.bib`，增补正文按章放在 `chapters/recent/`。

2026 年 11 月增补版纳入本书选定的 400 篇近期论文，收录日期范围为 2026 年 8 月 1 日至 11 月 19 日。新增正文已逐篇对照论文原文核对方法、实验与适用范围。

## 编译

使用安装了中文支持的 TeX Live，包含 XeLaTeX、BibTeX、CTeX、Fandol、TikZ、tcolorbox、bbm、doublestroke、natbib 和相关依赖。字体可由 TeX Live 提供。

在仓库根目录执行

```sh
xelatex -no-pdf -halt-on-error -interaction=nonstopmode main.tex
bibtex main
xelatex -no-pdf -halt-on-error -interaction=nonstopmode main.tex
xelatex -halt-on-error -interaction=nonstopmode main.tex
```

编译结果为 `main.pdf`。书中引用的图件保存在 `figures/`。
