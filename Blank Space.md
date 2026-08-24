
```tikz
\begin{document}
\begin{tikzpicture}[x=1.4cm, y=1cm]

\node (a0) at (0,0) {$a_0$};
\node (a1) at (1,0) {$a_1$};
\node (a2) at (2,0) {$a_2$};
\node (adots) at (3,0) {$\cdots$};
\node (an1) at (4,0) {$a_{n-1}$};
\node (an) at (5,0) {$a_n$};
\node (c)  at (6,0) {$c$};

\node (cb0) at (1,-0.7) {$cb_0$};
\node (cb1) at (2,-0.7) {$cb_1$};
\node (cbdots) at (3,-0.7) {$\cdots$};
\node (cbn2) at (4,-0.7) {$cb_{n-2}$};
\node (cbn1) at (5,-0.7) {$cb_{n-1}$};

\node (b0) at (0,-1.6) {$b_0$};
\node (b1) at (1,-1.6) {$b_1$};
\node (b2) at (2,-1.6) {$b_2$};
\node (bdots) at (3,-1.6) {$\cdots$};
\node (bn1) at (4,-1.6) {$b_{n-1}$};
\node (r) at (5,-1.6) {$r$};

\draw (-0.5,-1.2) -- (5.5,-1.2);
\draw (5.6,0.4) -- (5.6,-2.0);

\end{tikzpicture}
\end{document}
```

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
% axes
\draw[->] (-0.3,0) -- (6,0) node[right] {$x$};
\draw[->] (0,-0.3) -- (0,5) node[above] {$f(x)$};

% epsilon band (horizontal, shaded)
\fill[blue!10] (0,2.3) rectangle (6,3.3);
\draw[dashed, blue] (0,2.3) -- (6,2.3);
\draw[dashed, blue] (0,3.3) -- (6,3.3);
\node[blue, left] at (0,3.3) {$L+\varepsilon$};
\node[blue, left] at (0,2.3) {$L-\varepsilon$};
\node[blue, left] at (0,2.8) {$L$};
\draw[dashed, blue] (0,2.8) -- (6,2.8);

% delta band (vertical, shaded)
\fill[orange!15] (2.5,0) rectangle (3.5,5);
\draw[dashed, orange] (2.5,0) -- (2.5,5);
\draw[dashed, orange] (3.5,0) -- (3.5,5);
\node[orange, below] at (2.5,0) {$a-\delta$};
\node[orange, below] at (3.5,0) {$a+\delta$};
\node[below] at (3,0) {$a$};

% the curve
\draw[very thick, domain=0.3:5.7, samples=100, color=red]
  plot (\x, {2.8 + 0.6*sin(2*\x r) + 0.15*(\x-3)});

% point (a, L)
\filldraw[black] (3,2.8) circle (1.2pt);

\end{tikzpicture}
\end{document}
```
