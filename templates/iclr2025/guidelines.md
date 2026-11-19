# ICLR 2025 论文写作指南

以下说明可帮助你完成 ICLR 2025 的 LaTeX 论文写作流程。

## 通用设置
* **文档类：** `\documentclass{article}`
* **必需宏包：**
    ```latex
    \usepackage{iclr2025_conference,times}
    \usepackage{hyperref}
    \usepackage{url}
    % 可选，但推荐用于数学
    \input{math_commands.tex}
    ```
* **样式文件：** 必须使用 `iclr2025_conference.sty` 和 `iclr2025_conference.bst`。

## 匿名性（关键）
* ICLR 采用双盲评审。**不要**在投稿版本中包含真实作者姓名或单位，请改用 "Ambitious AI Researcher"。
* 引用自己先前的工作时使用第三人称（例如用 "Earlier work by Smalle (2024)..." 而非 "In our earlier work..."）。
* 你可以将论文发布到 arXiv，但不要在论文中明确提及 arXiv 版本，以保持匿名。

## 论文长度
* **正文：** 严格上限为 **10 页**。
* **参考文献：** 不限页数。
* **伦理与可复现性声明：** 可选。不计入页数限制（各最多 1 页）。
* **致谢：** 不计入页数限制。

## 摘要
摘要必须限制为**一个段落**。
* **边距：** 左右边距均缩进 1/2 英寸（3 派卡）。
* **字体：** 10 磅字号，行距 11 磅。
* **标题：** `\textsc{Abstract}` 一词必须居中、小型大写字母、12 磅字号。
* **间距：** 摘要前空两行。

## 论文格式
正文必须限制在宽 5.5 英寸（33 派卡）、长 9 英寸（54 派卡）的矩形区域内。左边距为 1.5 英寸（9 派卡）。
* **字体：** 推荐 Times New Roman（通过 `times` 宏包）。
* **字号：** 10 磅字号，行距 11 磅。
* **段落：** 以 1/2 行距分隔，**不缩进**。
* **论文标题：** 17 磅、小型大写字母、左对齐。

### 标题
* **一级标题：** 小型大写字母（`\textsc`），左对齐，12 磅。前空一行，后空 1/2 行。
* **二级标题：** 小型大写字母，左对齐，10 磅。前空一行，后空 1/2 行。
* **三级标题：** 小型大写字母，左对齐，10 磅。前空一行，后空 1/2 行。

## 引用与参考文献
使用 `natbib` 宏包（样式文件会自动加载）。
* **叙述式引用：** 使用 `\citet{Gomu2024}` $\rightarrow$ "Gomu et al. (2024)"。
* **括号式引用：** 使用 `\citep{Gomu2024}` $\rightarrow$ "(Gomu et al., 2024)"。
* **参考文献：**
    ```latex
    \bibliography{references}
    \bibliographystyle{iclr2025_conference}
    ```

## 图与表
* 所有插图必须整洁、清晰、可读。
* **图注：** 小写（首词和专有名词除外）。
* **位置：**
    * **图：** 图注位于图**之后**（下方）。
    * **表：** 表注位于表**之前**（上方）。

### 图示例代码
```latex
\begin{figure}[h]
\begin{center}
%\framebox[4.0in]{$\;$}
\fbox{\rule[-.5cm]{0cm}{4cm} \rule[-.5cm]{4cm}{0cm}}
\end{center}
\caption{Sample figure caption.}
\end{figure}
```

### 表示例代码
```latex
\begin{table}[t]
\caption{Sample table title}
\label{sample-table}
\begin{center}
\begin{tabular}{ll}
\multicolumn{1}{c}{\bf PART}  &\multicolumn{1}{c}{\bf DESCRIPTION}
\\ \hline \\
Dendrite         &Input terminal \\
Axon             &Output terminal \\
Soma             &Cell body (contains cell nucleus) \\
\end{tabular}
\end{center}
\end{table}
```

## 数学符号
* ICLR 鼓励使用 `\input{math_commands.tex}` 统一符号（基于深度学习教材的符号体系）。
* 变量：斜体（$a$、$\va$、$\mA$）。
* 随机变量：正体（$P(\ra)$）。
* 集合：黑板粗体（$\R$、$\sA$）。
* 函数：标准 LaTeX（$f(\vx)$）。

## 可选声明
这些声明应放在正文末尾、参考文献之前。
1.  **伦理声明：**（可选，最多 1 页）说明潜在关切（人类受试者、敏感数据、偏见等）。
2.  **可复现性声明：**（可选，最多 1 页）引用代码、证明或数据处理步骤以确保可复现性。

## 重要规则
* **格式：** 不要修改正文矩形的宽度或长度，也不要修改字号。
* **行号：** 不要在正文中引用行号（样式文件会自动添加行号供评审使用）。
* **附录：** 可以在主 PDF 最末尾（参考文献之后）加入附录。使用 `\appendix` 开始该部分。
* **图片目录：** 为保证编译一致，所有图片都放在 `figures` 目录下。在 `\includegraphics` 命令中始终包含 `figures/` 前缀（例如 `figures/figure_1.pdf`）。
* **作者信息：** 写作中始终使用以下作者信息占位符：
    * Ambitious AI Researcher, AI Research Institute, 123 AI Avenue, ML City, researcher@institute.ai