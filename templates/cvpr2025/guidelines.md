# CVPR 2025 论文写作指南

以下说明可帮助你完成 CVPR 2025 的 LaTeX 论文写作流程。

## 语言
所有稿件必须使用英文。

## 投稿政策与匿名性
CVPR 采用双盲评审。作者不得知道审稿人的姓名，审稿人也不得知道作者的姓名。

* **禁止身份信息：** 不要在致谢（如合作者和基金编号）或补充材料中提供可能识别作者身份的信息。
* **链接：** 不要提供指向可识别作者身份的网站的链接。
* **GitHub：** 指向 GitHub 的链接必须匿名。
* **自引用：** 如需引用你本人正在同时投稿的论文，请在补充材料中附上匿名版本，并以匿名方式引用。引用先前工作时不要使用"我的"或"我们的"等字眼；将自己先前的工作当作他人所写来对待（例如用"Smith 等人表明……"而非"我们表明……"）。

## 论文长度
论文正文（不含参考文献部分）不得超过八页。
参考文献部分不计入页数，且参考文献长度不限。
例如，一篇八页正文加两页参考文献的论文，总长度为 10 页。

超长论文，或页边距与格式被认定有显著改动的论文，将不予评审。

## 数学公式
请为所有章节和独立公式编号，如下例所示：
```latex
\begin{equation}
  E = m\cdot c^2
  \label{eq:important}
\end{equation}
```
以及
```latex
\begin{equation}
  v = a\cdot t.
  \label{eq:also-important}
\end{equation}
```

## 论文格式
所有文本必须采用双栏格式。
文本区域的总允许尺寸为宽 $6\frac78$ 英寸（17.46 cm）、高 $8\frac78$ 英寸（22.54 cm）。
每栏宽 $3\frac14$ 英寸（8.25 cm），栏间距为 $\frac{5}{16}$ 英寸（0.8 cm）。
主标题（位于第一页）应从页面顶部边缘起 1 英寸（2.54 cm）处开始。
第二页及后续页面应从顶部边缘起 1 英寸（2.54 cm）处开始。
所有页面的底部边距：对于 $8.5 \times 11$ 英寸纸张，应从页面底部边缘起 $1\frac{1}{8}$ 英寸（2.86 cm）；
对于 A4 纸张，约为从页面底部边缘起 $1\frac{5}{8}$ 英寸（4.13 cm）。

### 字体样式与字体
凡指定使用 Times 之处，也可使用 Times Roman。如果你的文字处理软件两者均不可用，请使用你能获取的、外观最接近 Times 的字体。

### 主标题
标题居中，距第一页顶部边缘 $1\frac{3}{8}$ 英寸（3.49 cm）。标题应使用 Times 14 磅粗体。名词、代词、动词、形容词和副词的首字母大写；冠词、并列连词和介词不大写（除非标题以这类词开头）。

摘要和正文采用双栏格式。

### 正文
正文使用 10 磅 Times 字体，单倍行距。
不要使用双倍行距。
所有段落应缩进 1 派卡（约 $\frac{1}{6}$ 英寸或 0.422 cm）。确保文本两端对齐——即左对齐且右对齐。段落之间不要添加额外的空行。

图和表的标题应使用 9 磅 Roman 字体，如 \cref{fig:onecol,fig:short} 所示。
短标题应居中。

\noindent 标注框应使用 9 磅 Helvetica 非粗体。章节标题及一、二、三级标题仅首词首字母大写。

#### 一级标题
例如，{\large \bf 1. Introduction} 应使用 Times 12 磅粗体，首字母大写，左对齐，前后各空一行。

#### 二级标题
例如，{ \bf 1.1. Database elements} 应使用 Times 11 磅粗体，首字母大写，左对齐，前后各空一行。
如需三级标题（我们不鼓励使用），请使用 10 磅 Times 粗体，首字母大写，左对齐，前空一行，后接句号，正文紧随其后同行。

### 脚注
请谨慎使用 \footnote{脚注的样子就是这样。
它常常分散读者对论证主线的注意力。}。

实际上，应尽量避免使用脚注，将必要的边缘性说明写入正文（如你愿意，可放在括号内，如本句所示）。如需使用脚注，请将其置于引用处所在页面的栏底。
使用 Times 8 磅字体，单倍行距。

### 交叉引用
为便于作者和读者，请使用
```latex
{\small\begin{verbatim}
  \cref{...}
\end{verbatim}}
```
命令交叉引用图、表、公式或章节。

这会在交叉引用旁自动插入相应的标签，如下例所示：
```latex
\begin{quotation}
  To see how our method outperforms previous work, please see \cref{fig:onecol} and \cref{tab:example}.
  It is also possible to refer to multiple targets as once, \eg~to \cref{fig:onecol,fig:short-a}.
  You may also return to \cref{sec:formatting} or look at \cref{eq:also-important}.
\end{quotation}
```
如你不希望缩写标签（例如在句首），可使用
```latex
{\small\begin{verbatim}
  \Cref{...}
\end{verbatim}}
```
命令。示例如下：
\begin{quotation}
  \Cref{fig:onecol} is also quite important.
\end{quotation}

## 表格示例代码
```latex
\begin{table}
  \centering
  \begin{tabular}{@{}lc@{}}
    \toprule
    Method & Frobnability \\
    \midrule
    Theirs & Frumpy \\
    Yours & Frobbly \\
    Ours & Makes one's heart Frob\\
    \bottomrule
  \end{tabular}
  \caption{Results.   Ours is better.}
  \label{tab:example}
\end{table}
```

## 图表示例代码
```latex
\begin{figure}[t]
  \centering
  \fbox{\rule{0pt}{2in} \rule{0.9\linewidth}{0pt}}
   %\includegraphics[width=0.8\linewidth]{egfigure.eps}

   \caption{Example of caption.
   It is set in Roman so that mathematics (always set in Roman: $B \sin A = A \sin B$) may be included without an ugly clash.}
   \label{fig:onecol}
\end{figure}

\begin{figure*}
  \centering
  \begin{subfigure}{0.68\linewidth}
    \fbox{\rule{0pt}{2in} \rule{.9\linewidth}{0pt}}
    \caption{An example of a subfigure.}
    \label{fig:short-a}
  \end{subfigure}
  \hfill
  \begin{subfigure}{0.28\linewidth}
    \fbox{\rule{0pt}{2in} \rule{.9\linewidth}{0pt}}
    \caption{Another example of a subfigure.}
    \label{fig:short-b}
  \end{subfigure}
  \caption{Example of a short caption, which should be centered.}
  \label{fig:short}
\end{figure*}
```

## 插图、图表和照片
所有图形应居中。
在 \LaTeX 中，避免为此使用 \texttt{center} 环境，因为它会引入可能不需要的空白。
请改用
```latex
{\small\begin{verbatim}
  \centering
\end{verbatim}}
```
置于图的开头。

请确保你希望表达的要点在论文打印稿中清晰可辨。将图中的字体大小调整为与正文一致，并选择在打印时能有效呈现的线宽。

在 \LaTeX 中放置图形时，几乎总是最好使用 \verb+\includegraphics+，并以行宽的倍数指定图形宽度，如下例所示

```latex
{\small\begin{verbatim}
   \usepackage{graphicx} ...
   \includegraphics[width=0.8\linewidth]
                   {myfile.pdf}
\end{verbatim}}
```

## 颜色
如果在图中使用颜色，请记住相当一部分审稿人和读者可能存在色觉缺陷；红绿色盲最为常见。
因此，避免仅依赖颜色作为图中的区分特征（如红线 \vs 绿线），而应增加第二种区分特征以便区分。


## 重要规则
* 不要将 `\usepackage[capitalize]{cleveref}` 改为 `\usepackage[capitalize]{cleverref}`，因为不存在 `cleverref.sty`。
* 保持模板中现有宏包不变。
* 为保证跨环境的一致编译，所有图应放在 `figures` 目录中。务必在 `\includegraphics` 命令中包含 `figures/` 前缀。缺少该前缀（例如使用 `figure_1.png` 而非 `figures/figure_1.png`）将导致构建过程中图片加载错误。
* 撰写时始终使用以下作者信息占位符：
    * Ambitious AI Researcher, AI Research Institute, 123 AI Avenue, ML City, researcher@institute.ai