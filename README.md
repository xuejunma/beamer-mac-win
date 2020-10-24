# beamer-mac-win

\documentclass[10pt,CJKutf8]{beamer}
\usepackage{CJKutf8}

%%%%%%%%%%R code
\usepackage{fancyvrb}
\fvset{frame=lines,framesep=1mm,fontfamily=courier,
fontsize=\small,numbers=left, framerule=0.5pt, %rulecolor=\color{blue}, %formatcom=\color{red}, fontsize=\scriptsize
numbersep=1mm}
%%%%%%%%%%

%\mode<presentation>
%Berlin, Ilmenau, lined, Malmoe, Montpellier, Singapore, Warsaw, Berkeley, Rochester
% no use  classic, copenhagen, bars,Darmstadt Dresden, Frankfurt,
%\usetheme[secheader]{Madrid}
%\usecolortheme{whale}%seahorse, whale, dolphin, crane, beetle, rose, dove, fly, orchid, albatross, lily
%color setting more or less matching U of A colors

%% lession 
\usetheme{Hannover}%Hannover Montpellier
\usecolortheme{orchid}%% 经典的蓝色黑色 


%\usetheme{CambridgeUS}
%\usetheme{Antibes}
%\usetheme{Madrid}
%\usetheme{Pittsburgh}
%\usetheme{Boadilla}  % report
%\usecolortheme{dove}% no color 
%\usecolortheme{orchid}% 红色字体灰色背景 % beaver wolverine rose seahorse dove wolverine
%\usecolortheme{orchid}%% 经典的蓝色黑色

\begin{document}

\begin{CJK*}{UTF8}{gbsn}

\title[应用回归分析]{第四章：违背基本假设的情况}   % 如果标题不长, [短标题]可以略去


\author[马学俊]{马学俊(主讲)~~杜悦(助教)}%\\[0.5em]
\institute[苏州大学]{苏州大学\\ [0.5em]数学科学学院\vspace{10pt}\\
\url{https://xuejunma.github.io/}}
\date{}


\begin{frame}% 自动目录
  \titlepage
\end{frame}



\begin{frame}

\frametitle{目录}
\tableofcontents

\end{frame}

\section{第一部分}
\subsection{1.1部分}
\begin{frame}{1.1部分}
\begin{alertblock}{定义}
什么是
\end{alertblock}

\begin{exampleblock}{定义}
什么是
\end{exampleblock}

\begin{block}{定义}
什么是
\end{block}

\end{frame}



\subsection{1.2部分}
\begin{frame}
1.2部分
\end{frame}

\begin{frame}{异方差性带来的问题}
当存在异方差时，普通最小二乘估计存在以下问题：
\begin{enumerate}[(1)]
  \item 参数估计值虽是无偏的，但不是最小方差线性无偏估计；
\end{enumerate}
\end{frame}

\section{R code}
\begin{frame}[fragile]
\begin{Verbatim}[label={模拟 R代码}]
> rm(list=ls())
> library(MASS)
> p <- 3; n <- 50
> mu <- rep(0, p)
> sigmu <- diag(rep(1, p))
\end{Verbatim}
\end{frame}

\begin{frame}[fragile]
\begin{Verbatim}[label={模拟 R代码}]
> rm(list=ls())
> library(MASS)
> p <- 3; n <- 50
> mu <- rep(0, p)
> sigmu <- diag(rep(1, p))
\end{Verbatim}
\end{frame}


\begin{frame}[fragile]

\begin{Verbatim}[label={例4.3 R代码}]
> rm(list=ls())
> ex43 <- read.table("ex43.txt", head=TRUE, fileEncoding="utf8")
> attach(ex43)
> head(ex43)
     y     x
1 5081 25669
2 2724 17885
> fit43 <- lm(y~x)
> summary(fit43)

             Estimate Std. Error t value Pr(>|t|)
(Intercept) 1.274e+02  2.744e+02   0.464    0.646
x           1.068e-01  8.573e-03  12.454 3.66e-13 ***

> cor.test(x=x, y =abs(fit43$residuals), method = "spearman")
S = 2100, p-value = 0.0008485
alternative hypothesis: true rho is not equal to 0
sample estimates:
      rho
0.5766129
\end{Verbatim}

\end{frame}


\section{一元加权最小二乘估计}
\subsection{}
\begin{frame}{异方差性的检验}
\begin{itemize}
  \item 残差图分析法
\end{itemize}
\end{frame}


\begin{frame}{异方差性的检验}
\begin{itemize}
  \item 残差图分析法
\end{itemize}
\end{frame}


\end{CJK*}

\end{document}

