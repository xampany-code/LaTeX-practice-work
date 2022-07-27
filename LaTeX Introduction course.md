### LaTeX Introduction course
A practical work conducted during the summer internship by 3rd DSBA year student Anna Gertsog.
In this document I will detail my experience of the LaTeX markup language and provide a tutorial for anyone who wants to understand how to work with LaTeX.
#### What is LaTeX?

LaTeX is the collective name for a document preparation system. It includes a set of tools that generate print-ready documents (usually in PDF format) from text files written using a special markup language. TeX itself is the low-level markup and programming language which underpins it.

#### Features
Typically, LaTeX is used to write articles, documents, reports and develop presentations. 
This markup language has a number of advantages:

- It is easy to type mathematical formulas, design graphs, algorithms and other formulas
- Style, fonts, table layout and drawings are consistent throughout the whole document
- It is free and easy to use
- Since the source document simply contains text, you can use software tools to create tables, figures, formulas, etc
- LaTeX encourages authors to write well-structured documents because that's how the software works - by specifying the structure.
- There are already a number of ready-made templates that can be used for documents. For example CVs, schedules, formal letters, presentations, etc.

>For me, the main benefits of Latex are easy to write homework with complex mathematical formulas, user-friendly report writing, and the use of interesting templates for CVs.

#### The initial experience
The initial experience with LaTeX should begin with the development environment 

IDE's:
- [Overleaf]
- [LaTeX project]
- [Texmaker]

I have only mentioned a list of the most popular editors, but there are many more, for example wikipedia has a comparison of different [editors] according to many criteria.

Guides:
- [LaTeX Wikibook]
- [Overleaf guide]
- [Mastering LaTeX in 30 minutes] (in Russian)

>Personally, I used Overleaf, it's free and easy to use in the browser, however you can upgrade for a fee to access other features.

#### Main functions
Initially we must declare the type of document 
| Document type| Description|
| ------ | ------ |
| article | For short documents and journal articles. Is the most commonly used |
| report | For longer documents and dissertations |
| book | Useful to write books|
| letter | For letters |
| slides | For slides, rarely used |
| beamer | Slides in the Beamer class format|
Let's take the article as an example:
```sh
\documentclass{article}
```
First of all, we should create a front page properly with name, name and date:

```sh
\title{LaTeX is the best }
\author{Your name}
\date{01.01.1970}
\maketitle
```
Then, we create a document in which we will add all the necessary components:
```sh
\begin{document}
.
.
.
\end{document}
```

After this, we put all the necessary parts of the document between the 2 lines above. Let us create a new page and table of contents:

```sh
\newpage
\tableofcontents
```
All chapters are added to the table of contents automatically, so there is no need to deal with this function separately.
In LaTeX there are many ways to divide text into parts:
```sh
\part
\chapter
\section
\subsection
\subsubsection
\paragraph
\subparagraph
\subsubparagraph
```
However, I prefer to mainly use the sections. For each section, we simply create:
```sh
\section{LaTeX is the best}
```
Then the section name goes in the table of contents and we get this:
#### LaTeX is the best

In the section we can add any subsections,
```sh
\subsection{...}
```
any text, and different types of formatting can be tried out.

Let's start with text styles, in my opinion, the most important are **bold** and _italics_
we can add them using:
```sh
\textbf{Bold text}
\textit{Italic}
```
Also, some more important things:
```sh
\\ - new line
\indent\setlength{\parindent}{1em} - creates an indent at the front of the line
```
#### List creation

Many different lists can be created in LaTeX, which are also easy to use...
```sh
\begin{enumerate}  
	\item The first item 
	\item The second item 
	\item The third item
\end{enumerate}
```
it will look like
1. The first item
2. The second item
3. The third item

or we can use
```sh
\begin{itemize}[noitemsep]
	\item The first item 
	\item The second item 
	\item The third
\end{itemize}
```
and it will look like

- The first item
- The second item
- The third item

#### Tables
Tables can be created in different ways, it just depends on what you want to make.
Initially, we create a table using this command:
```sh
\begin{tabular}
.
.
.
\end{tabular}
```
In more detail, we start with {c c c} which means that all elements will be formatted in the centre, if we want to shift to the right or left, we use _r_ or _l_ accordingly. 
All elements are separated by columns using the & element, and it is also important to use the newline transition \ \

To divide it into lines, we use:
```sh
\begin{tabular}{c | c | c}
  1 & 2 & 3 \\
  4 & 5 & 6 \\
  7 & 8 & 9 \\
\end{tabular} \\
```
Also, it is possible to color your table
```sh
\rowcolors{1}{blue}{red}
```
It is also equally important if you want to centre your table (or also text, formula and picture), it is worth prescribing in advance:
```
\begin{center}
.
.
.
\begin{center}
```
#### Formulas

Probably the most important part for students and researchers who write articles is the use of formulas.
In my opinion, one of the most useful source is [Wikibox]
The most important symbols:
```sh
\frac{}{} - fraction

\int - integral

\sqrt - square root

\sum_{i=1}^{n} - sum

\[\begin{matrix}
  a & b & c \\
  d & e & f \\
  g & h & i
 \end{matrix}\] - matrix
```
All equations are usually allocated separately using:
```sh
\begin{equation}

\end{equation}
```
if you just want to highlight expressions that use mathematical symbols, then use
```sh
\begin{math}

\end{math}
```
In general, all the formulas you need are learnt as you apply them, you can always use the website I mentioned above and just google the symbols you need.

#### Images
Images are also an indispensable part of any document, when talking about uploading to Overleaf, you should first upload the desired image and then use code to link to the image
```sh
 \includegraphics[width=0.4\linewidth]{images/caracal.jpeg}
```
![](https://g2.delphi.lv/images/pix/676x385/1O2BjvVguG8/caracal-gosha-big-floppa-53258705.jpg)

Here you can see the necessary picture with that cute caracal :З

However, it is possible to adjust the size of the pictures, their location or add several pictures together by splitting them up with the \quad command.

#### References
Let us finish the topic of the article with references
```sh
\begin{thebibliography}{10}
\bibitem I love HSE
\end{thebibliography}
```
We use thebibliography value to automatically create a reference list, {10} - any number can be chosen, the maximum value of the rows we want to add. Using \bibitem we add the necessary book or link, the principle is the same as with lists.

#### Beamer presentation
**Beamer** is a class for LaTeX that allows you to create slides for presentations. Complex mathematical formulas, illustrations and animations can be included. The presentations created can be clearly structured. The structure, as well as the speaker's name and title, can be presented in the margins of the slides.  It is possible to navigate via hyperlinks (the package is included by default) and define buttons for navigating. For definitions, theorems, etc. there are blocks of a certain colour. There is a set of ready-made colour/structure combinations/representations, which are coded with names of animals/cities. Also, as LaTeX has enormous possibilities for writing mathematical formulas, the beamer provides the user with the full power of LaTeX for creating scientific presentations.

To create a Beamer class, as discussed earlier, you need to use a certain command
```sh
\documentclass{beamer}
```
You can also choose from several themes/templates and colours at the start. I liked the Dresden template, however, of much more, you can explore, for example, in this [guide].
```
\usetheme{Dresden}
\usecolortheme{default}
```
![](https://habrastorage.org/r/w1560/getpro/habr/post_images/b09/bdc/df2/b09bdcdf2268971e6365aac99abf23cf.png)
Here, the front page usually has all the basic information about you: title, your name, university, date, etc.
```
\title{LaTeX  practice work}
\subtitle{Beamer presentation}
\author{Anna Gertsog}
\institute[HSE]{Faculty of Computer Science,\\ Data Science and Business Analytics, \\ HSE University}
\date{25 July 2022}
```
You can also add a logo, it will automatically be installed in the bottom right corner and will be on all slides of the presentation.
```
\logo{\includegraphics[height=1.5cm]{images/logo.png}}
```
After that, the principle of filling a presentation is the same as that of an article. You can add any sections, table of contents, however, you should use frames for each slide, it is like subsection in your presentation.
```
\begin{frame}
\frametitle{Table of Contents}
\tableofcontents
\end{frame}
```
The rest remains exactly the same, you can rely on the article guide. Also add formulas, lists, pictures and so on. By the way, I forgot to mention that you can also change the colour of slides, text colour, etc
For instance:
```
\textcolor{red}{Hello!}
```
If you want to colour your sentence red.



#### Conclusion

I have only mentioned the basic LaTeX commands, in fact there are many more if you go deeper into the process. I learned the basic principles of LaTeX during a summer internship - my work included a summary of a textbook on differential equations, in consequence I mostly practiced creating a lot of complex formulas, which is certainly useful for my further studies. It is also worth noting that I practised rewriting my coursework report and creating a Beamer presentation. I believe that such a skill is really useful for students who are at least studying higher mathematics. I hope my article and mini guide will be useful for studying.
Thank you for reading to the end! 




[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

[editors]: https://en.wikipedia.org/wiki/Comparison_of_TeX_editors
[Mastering LaTeX in 30 minutes]: https://habr.com/ru/company/ruvds/blog/574352/
[Overleaf]: https://www.overleaf.com/ 
[LaTeX project]: https://www.latex-project.org/get/ 
[Texmaker]: https://www.xm1math.net/texmaker/
[LaTeX Wikibook]: https://en.wikibooks.org/wiki/Main_Page 
[Overleaf guide]: https://www.overleaf.com/learn 
[Wikibox]: https://ru.wikibooks.org/wiki/Математические_формулы_в_LaTeX
[guide]: https://habr.com/ru/post/145523/