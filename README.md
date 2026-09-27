# IEEE-MacTex-Temp

IEEE 论文写作模板仓库（MacTeX + IEEEtran），用于快速启动新的会议 / 期刊论文项目。

## 目录结构

```
IEEE-MacTex-Temp/
└── paper/               # 论文工作目录
    ├── main.tex         # 论文主文件（IEEE 会议模板骨架）
    ├── references.bib   # 参考文献库
    ├── IEEEtran.cls     # IEEE 文档类
    ├── IEEEtran.bst     # IEEE 参考文献样式
    └── figures/         # 图片目录
```

## 编译环境

- [MacTeX](https://www.tug.org/mactex/)（LaTeX 发行版）
- VS Code + [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) 插件

## 编译方式

编译链：`pdflatex → bibtex → pdflatex → pdflatex`

**命令行：**

```bash
cd paper
latexmk -pdf main.tex
```

**VS Code：** 打开 `paper/main.tex`，保存（⌘S）即自动编译；`⌘⌥V` 打开 PDF 预览，支持正反向跳转。

## 开新论文

1. 从本模板仓库新建仓库（或复制 `paper/` 目录）；
2. 修改 `main.tex` 中的标题、作者、摘要等占位内容；
3. 在 `references.bib` 中添加参考文献，正文用 `\cite{key}` 引用。

## 写作约定

- 正文与公式统一放在 `main.tex`，图片放 `figures/`（`main.tex` 已配置 `\graphicspath`）
- 编译中间文件（`.aux`、`.log`、`.bbl` 等）及 `main.pdf` 已被 `.gitignore` 忽略，无需手动清理
