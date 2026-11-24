# 3D Gaussian Splatting 技术综述

一本关于 3D Gaussian Splatting（3DGS）的中文技术综述。全书共 22 章，从高斯表示、渲染和几何重建讲起，延伸到动态场景、生成、压缩、SLAM、机器人与自动驾驶等应用。阅读时可以先看全书目录，再按感兴趣的方向进入对应章节。

## 选择版本

| 版本 | 收录范围 | 编译入口 |
| --- | --- | --- |
| 《3D Gaussian Splatting 技术综述》全版 | 22 章，含 2026 年 11 月选定的 400 篇论文增补 | [main.tex](main.tex) |
| 《可信 3D Gaussian Splatting 方法综述》 | 21 章，2026 年 11 月增补 101 篇，正文共 1189 篇 | [reliable-edition/main.tex](reliable-edition/main.tex) |

## 全版的 2026 年 11 月增补

本次增补 400 篇 arXiv 论文，所选论文的首次提交日期范围为 2026 年 8 月 1 日至 11 月 19 日。新增正文已逐篇对照原文核对方法、实验条件和适用范围。各章的「近期研究」小节可单独阅读，文中编号可跳到参考文献，本版新增条目的 arXiv 链接可用于打开原论文。

## 可信版的 2026 年 11 月增补

复核原书未覆盖的 108 项入选记录后，101 篇带有符合原书条件的外部证据，现已按技术主题入章。有 7 篇的代码链接与论文不符或尚未提供完整实现，留在代码待跟进表。作者署名与公开代码用于说明入选理由，实验结论按论文报告的协议解读。

## 源码结构

| 路径 | 内容 |
| --- | --- |
| [main.tex](main.tex) | 全书入口、目录与章节顺序 |
| [preamble.tex](preamble.tex) | 中文排版、模板与宏定义 |
| [chapters/](chapters/) | 正文章节 |
| [chapters/recent/](chapters/recent/) | 分章存放的 400 篇论文增补 |
| [biblio.bib](biblio.bib) · [recent-papers.bib](recent-papers.bib) | 原版与本次增补的参考文献 |
| [reliable-edition/](reliable-edition/) | 可信版的正文、参考文献和代码跟进附录 |
| [tikz/](tikz/) · [figures/](figures/) | TikZ 图源和编译所需图件 |

## 从源码生成 PDF

1. 安装带中文支持的 TeX Live。完整安装可省去逐个补包的步骤。已有精简安装时，确保有 XeLaTeX、BibTeX、CTeX、Fandol、TikZ、tcolorbox、tikzfill、pdfcol、bbm、doublestroke 和 natbib。
2. 在 GitHub 仓库主页通过 **Code → Download ZIP** 下载并解压，或用 Git 克隆仓库。
3. 打开终端。编译全版时进入仓库根目录，编译可信版时进入其中的 `reliable-edition/` 目录。依次运行：

   ```sh
   xelatex -no-pdf -halt-on-error -interaction=nonstopmode main.tex
   bibtex main
   xelatex -no-pdf -halt-on-error -interaction=nonstopmode main.tex
   xelatex -halt-on-error -interaction=nonstopmode main.tex
   ```

4. 编译完成后，在同一目录打开 `main.pdf`。全书较长，首次编译请等四条命令依次结束。

编译只需要仓库中的源码和图件。需要直接阅读可信版时，可到 [GitHub Releases](https://github.com/robberban/3dgs-book-tex/releases/tag/reliable-2026-11) 下载 2026 年 11 月增补版 PDF。论文数据库、核验记录和本地编译产物保留在本地。
