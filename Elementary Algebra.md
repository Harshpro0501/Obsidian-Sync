---
tags:
  - Mathematics/Algebra
---
## Theory of Equations 
##### The Polynomial
If $n$ is a positive integer, and $c_{0},c_{1},c_{2},c_{3},\dots,c_{n}$ are complex constants belonging to $\mathbb{C}$ then 
$$
	\boxed{f(x) \equiv c_{0}x^{n}+c_{1}x^{n-1}+c_{2}x^{n-2}+\dots c_{n-1}x+c_{n}= \sum_{k=0}^{n} c_{k}x^{n-k}}
$$
##### The Remainder Theorem
Theorem: 
$$\begin{aligned} 
&\textit{States that if the polynomial $f(x)$ is divided by the linear factor $(x-c)$ until a remainder} \\ & \textit{independent of x is obtained then the remainder is f(c)}
\end{aligned}$$
Proof:
$$
	\begin{aligned}
		&\text{From the polynomial division alogorithm we obtain $f(x)\equiv q(x)g(x)+r(x)$ where f(x) being the} \\
		& \text{polynomial divident, $g(x)$ being the divisor, $q(x)$ being the quotient and $r(x)$ is the remainder} \\ 
		& \text{ }\\
		& \text{When $g(x) = (x-c)$ then we obtain the relation; }\\
		& \text{} \\
		& \text{$f(x)=(x-c)g(x)+r(x)$, clearly the maximum degree of $r(x)$ being $n-1$, therfore $r(x)$ is a constant} \\
		& \text{} \\
		& \text{$\implies$ $ \boxed{f(c) = r}$}
	\end{aligned}
$$
##### The Factor Theorem ( Corollary of Remainder Theorem )
**Theorem:**
$$
	\boxed{\textit{If $f(c)$ is equal to zero then $(x-c)$ is a factor of $f(x)$, in other words $c$ is a root of $f(x)$}}
$$
**Proof:**
$$
	\begin{aligned}
		&\text{From the relation $f(x)=(x-c)g(x)+r(x)$, when r(x) = 0 we obtain $f(x)=(x-c)g(x)$} \\
		&\text{}\\
		&\text{Clearly, $(x-c)$ is a factor of the polynomial}
	\end{aligned}
$$
**Some Results:**
$$
	\boxed{x^{n}-1 = (x-1)\left( \sum_{k=1}^{n}x^{n-k}  \right)}\\

$$
$$\begin{aligned}
	& \text{In the above formula, replacing $x$ by $x/y$ we obtain the relation, the number of terms in the second }\\
	&\text{bracket being $n$}
\end{aligned}
$$
$$
\boxed{x^{n}-y^{n}=(x-y)(x^{n-1}+x^{n-2}y+\dots+xy^{n-2} + y^{n-1})=\sum_{k=0}^{n-1}x^ky^{n-1-k} }
$$
$$
	\begin{aligned}
		&\text{Using this we can obtain the common identities of difference of powers of 2,3,4,5 etc. } \\
		&\text{}\\
	\end{aligned}
$$
$$
	\boxed{x^{3}-y^{3}=(x-y)(x^{2}+xy+y^{2})}
$$
$$
\boxed{x^{4}-y^{4}=(x-1)(x^{3}+x^{2}y+xy^{2}+y^{3})}
$$
$$
	\text{The expression for the sum of a geometric series can be derived from the first result aswell;}
$$
$$
	\text{Let}{~~a,ar,ar^{2},ar^{3},\dots,ar^{n-1}~~}\text{be our given geoemetric progression.}
$$
$$
	S = a+ar+ar^{2}+ar^{3}+\dots+ar^{n-1} = a\sum_{k=0}^{n}r^{n-k} 
$$
$$
\implies \boxed{S = a\Big(\frac{r^{n}-1}{r-1}\Big)}
$$
##### Synthetic  Division 
**Theorem:**
$$
	\begin{aligned}
		&\textit{Synthetic Division is a method to divide any polynomial by a linear factor $(x-c)$}\\
		&\textit{to obtain the value of the polynomial at a value $c$, without computing the value }\\
		&\textit{of $f(c)$ which is tedious.}
	\end{aligned}
$$
$$ 
\begin{aligned}
	&\text{Let $f(x) = \sum_{k=0}^{n}a_{k}x^{n-k}$ being divided by  $(x-c)$.  Let the quotient $q(x) = \sum_{k=0}^{n-1}b_{k}x^{n-1-k}$ }\\
	&\text{From the remainder theorem our polynomial is $(x-c)q(x) + f(c)$~(1)}\\
	&\text{}\\
	&\text{Comparing the coefficients of (1) and $f(x)$ we obtain the following relations:}\\
	&\text{}\\
	&{b_{0}=a_{0}, ~b_{1}=a_{1}+cb_{0},~b_{2}=a_{2}+cb_{1},~ \dots,~ b_{n-1}=a_{n-1}+cb_{n-2} ~\text{ and }r = a_{n}+b_{n-1} = f(c)}
\end{aligned}
	
$$
**Use of the method:**
- We write the coefficients of all powers of $x$ including the missing powers as-well
- Starting from the first coefficient, we bring it down the line, multiply it with the value at which the polynomial is being evaluated. 
- The term is then written below the second coefficient, added and then multiplied with $c$ again, and this process is repeated, until the last term, where we obtain t
he remainder of the polynomial. The coefficients in the row below are of the quotient polynomial.

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


**e.g.** Evaluate $P(x) = x^4 + 3x^3 - 2x - 5$ at $x = 2$.

Since $x^4 = x\cdot x^3 = 2x^3$, the first two terms combine to give $5x^3$. Multiplying $5x^3$ by $2$ and combining with the next term $-2x$ gives further partial sums, until we reach the final value.
$$
P(2) = 1\cdot 2^4 + 3\cdot 2^3 + 0\cdot 2^2 - 2\cdot 2 - 5 = 31
$$
We arrange the coefficients (including a $0$ for the missing $x^2$ term) and carry out the synthetic division against $c = 2$:

```tikz
\begin{document}
\begin{tikzpicture}[x=1.3cm, y=1cm]

\node at (0,0) {$1$};
\node at (1,0) {$3$};
\node at (2,0) {$0$};
\node at (3,0) {$-2$};
\node at (4,0) {$-5$};
\node at (5,0) {$2$};

\node at (1,-0.7) {$2$};
\node at (2,-0.7) {$10$};
\node at (3,-0.7) {$20$};
\node at (4,-0.7) {$36$};

\node at (0,-1.6) {$1$};
\node at (1,-1.6) {$5$};
\node at (2,-1.6) {$10$};
\node at (3,-1.6) {$18$};
\node at (4,-1.6) {$31$};

\draw (-0.5,-1.2) -- (4.5,-1.2);
\draw (4.6,0.4) -- (4.6,-2.0);

\end{tikzpicture}
\end{document}
```

The bottom row (excluding the last entry) gives the coefficients of the quotient, and the last entry is the remainder $P(2)$:
$$
P(x) = (x-2)\big(x^3 + 5x^2 + 10x + 18\big) + 31
$$

##### Factored form of Polynomials
Considering the following polynomial
$$
	f(x) = c_{0}x^{n} + c_{1}x^{n-1} + \dots + c_{n-1}x + c_{n}
$$
If $f(x)= 0$  has a root $\alpha_{1}$ then from the factor theorem it has a factor $(x-\alpha_{1})$, therefore
$$
	\implies f(x) = (x-\alpha_{1})Q(x)~~~~~~~~~~~~~~~~~~~~~~~~
$$
Evidently the degree of $Q(x)$ would be $n-1$.Now suppose $Q(x)=0$ has a root $\alpha_{2}$ then 
$$
	\implies f(x) = (x-\alpha_{1})(x-\alpha_{2})Q_{1}(x)~~~~~~~~~~~~~~
$$
And so on we obtain;
$$
	\implies \boxed{f(x) = c_{0}(x-\alpha_{1})(x-\alpha_{2})\dots(x-\alpha_{n})}~~~~~~~~~~~~~~~(1)
$$
Now this expression has been mechanically deduced from the factor theorem. Deducing some more results;
$$\begin{aligned}
	&\text{Suppose that $f(x)$ of degree $n$ has $n$ distinct roots }{\alpha_{1},\alpha_{2},\alpha_{3}\dots\alpha_{n}}{\text{ then from the factor theorem}}\\
	&\text{If }{Q(x) = 0}\text{ has the root }{\alpha_{2}}\text{ then}\\
	&\text{}\\
	&{\implies f(\alpha_{2})=(\alpha_{2}-\alpha_{1})Q(\alpha_{2})}
	\\&\text{}
	\\&\text{From where }{Q(\alpha_{2}) = 0}\text{ and similarly if }{ \alpha_{3} }\text{ is a root of }{f(x) = 0}\text{ then repeating the same process}
	\\&\text{}
	\\&{\implies f(\alpha_{3})=(\alpha_{3}-\alpha_{2})(\alpha_{3}-\alpha_{1})Q_{1}(\alpha_{3})}
	\\&\text{}
	\\&\text{From where it is easily deducible that }{Q_{1}(\alpha_{3})=0}
	\\&\text{}
	\\&\text{And so on we obtain the original factored form in (1) and our assumptions have been justified}
	
\end{aligned}\\

$$
If $f(x)=0$ had any one more root other than $\alpha_{1},\alpha_{2},\alpha_{3},\dots,\alpha_{n}$ say $\alpha_{n+1}$ then it from the factor theorem it would have another factor in its factor fom, rbut since a it can only have $n$ factors, therefore we prove the theorem that
Theorem:
$$
	\boxed{\textit{Any polynomial $\mathbf{f(x)}$ in $x$ of degree $\mathbf{n}$ can not have more than $\mathbf{n}$ roots for the equation $\mathbf{f(x) = 0}$}}
$$
##### Multiplicity
Any root can occur more than one time in the factored form of a polynomial, the number of occurrence of the root being called its multiplicity
$$
	f(x) = c_{0}(x-\alpha_{1})^{m_{1}}(x-\alpha_{2})^{m_{2}}(x-\alpha_{3})^{m_{3}}\dots(x-\alpha_{k})^{m_{k}}
$$
Here $\alpha_{1}$ is called a root of multiplicity $m_{1}$ of $f(x)=0$, and so on. 
$$m_{1}+m_{2}+m_{3}+\dots+m_{k}=n$$which is pretty obvious. 
The multiplicity is counted when counting the number of roots.

>[!theorem] The fundamental Theorem of Algebra
>
>$$
>	\text{Every polynomial $f(x)$ in $x \in \mathbb{C}$ of degree $n$ has exactly $n$ complex roots (real or imaginary)}
>$$

##### Relation between Roots and Coefficients
Let our polynomial be $f(x) = c_{0}x^{n} + c_{1}x^{n-1} + \dots + c_{n-1}x + c_{n}$
Results:
$$
	\alpha_{1}+\alpha_{2}+\alpha_{3}+\dots+\alpha _{n} = -\frac{c_{1}}{c_{0}}
	
$$
$$
	\alpha_{1}\alpha_{2}+\alpha_{1}\alpha_{3}+\dots+\alpha_{n-1}\alpha_{n} = \frac{c_{2}}{c_{0}}
$$
From this we infer that sum of roots taken $m$ at a time is
$$
	\boxed{\alpha_{1}\alpha_{2}..\alpha _{m}+\dots+\alpha_{1}\alpha_{2}..\alpha_{n-1}\alpha_{n}=\sum_{cyc}^{}\alpha_{i} \alpha_{j}..\alpha_{m} = (-1)^{m}\frac{c_{m}}{c_{0}}}
$$
And finally the product of all roots
$$
	\boxed{\prod_{cyc}^{}\alpha_{i} = (-1)^{n} \frac{c_{n}}{c_{0}}} 
$$
##### Imaginary Roots Occurs in Pairs
Theorem:
$$\begin{aligned}
	&\text{If an algebraic equation $f(x) = 0$ has an imaginary root of the form $a+bi$ then it also has a conjugate}
	\\&\text{root of the form $a-bi~~(b\not=0)$ }\textbf{ provided it has real coefficients}
\end{aligned}
$$
This result comes from the nature of quadratic equations with real coefficients having conjugate pairs of imaginary roots, paired with the factor theorem, we can group a polynomial into linear and quadratic factors. 

Proof:
Let us have an algebraic equation $f(x)=0$ with real coefficients and one root being $a+ib$. Dividing it by the quadratic equation $(x-a+bi)(x+a-bi)$ which has the same imaginary root until we obtain a remainder function $r(x)$ whose whose degree is 1 since $\mathbf{deg~r(x)<deg~g(x)}$
$$
	f(x) = Q(x)\underbrace{ \{(x-a^{2})+b^{2}\} }_{g(x)} + rx + s
$$
Since $f(a+bi)=0$, then
$$
	0 = r(a+bi)+s \implies ra + ibr + s = 0
$$
But since $b\neq 0$ then $r = s = 0$ which means our remainder function $r(x)$ is $0$ hence our polynomial is divisible by the quadratic and hence also having the root $a-bi$
We can recursively apply this result to $Q(x)$, and from this we obtain the corollary:
Corollary:
$$
	\begin{aligned}
		&\text{If an algebraic equation with real coefficients has imaginary root of multiplicity $m$}
		\\&\text{then it also has conjugate root of multiplicity $m$}
	\end{aligned}
$$
And for real polynomials, since the imaginary roots always occur in pairs, any polynomial can be factored into a product of linear factors and irreducible quadratic factors in $\mathbb{R}$. The number of linear factors would be $n-2k$ provided $k$ is the number of independent imaginary roots excluding their conjugate pairs. 

Corollary:
$$
	\begin{aligned}
		\text{Every polynomial of odd degree with real coefficients has }\textbf{atleast one real root}
	\end{aligned}
$$
**Sidenote**: *Every polynomial with rational coefficients, if  the discriminant is real and irrational, then the irrational roots occurs in pairs of the form  $a+\sqrt{ b },a-\sqrt{ b }$*





