<!-- Badge for License -->
<div align="right">

  [![](https://img.shields.io/badge/docs-Wiki-F7D360.svg?logo=&style=flat-square)](https://hsins.me/NTU-Thesis/)
  [![](https://img.shields.io/github/license/Hsins/NTU-Thesis.svg?style=flat-square)](./LICENSE)

</div>

<!-- Logo -->
<p align="center">
  <img src="https://i.imgur.com/x2M158J.png" alt="NTU Thesis" height="150px">
</p>

</div>

<!-- Title and Description -->
<div align="center">

# NTU Thesis

📖 _Unofficial LaTeX and Word templates for your master/doctor thesis at National Taiwan University._

![](https://img.shields.io/badge/LaTeX%202%CE%B5-3.14159265-blueviolet?logo=latex&style=flat-square)
![](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg?style=flat-square)
<br>
[![](https://img.shields.io/badge/GitHub%20Actions%20-Open%20as%20Template-2088ff?logo=github-actions&style=flat-square)](https://github.com/Hsins/NTU-Thesis-CI/)
[![](https://img.shields.io/badge/Overleaf%20-Open%20as%20Template-46a247?logo=overleaf&style=flat-square)](https://www.overleaf.com/latex/templates/national-taiwan-university-thesis-template/hvfybyfxgztt)

</div>

## Structures

```
├── back
│   ├── appendix-*.tex              // 附錄
│   ├── references.bib              // 參考文獻
│   └── ...
├── contents
│   ├── chapter-*.tex               // 論文內容
│   └── ...
├── figures
│   └── ...
├── fonts
│   ├── chinese
│   │   ├── BiauKai.ttf             // 標楷體
│   │   ├── Arphic-*.ttf            // 文鼎字體
│   │   ├── MOE-*.ttf               // 教育部字體
│   │   ├── WHZ-*.ttf               // 王漢宗字體
│   │   ├── cwTeX-*.ttf             // cwTeX 字體
│   │   └── ...
│   └── english
│       ├── Times New Roman-*.ttf   // Times New Roman 字體
│       └── ...
├── front
│   ├── abstract.tex                // 摘要
│   ├── acknowledgement.tex         // 致謝
│   └── denotation.tex              // 符號列表
├── main.tex                        // 主文件
├── ntusetup.tex                    // 模板設定
├── ntuthesis.cls                   // 模板文件
└── ...
```

# Build

NTU-Thesis is built with XeLaTeX + BibTeX. The standard command sequence is:

```sh
cd ~/Desktop/NTU-Thesis
xelatex main.tex
bibtex main
xelatex main.tex
xelatex main.tex
```

The three xelatex passes are needed so the table of contents, list of figures, list of tables, and all cross-references (\ref, \cite) converge. bibtex only needs to run when the bibliography changes.

For a quick rebuild after edits that don't touch citations, two xelatex passes are usually enough:

```sh
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

The flags suppress interactive prompts on errors and abort on the first failure, which is convenient for scripted rebuilds.

A successful build produces main.pdf in the same directory. The template's magic comments (`% !TEX TS-program = xelatex`, `% !BIB program = bibtex`) at the top of main.tex also let editors like TeXShop or VS Code's LaTeX Workshop pick the right toolchain automatically.


## License

Licensed under the MIT License, Copyright © 2017-present Hsins.
