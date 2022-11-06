## Math Review

### Preliminaries

- Taylor's Theorem: for a smooth function $f: \mathbb{R} \to \mathbb{R}$, $\displaystyle f(x)=\sum_{n=0}^N \frac{f^{(n)}(a)}{n!}(x-a)^n + R_N(x)$, where $\displaystyle R_N = \frac{f^{(N+1)}(z)}{(N+1)!}(x-a)^{N+1}$ for some $z$ between $x$ and $a$.
  - (Special case) Maclaurin series: $\displaystyle f(n) = \sum_{n=0}^\infty f^{(n)}(0)\frac{x^n}{n!}$
    - $\displaystyle e^x = \sum_{n=0}^\infty \frac{x^n}{n!} = 1 + \frac{x}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + \ldots$
    - When $x=1$, $\displaystyle e = \sum_{n=0}^\infty \frac{1}{n!} = 1 + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \ldots$
    - When $x=-1$, $\displaystyle \frac{1}{e} = e^{-1} = \sum_{n=0}^\infty \frac{(-1)^n}{n!} = 1 - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \ldots$
  - When $N=0$, $f(x)=f(a) + f'(z)(x-a)$ (Mean Value Theorem)
  - When $N=1$, $f(x)=f(a) + f'(a)x+\frac{f''(z)}{2}(x-a)^2$
- Binomial Theorem: $\displaystyle (x+y)^n=\sum_{k=0}^n \binom{n}{k} x^{n-k} y^k = \sum_{k=0}^n \binom{n}{k} x^{k} y^{n-k}$
- Bernoulli's inequality: $(1+x)^r \geq 1 + rx$ for any $x \geq -1, r\geq 1$.
- Euler's number (Napier's constant): $\displaystyle e=\sum_{n=0}^{\infty}\frac{1}{n!} = \lim_{n\to \infty}\left(1+\frac{1}{n}\right)^n$
  - $\displaystyle \left(1 + \frac{x}{p}\right)^p < e^x < \left(1 + \frac{x}{p}\right)^{p+x/2}$ for all $x, p > 0$.
    - (Special case) $\displaystyle \left(1 + \frac{1}{x}\right)^x < e < \left(1 + \frac{1}{x}\right)^{x+1}$ for all $x > 0$.
    - $\displaystyle \left(1 - \frac{1}{x}\right)^x < \frac{1}{e} < \left(1 - \frac{1}{x}\right)^{x-1}$ for all $x > 1$.

### Exercises

**(1)** Prove Bernoulli's inequality using Taylor's Theorem.
**(2)** Show $1-\left(1-\frac{1}{a}\right)^b \leq \frac{b}{a}$ for $a,b \geq 1$.
**(3)** Show $\left(1 + \frac{x}{p}\right)^p < e^x < \left(1 + \frac{x}{p}\right)^{p+x/2}$ for $x, p > 0$
**(4)** Show $\left(1 - \frac{1}{x}\right)^{x} < \frac{1}{e} < \left(1 - \frac{1}{x}\right)^{x-1}$ for $x > 1$.

----

### Solution to Exercises

**(1)** Let $f(x)=(1+x)^r - 1-rx$. We want to show $f(x) \geq 0$ for any $x \geq -1, r \geq 1$.

When $x=0$ or $r=1$, the equality holds. Otherwise, from Taylor's theorem, there exists $z \in (\min(0,x), \max(0,x))$ such that $
f(x)=f(0) + f'(0)x+\frac{f''(z)}{2}x^2$.

We have:
- $f(0)=0$
- $f'(x) = r(1+x)^{r-1}-r \Longrightarrow f'(0)=0$
- $f''(x) = r(r-1)(1+x)^{r-2}$ as $r \neq 1$.

Then, $f(x)=\frac{r(r-1)}{2}(1+z)^{r-2} x^2$, and 
- $r > 1 \Longrightarrow \frac{r(r-1)}{2}>0$
- $z > -1  \Longrightarrow (1+z)^{r-2}>0$
- $x \neq 0 \Longrightarrow x^2 > 0$.

Finally, we obtain $f(x) > 0$.
(Dragoslav S. Mitrinović. *Analytic Inequalities*. 1970, p.34)

**(2)** By Bernoulli's inequality with $-1 \leq -\frac{1}{a} < 0$, we obtain $\left(1-\frac{1}{a}\right)^b \geq 1-\frac{b}{a}$. Then, $1-\left(1-\frac{1}{a}\right)^b \leq 1-\left(1-\frac{b}{a}\right)=\frac{b}{a}$.

**(3)** For $x=1$ and $n=p \in \mathbb{N}$, we may use Binomial Theorem.
$\displaystyle \left(1 + \frac{1}{n}\right)^n = \sum_{k=0}^n \binom{n}{k} \frac{1}{n^k} = \sum_{k=0}^n \frac{n(n-1)(n-2)\ldots(n-k+1)}{n^k}\cdot \frac{1}{k!} \leq \sum_{k=0}^n \frac{1}{k!} < e$

In general, let $F(p)=\left(1+\frac{x}{p}\right)^p$, $G(p)=\left(1+\frac{x}{p}\right)^{p+x/2}$, $f(p)=\log F(p)$, $g(p) =\log G(p)$.

First, notice the following limits:
- $\displaystyle \lim_{p\to\infty} F(p)=\lim_{t\to\infty}\left(1 + \frac{1}{t}\right)^{tx}= e^x$
- $\displaystyle \lim_{p\to\infty} G(p)=\lim_{p\to\infty}F(p)\left(1+\frac{x}{p}\right)^{x/2}=\lim_{p\to\infty}F(p)\cdot 1=e^x$

It is sufficient to prove that $F$ is an increasing and $G$ is a decreasing function of $p$, both for $p>0$. This is equivalent to the assertion that $f$ is an increasing and $g$ a decreasing function, both for $p>0$.

Let $y(p)=\log\left(1+\frac{x}{p}\right)$. Then,
- $y'(p)=\left[\log(p+x) - \log(p)\right]'=\frac{1}{p+x} - \frac{1}{p}=\frac{-x}{p(p+x)}$
- $y''(p)=\frac{x\left[p(p+x)\right]'}{\left(p(p+x)\right)^2}=\frac{2xp+x^2}{p^2(p+x)^2}$.

By differentiation we get:
- $f'(p)=[p\cdot y(p)]'=p\cdot y'(p)+y(p)$
- $f''(p)=p\cdot y''(p) + y'(p) + y'(p) = \frac{2xp+x^2}{p(p+x)^2} - \frac{2x}{p(p+x)}=\frac{2xp+x^2 - 2xp - 2x^2}{p(p+x)^2} = \frac{- x^2}{p(p+x)^2} < 0$
- $g'(p)=\left[f(p)+ \frac{x}{2}\cdot y(p)\right]'=f'(p) + \frac{x}{2}\cdot y'(p)$
- $g''(p)=f''(p) + \frac{x}{2}\cdot y''(p)=\frac{-x^2}{p(p+x)^2} + \frac{x(2xp+x^2)}{2p^2(p+x)^2}=\frac{-2x^2p +2x^2p + x^3}{2p^2(p+x)^2}=\frac{x^3}{2p^2(p+x)^2} > 0$

Knowing that $\displaystyle \lim_{p\to\infty} f'(p) = \lim_{p\to\infty} g'(p)=0$, we conclude $f'(p)>0$ and $g'(p)<0$. $f$ is increasing and $g$ is decreasing for $p>0$.
(Dragoslav S. Mitrinović. *Analytic Inequalities*. 1970, p.266)

**(4)** This is a direct result of $\left(1 + \frac{1}{x}\right)^x < e < \left(1 + \frac{1}{x}\right)^{x+1}$ for $x>0$.

Since $1+\frac{1}{x}=\frac{x+1}{x}$, we have $\left(\frac{x+1}{x}\right)^x < e < \left(\frac{x+1}{x}\right)^{x+1}
\Longrightarrow \left(\frac{x}{x+1}\right)^x > \frac{1}{e} > \left(\frac{x}{x+1}\right)^{x+1}
\Longrightarrow \left(1-\frac{1}{x+1}\right)^x > \frac{1}{e} > \left(1-\frac{1}{x+1}\right)^{x+1}$.

Then, $\left(1-\frac{1}{x}\right)^{x-1} > \frac{1}{e} > \left(1-\frac{1}{x}\right)^{x}$ for $x>1$.
