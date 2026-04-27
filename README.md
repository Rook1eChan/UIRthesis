# UIRthesis
UIR 本科毕业论文模板

修改自天津大学2024本科毕业生论文模板
https://www.overleaf.com/latex/templates/tian-jin-da-xue-tianjin-university-tju-2024ben-ke-sheng-bi-ye-lun-wen/vprtxtfcrcmd

## 1. 公式环境

公式应使用 `algorithm2e` 的语法。

## 2. 参考文献排序

默认情况下，参考文献是按照正文中引用的先后顺序排列的。如果需要修改为：

- **中文文献在前，英文文献在后**
- **中文文献按作者拼音顺序排列**
- **英文文献按作者字母顺序排列**

进入 `format.tex`，找到 `\makereferences` 函数，改为如下代码：

```latex
\def\makereferences{
    \titleformat{\chapter}{\centering\xiaosan\hei}{\chaptername}{1em}{}
    \chapter*{\bibname}
    \defaultfont
    
    \begin{thebibliography}{99}
    
    % =================== 中文文献（按作者拼音排序）===================
    
    \bibitem{JSYJ202508002}
    曹荣荣, 柳林, 于艳东, 等. 融合知识图谱的大语言模型研究综述[J]. 计算机应用研究, 2025, 42(08): 2255--2266.
        
    % ... 其他中文文献按拼音顺序添加 ...
    
    % =================== 英文文献（按作者字母排序）===================
    
    \bibitem{anthropic2025claudecode}
    Anthropic. Claude Code: Agentic Coding Assistant[EB/OL]. 2025. \url{https://code.claude.com/docs/en/overview}. Accessed: 2025-12-04.
    
    % ... 其他英文文献按字母顺序添加 ...
       
    \end{thebibliography}
    
    \phantomsection
    \markboth{参考文献}{参考文献}
    \addcontentsline{toc}{chapter}{参考文献}
}
```

可以把你的ref.bib喂给AI，让他自动排序并生成新的\makereferences函数。
