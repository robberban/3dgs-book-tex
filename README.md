# 3D Gaussian Splatting 技术综述

一本关于 3D Gaussian Splatting（3DGS）的中文技术综述。全书共 22 章，从高斯表示、渲染和几何重建讲起，延伸到动态场景、生成、压缩、SLAM、机器人与自动驾驶等应用。阅读时可以先看全书目录，再按感兴趣的方向进入对应章节。

## 2026 年 11 月增补版

本次增补 400 篇 arXiv 论文，所选论文的首次提交日期范围为 2026 年 8 月 1 日至 11 月 19 日。新增正文已逐篇对照原文核对方法、实验条件和适用范围。各章的「近期研究」小节可单独阅读，文中编号可跳到参考文献，本版新增条目的 arXiv 链接可用于打开原论文。

## 源码结构

| 路径 | 内容 |
| --- | --- |
| [main.tex](main.tex) | 全书入口、目录与章节顺序 |
| [preamble.tex](preamble.tex) | 中文排版、模板与宏定义 |
| [chapters/](chapters/) | 正文章节 |
| [chapters/recent/](chapters/recent/) | 分章存放的 400 篇论文增补 |
| [biblio.bib](biblio.bib) · [recent-papers.bib](recent-papers.bib) | 原版与本次增补的参考文献 |
| [tikz/](tikz/) · [figures/](figures/) | TikZ 图源和编译所需图件 |

## 从源码生成 PDF

1. 安装带中文支持的 TeX Live。完整安装可省去逐个补包的步骤。已有精简安装时，确保有 XeLaTeX、BibTeX、CTeX、Fandol、TikZ、tcolorbox、tikzfill、pdfcol、bbm、doublestroke 和 natbib。
2. 在 GitHub 仓库主页通过 **Code → Download ZIP** 下载并解压，或用 Git 克隆仓库。
3. 打开终端，进入解压后含有 `main.tex` 的目录，依次运行：

   ```sh
   xelatex -no-pdf -halt-on-error -interaction=nonstopmode main.tex
   bibtex main
   xelatex -no-pdf -halt-on-error -interaction=nonstopmode main.tex
   xelatex -halt-on-error -interaction=nonstopmode main.tex
   ```

4. 编译完成后，在同一目录打开 `main.pdf`。全书较长，首次编译请等四条命令依次结束。

编译只需要仓库中的源码和图件。本地论文数据库、核验工作文件与生成的整书 PDF 不属于仓库内容。
