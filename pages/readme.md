\documentclass[a4paper, 10pt]{article}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{lmodern}
\usepackage[german]{babel}
\usepackage{graphicx}
\usepackage{amsmath,amssymb,amstext}
\usepackage{amssymb}
\usepackage{fullpage}
\usepackage{blindtext}
\usepackage{mathrsfs}
\usepackage{fancyhdr}
\usepackage{amsmath}
\usepackage{acronym}
\usepackage{float}
\usepackage{caption}
\usepackage[onehalfspacing]{setspace}
\newcommand{\diff}{\mathop{}\!\mathrm{d}}
\usepackage[T1]{fontenc}
\usepackage{booktabs}% http://ctan.org/pkg/booktabs
\newcommand{\tabitem}{~~\llap{\textbullet}~~}
\pagestyle{fancy}
\newcommand\ointint{\begingroup \displaystyle \unitlength 1pt \int\mkern-7.2mu \begin{picture}(0,3)
\put(0,3){\oval(10,8)} \end{picture} \mkern-7mu\int\endgroup}
\lhead{}
\chead{}
\rhead{}
\renewcommand{\headrulewidth}{0pt}
\cfoot{\thepage}

\title{Das Klassische N-Körper-Problem}

\begin{document}

\maketitle
\par

\section{Das N-Körper-Problem}
Für die Energieauswertung haben wir N = 100 Teilchen beobachtet. Dabei wurde der Zeitschrittparameter $\eta = 0.05$ verwendet und die Integration bis zur Zeit $t_{end} = 1$ durchgeführt.\\
\\
\begin{figure}[H]
\begin{minipage}{0.5\textwidth}
\includegraphics[width = \textwidth]{E100Euler.png}
\caption{Euler-Integrator}
\end{minipage}
\begin{minipage}{0.5\textwidth}
\includegraphics[width = \textwidth]{E100EulerCromer.png}
\caption{Euler-Cromer-Integrator}
\end{minipage}

\end{figure}

\begin{figure}[H]
\begin{minipage}{0.5\textwidth}
\includegraphics[width = \textwidth]{E100LeapFrog.png}
\caption{Leap-Frog-Integrator}
\end{minipage}
\begin{minipage}{0.5\textwidth}
\includegraphics[width = \textwidth]{E100Verlet.png}
\caption{Verlet-Integrator}
\end{minipage}

\end{figure}

\begin{figure}[H]
\begin{minipage}{0.5\textwidth}
\includegraphics[width = \textwidth]{E100Hermite1.png}
\caption{Hermite-Verfahren}
\end{minipage}
\begin{minipage}{0.5\textwidth}
\includegraphics[width = \textwidth]{E100Hermite2.png}
\caption{zeitumkehrbares Hermite-Verfahren}
\end{minipage}

\end{figure}
\begin{figure}[H]
\begin{minipage}{0.5\textwidth}
\includegraphics[width = \textwidth]{E100Runge2.png}
\caption{Runge-Kutta-Verfahren 2. Ordnung}
\end{minipage}
\begin{minipage}{0.5\textwidth}
\includegraphics[width = \textwidth]{E100Runge4.png}
\caption{Runge-Kutta-Verfahren 4. Ordnung}
\end{minipage}

\end{figure}

\noindent Die Betrachtung der Laufzeit zeigt, dass der Rechenaufwandt exponentiell mit zunehmender Teilchenzahl steigt.\\
\\
Für $\eta = 0.05$ und eine Gesamtzeit von $\pi$ ergeben sich im Vergleich für 2 und 100 Teilchen die folgenden Messwerte:
\begin{center}
\begin{tabular}{lcc}
\textbf{Integrator} & \textbf{Laufzeit für N = 2} & \textbf{Laufzeit für N = 100}\\
Euler & 0.053s & 723s\\
Euler-Cromer & 0.048s & 746s\\
Leap-Frog & 0.094s & 1426s\\
Verlet & 0.056s & 674s\\
Runge-Kutta (2. Ordnung) & 0.012s & 23.5s\\
Runge-Kutta (4. Ordnung) & 0.031s & 34.5s \\
Hermite & 0.052s & 187s\\
Hermite, zeitumkehrbar & 0.040s & 149\\

    \end{tabular}

\end{center}
Hierbei sei angemerkt, dass die Berechungen mit verschiedenen Laptops durchgeführt wurden, sodass es teilweise zu großen Unterschieden in der CPU Zeit kam.
\end{document}
