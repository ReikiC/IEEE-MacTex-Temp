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

编译器为 **XeLaTeX**（支持中文，正文可直接输入汉字）：

- `.vscode/settings.json` 已将唯一编译 recipe 固定为 `latexmk -xelatex`，保存即自动编译；
- 命令行需显式指定引擎：`latexmk -xelatex main.tex`。

编译链：`xelatex → bibtex → xelatex × 2`（由 latexmk 自动完成）

**命令行：**

```bash
cd paper
latexmk -xelatex main.tex
```

**VS Code：** 打开 `paper/main.tex`，保存（⌘S）即自动编译；`⌘⌥V` 打开 PDF 预览，支持正反向跳转。

## 开新论文

1. 从本模板仓库新建仓库（或复制 `paper/` 目录）；
2. 修改 `main.tex` 中的标题、作者、摘要等占位内容；
3. 在 `references.bib` 中添加参考文献，正文用 `\cite{key}` 引用。

## 写作约定

- 正文与公式统一放在 `main.tex`，图片放 `figures/`（`main.tex` 已配置 `\graphicspath`）
- 正文支持直接输入中文（`ctex` 宏包 + XeLaTeX）。一般用中文写草稿，定稿时把中文替换为英文即可，无需改编译配置；如要换回 pdflatex，`.vscode/settings.json` 内附有注释形式的英文版配置，对调注释即可
- 编译中间文件（`.aux`、`.log`、`.bbl` 等）及 `main.pdf` 已被 `.gitignore` 忽略，无需手动清理
