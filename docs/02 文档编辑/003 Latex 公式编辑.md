# $\LaTeX$ 公式编辑

> https://www.bilibili.com/video/BV1M54y1x7BJ/

- 插件：Markdown Footnotes
- 插件：$\LaTeX$ Workshop
- Copy Line Down: CTRL + SHIFT + D

## $\LaTeX$ 简介

$\LaTeX$ [^latex] 是一种基于 $\TeX$ [^tex] 文档排版系统，$\LaTeX$ 描述了内容在文档中的布局。与所见即所得的排版工具（如 Word）不同，$\TeX$ 是一种标记语言，$\LaTeX$ 是基于 $\TeX$ 的一系列宏的集合。$\TeX$ 是由 Donald E. Knuth (高德纳) [^knuth] 编写的，$\LaTeX$ 这个名字则是把 $\LaTeX$ 之父 Lamport [^lamport] 的姓和 $\TeX$ 混合得到的。在学术写作，尤其是数学、物理、计算机学界十分流行。

Latex 的完整系统分为：

- TeX Live(Unix/GNU/Linux) [^texlive]
- MacTeX(MacOSX) [^mactex]
- MiKTeX(Windows) [^miktex]

不过，配置起来相对比较复杂，对于论文排版，也可以使用 Overleaf [^overleaf] 来在线编辑，不过在线编辑也有诸多限制，互有优劣。

## 公式编辑

我们在小学一年级的时候就已经知道，$\sqrt{2}$ 是无理数，不能表示成两个整数比的最简形式 $\displaystyle {q \over p}$，其中 $p$ 和 $q$ 是正整数。

证明：

使用反证法，假设 $\sqrt{2}$ 是有理数，则存在互质的正整数 $p, q$，使得 ${q \over p} = \sqrt{2}$，则有：

$$
\begin{aligned}
{q \over p} &= \sqrt{2} \\
{q^2 \over p^2} &= 2 \\
q^2  &= 2 p^2 \\
\end{aligned}
$$

于是，$q^2$ 是偶数，所以 $q$ 也是偶数，设 $q = 2k$，$k$ 是正整数，则：

$$
\begin{aligned}
(2k)^2  &= 2 p^2 \\
4k^2  &= 2 p^2 \\
2k^2  &= p^2 \\
\end{aligned}
$$

于是，$p^2$ 也是偶数，$p, q$ 都是偶数，与假设 $p,q$ 互质矛盾，故假设不成立，证毕。

---

求极限：

$$
\lim_{x \to 0} {(1 + x)^{1 \over x} - (1 + 2x)^{1 \over 2x} \over \sin x}
$$

解：

$$
\begin{aligned}
& \lim_{x \to 0} {(1 + x)^{1 \over x} - (1 + 2x)^{1 \over 2x} \over \sin x} \\
\xlongequal[\sin x \sim x]{x^y = e^{y \ln x}}& \lim_{x \to 0} {
    e^{\ln (1 + x) \over x}
    - 
    e^{\ln (1 + 2x) \over 2x}
\over x} \\
\xlongequal[]{e^x - 1 \sim x}& \lim_{x \to 0} {
    e^{\ln (1 + 2x) \over 2x} \left[
    e^{{\ln (1 + x) \over x} - {\ln (1 + 2x) \over 2x}}
    - 
    1 \right]
\over x} \\
\xlongequal[\ln(1 + x) \sim x]{e^x - 1 \sim x}& e \lim_{x \to 0} {
    {\ln (1 + x) \over x} - {\ln (1 + 2x) \over 2x}
\over x} \\
\xlongequal[]{通分}& e \lim_{x \to 0} {
    \ln (1 + x)^2 - \ln (1 + 2x) \over 2x^2
} \\
\xlongequal[]{}& e \lim_{x \to 0} {
    \ln {(1 + x)^2  \over (1 + 2x)}  \over 2x^2
} \\
\xlongequal[]{\ln(1 + x) \sim x}& e \lim_{x \to 0} {
 {(1 + x)^2  \over (1 + 2x)} - 1  \over 2x^2
} \\
=& e \lim_{x \to 0} {(1 + x)^2 - 1 - 2x  \over (1 + 2x) 2x^2}  \\
=& e \lim_{x \to 0} {x^2 + 2x + 1 - 1 - 2x  \over (1 + 2x) 2x^2}  \\
=& e \lim_{x \to 0} {x^2  \over (1 + 2x) 2x^2}  \\
=& e \lim_{x \to 0} {1  \over (1 + 2x) 2}  \\
=& e \over 2 \\
\end{aligned}
$$

## References

[^latex]: https://www.latex-project.org/
[^tex]: https://www.tug.org/
[^knuth]: https://www-cs-faculty.stanford.edu/~knuth/
[^lamport]: https://www.lamport.org/
[^texlive]: https://www.tug.org/texlive/
[^mactex]: https://www.tug.org/mactex/
[^miktex]: https://miktex.org/
[^overleaf]: https://www.overleaf.com/
