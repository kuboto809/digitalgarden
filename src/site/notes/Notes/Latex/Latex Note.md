---
{"dg-publish":true,"permalink":"/Notes/Latex/Latex Note/"}
---

# Common notations
## Superscript 
`{base} ^ {power}`
E.g.: `x^3`
In default, only one digit after `^` will be put onto the power, so if u want more than one digit on ur power, put them in the curly bracket like this: `$$2x^{3x+4}$$`
## Subscript
`{base} _ {index}`
E.g.: `x_1`
More than one dight: `{base} _ {index}`
If u want more than one layer of subscript,  put every layer in a new curly bracket E. g.:  `{x} _ {1_{2_3}}`
It looks like: $${x}_{1_{2_3}}$$
## Greek letters
`\{its name}`
E.g.: `\pi`   $\pi$
If u want capital letter, start with the uppercase letter.
E.g.: `\Pi`   $\Pi$
Leave a space after `\{letter} ` otherwise we get an error.
## Trig functions
### Basic
`\{function's name} `
E.g.: `\sin x` $\sin x$
		`\sec \theta ` $\sec \theta$ 
Note that it doesn't treat "sin" as characters and make them italic anymore.
### Inverse Trig functions
Write -1 as superscript:
`\sin^{-1} \theta`                   $\sin ^ {-1} \theta$
Or "arc-"
`\arcsin \theta`                        $\arcsin \theta$
## Log functions
`\log {expression}`     
`\log x`                           $\log x$
`log_{base} {expression}`           $\log_{3x+5} 4x+2$
`\ln {x+5}`                      $\ln {x+5}$
## Roots
`\sqrt[power]{expression}` (the default power is 2 if u leave it blank)
`\sqrt[3]{3x+5} `               $\sqrt[3]{3x+5}$

## Fractions
`\frac{numerator}{denominator}`
`\frac{2x+3}{5x+4}`            $\frac{2x+3}{5x+4}$   
Or a simpler style:
`(   {numerator}  )  \ (   {denominator}   )`    $({ax+b})/({cx+d})$

## Brackets
###  Normal brackets and square brackets
Just type it as usual.
`(a) \\ [a]`   $(a)  [a]$
### Curly brackets and dollar sign
Since it is a symbol reserved in Latex, we need to type `\` in front of each one of the curly bracket.
`\{a + b + c \}`           $\{a + b + c \}$
The logic goes the same for the dollar sign `$`, we need to put a `\` in front of it. Otherwise it thinks we are starting a math expression.
`\$13.53`                $\$13.53$
### Angular brackets
`\langle    \rangle`      $\langle   3, 5 \rangle$
### Make brackets fit
When brackets are not "tall" enough, type `\left` and `\right` in front of the left and right bracket respectively.
E.g. `2  \left(   \frac{1}{2x+3}    \right)`  $$2 \left( \frac{1}{2x+3} \right)$$
Compared to `2   (    \frac{1}{2x+3}    )` $$2 (\frac{1}{2x+3})$$
The same also applies to square brackets, curly brackets and other "bracket-like" notation, such as absolute value.
#### When \\left and \\right are not paired
Sometimes u want to use \\right only, like in Calculus we want to write a vertical bar indicating that we are subsituting numbers.
If we write `\frac{dy}{dx} \right|_{x=1}`, we get an error because there isn't a `\left` to match the `\right`.
To solve this, we still need to write `\left`, but we put a period `.`  after it to hide its effect.
`\left. \frac{dy}{dx} \right|_{x=1}`  $\left. \frac{dy}{dx} \right|_{x=1}$


# Not-so-common notations
## 1. Lower dots
`\dots` $\ldots$
## 2. Limit
`\lim`            $\\lim$
`\lim_{x \to a}`       $\lim_{x \to a}$
`\lim \limits_{x \to a^-} f(x)`     $\lim \limits_{x \to a^-} f(x)$
The `\limits_{ }` thing puts stuff under a notation
## 3. Integral
`\int    \sin x \,    \mathrm{d}x`     $\int \sin x \,\mathrm{d}x$
`\int    \limits_   {3x+5}  ^  {\phi(x)}    f(x) \,   \mathrm{d}x`  $\int \limits_    {3x+5}  ^   {\phi(x)} f(x) \, \mathrm{d}x$
`[a+b]_    {\phi(x)} ^ {\Phi()}   `                           $\displaystyle{\left[a+b   \right]_    {\phi(x)} ^ {\Phi(x)}}$
`\sum \limits_ {n=1} ^ {\infty} ar^n = a + ar + ar^2 + \cdots + ar^n`      $\sum \limits_ {n=1} ^ {\infty} ar^n = a + ar + ar^2 + \cdots + ar^n$
`\sum_{n=1}^{\infty}{T(n)`                     $\sum_{n=1}^{\infty}{T(n)}$

## 4. Vectors
`\vec {v_1}`       $\vec {v}_{1}$

# Tables
- Type  `\begin{tabular}    \end{tabular}` to start a table
- Type `{lllccccrrrr}` immediately after `{tabular}` to make columns. `l` , `c`, `r`  represents the alignment of the elements in the table cells. L means align to the left; c, center; r, right. Type `p{width}` to indicate that u want a paragraph in a table celll, and u can adjust the width of the column using the `width` parameter.
- Use `&` to indicate the border of each cell
- The number of  `l` or `c` or `r` indicates the number of columns u make
- Write `|` between the columns to make vertical lines
- Write \\\\ to start a new row
- Write \hline after \\\\ to draw a horizontal line
### Example
```
$$
\begin{tabular}{|c||c|l|l|r|r|} \hline
$x$ & 3 & 4 & 6 & 7 \\ \hline
$f(x)$ & 2 & 4 &7 &5\\ \hline
\end{tabular}
$$
```

And we get this:
![Pasted image 20231113114734.png](/img/user/Notes/Latex/Pasted%20image%2020231113114734.png)

- Use `\vspace{distance}` to enlarge the distance as usual  (v stands for vertical)
### More settings
Type `\begin{table} \end{table}` to surround the `\begin{tabular}  \end{tabular}` so that we can play around with the table settings.
Type `\begin{table}[H]` to fix the position of the table. Otherwise it will be moved to where the compiler thinks it fits the best. It requires `float` package. (It works for other stuff as well, like figures)
Type `\def\arraystretch[distance]` in between ` \begin{table}`   and   `\begin{tabular}` to adjust the row height. Also, type `\centering`  in the same position to center ur table.
Type `\caption{text}` at where u want to make captions for ur table.


# Equation arrays
Type `\begin{align} \end{align}` to start an array. Note that everything in it will be in math mode.
Then u can start writing ur eqns in it. Note each eqn is numbered. If u don't want it, type `{align*}` instead of `{align}` at the begining and at the end.
To start a new line, write `\\` as usual. `
To align the eqns with respect to the equal sign "=", type `&` in front of the "=".
### Example
```
\begin{align*}
3x + 4  &= 8\\[10pt]
2x + 65525  &= 92525
\end{align*}
```

![Pasted image 20231113122049.png](/img/user/Notes/Latex/Pasted%20image%2020231113122049.png)
# Lists
Type `\begin{enumerate} \end{enumerate}` to start a list with number order.
For each item in the list, type `\item` in front of it. If u don't want the index to show, type `[]` after `\item`. Or if u want other customized index, type it in `[]`.
### Example
```
\begin{enumerate}
    \item apple
    \item banana
    \item orange
\end{enumerate}
```

![Pasted image 20231113122204.png](/img/user/Notes/Latex/Pasted%20image%2020231113122204.png)

Type `\begin{itemize} \end{itemize}` instead to make a bullet point list. 
![Pasted image 20231113122320.png](/img/user/Notes/Latex/Pasted%20image%2020231113122320.png)
Type `\begin{enumerate} \end{enumerate}` after an item to make a sub list under the item.
```
\begin{enumerate}
\item apple
\item banana
\item orange
	\begin{enumerate}
	\item seed
	\item skin
	\item core
		\begin{enumerate}
		\item skin of core
		\item core of core
		\end{enumerate}
     \end{enumerate}
\end{enumerate}
```


![Pasted image 20231113122732.png](/img/user/Notes/Latex/Pasted%20image%2020231113122732.png)

- Type ` [A.] ` or other immediately after ` \begin{enumerate} `  to adjust the index
- If u don't want it to start counting from 1, type `\setcounter{enumi}{the starting number you want -1}`

# Formatting formula
## \\displaystyle
It makes inline math expressions as big as those in `$$  $$`. Also, it starts a new line.
`\displaystyle \frac{2}{3}`  An apple is  $\displaystyle \frac{2}{3}$  an orange.
`displaystyle{\int \sin x \, \mathrm{d}x}`   $\displaystyle{\int \sin x \, \mathrm{d}x}$

## Starting new line \\
Write `\\[distance]` to start a new line with the distance to the above line as specified. Note that we need to enter the unit of the distance.
`\\[6pt]`
## Write texts in math mode
Type `\text{ur text}`
## Space in math mode
Since spaces get ignored in math mode, we need commands to make space.
`\,` -- a small space. If u want more spaces, type it more times.
# Formatting text
- Italic text
	`\textit{the text u want to italic}`
- Bold text	
	`\textbf{the text}` (bf stands for bold face)	
- Capticalize
	`\textsc{the text}` (sc stands for  small caps)
- Typewriter font
	`\texttt{the text}`	(just to make the text stands out)
- Url
	The package used: `hyperref`
	`\url{the link}` to make a link clickable
	`\href{the link}{the display text}` to make a clickable link but is shown as the the text u want
- Adjust text size
	`\begin{Huge}    the text    \end{Huge}` to enlarge the text (Lowercase h will enlarge it but not as large as capital h)
	`{Large}` `{normalsize}`	`{sriptsize}` `{tiny}`    big ---> small
- Adjust text position
	`\begin{center}` to center the text
	`{flushleft}` `{flushright}`
	`\centering` will affect everything after it
- Make text not italic
	`\mathrm{the text}` to make the text not italic (like the d in the  differential operator d/dx)


# Formatting page
## Title, author and date
- Type the following before `\begin{document}`
	Title: `\title{the title u want}`
	Author: `\author{the author's name} `
	Date: `\date{u type it}` (e.g. 26 July 2020) or u can put in `\today` to make it grab the current date each time u compile
To make it actually show up on ur document, u need to type `\maketitle` after `\begin{document}`
- `\documentclass[font size, papaer size]{article}`
## Table of content
`\table of content` to generate the table of content
## Section
`\section{section name}` to make a new section.
Under it, type `\subsection{section name}` to make a subsection.
`\subsubsection{section name}` to make a sub sub section.
If u don't want the numbers to show up, type `*` after the word `section` or `subsection`
## Page number
- Delete page number 
	`\pagestyle{empty}`
## Paragraph indent
Modify how much u want to indent when u start a new paragraph.
`\parindent [size]`
The size can be `0px` or so.
## Page break
Type  `\pagebreak` to break pages
# Packages
Load the packages in the preamble section (i.e. the lines after `\documentclass[11pt]{article}` and before `\begin{}`)
`\usepackages{   package1, package2, ...  }`
## Common packages
`{fullpage}`: narrow the margin of the document
`{geometry}`: set margins
	E.g.: `\usepackage[top = 1in, bottom = 1in, right = 0.5cm, left = 0.2pt]{geometry}`
`{amsfonts} {amsmath} {amssymb}` 
	`\mathbb{R}`: the real number notation
`{graphicx}`: insert graphic in ur document
	`\includegraphics[scale = aNumberYouChoose]{file name}`
		Or u can specify the width and height instead of changing the scale:  replace the `[scale]` with  `[width = numberAndUnit, height = numberAndUnit]` or `[width = aNumberBetweenZeroAndOne\textwidth]` e.g. `[width = 0.5\textwidth]`
# Macro
`\def what u type to call it {the content}`
E.g. Put  `\def\eq1{y = 3x + 2}` in the preamble section. In the document whenever u want to type "y = 3x + 2", u can type `$\eq1$`. Note that we better not include the dollar sign in the `{the content}` cuz we may want to call it not as a math expression. But make sure to add the dollar sign if we want it to display in math mode.
# Command
 