### Basics
Complex numbers $\mathbb{C}$ can be represented in two main ways:
1) $a+bi$ where $a,b\in \mathbb{R}$, and $i=\sqrt{ -1 }$.
2) $re^{i\theta}$, where $r>0$ and $\theta\in \mathbb{R}$. Note that $0$ does not have a representation in this form.
In the second form, one can rewrite $e^{i\theta}=\cos\theta+i\sin\theta$.
This second form allows us to consider also a complex logarithm, for any non-zero $z\in \mathbb{C}$. We define it as 
$$
\log(z)=\log(re^{i\theta}):=\ln(r)+i\theta,
$$
observing that $e^{\log(z)}=z$. Note that for any $\Theta\in (-\pi,\pi]$, $e^{i\theta}=e^{i\Theta}$ whenever $\theta=\Theta+2\pi n$ for some $n\in \mathbb{N}$. This means $\log(z)$ is only a one-way inverse, and it is actually a multi-valued function since the choice of $\theta$ is not unique. As such, one can make it single valued by restricting $\theta$ to $(-\pi,\pi]$, known as the *principal branch*. Other domains for $\theta$ are possible, creating separate branches.



### Differentiability and series representations

We say that a function $f:\mathbb{C}\to \mathbb{C}$ is complex differentiable at a point $z_{0}$ if
$$
f'(z_{0}):=\lim_{ z \to z_{0} } \frac{f(z)-f(z_{0})}{z-z_{0}}
$$
exists (and is finite). Writing $z=a+bi$ then we note that any such function $f=g(a,b)+h(a,b)i$, where $g,h$ are real-valued functions. So the differentiability formula can be rewritten as
$$
\lim_{ a+bi \to a_{0}+b_{0}i } \frac{(g(a,b)-g(a_{0},b_{0}))-(h(a,b)-h(a_{0},b_{0}))i}{(a-a_{0})-(b-b_{0})i}.
$$
For a differentiable function, this formula needs to be path independent. Using this fact, one can deduce the *Cauchy-Riemann equations:*
$$
\frac{dg}{da}=\frac{dh}{db},\qquad -\frac{dg}{db}=\frac{dh}{da},
$$
 which are necessarily satisfied by a differentiable function. **2022 PM2** These equations holding true on some neighborhood around $z_{0}$ is also a sufficient condition for differentiability. If a function $f$ is differentiable on some neighborhood of a point $z_{0}$, it is said to be *analytic* at that point. Equivalently, functions which are analytic at $z_0$ admit local power series representations:
 $$
f(z)=\sum_{k=0}^\infty a_{k}(z-z_{0})^k.
$$
Furthermore, we have the following theorem:
##### Laurent's Theorem:
---
If $f$ is analytic on a domain $R_{1}<|z-z_{0}|<R_{2}$ for $0<R_{1}<R_{2}\in \mathbb{R}$ and $z_0\in\mathbb{C}$, then for each point in this domain, $f$ can be uniquely representation by
$$
f(z)=\sum_{n=-\infty}^\infty c_{n}(z-z_{0})^n,
$$
where, for any simple positively-oriented closed contour (SPOCC) $\Gamma$,
$$
c_{n}=\frac{1}{2\pi i}\int_{\Gamma}\frac{f(z)}{(z-z_{0})^{n+1}}dz.
$$
---
**2023 PM6**
### Integrals and singular points

A point $z_0$ is called a(n) (isolated) *singular point* of a function $f$ if the function is analytic for every point in some neighborhood of $z_0$, but not analytic on $z_0$.

##### Cauchy (Extended) Integral Formula:
---
If $f$ is analytic on some set enclosed by a SPOCC $\Gamma$ and $z_{0}$ is in the interior of this set, then
$$
f^{(n)}(z_{0})=\frac{n!}{2\pi i}\int_{\Gamma}\frac{f(z)}{(z-z_{0})^{n+1}}dz.
$$

##### Cauchy Residue Theorem:
---
If $f$ is analytic everywhere except finitely many singular points $(z_k)_{k=1}^n$ on some set enclosed by a SPOCC $\Gamma$, then
$$
\int_{\Gamma}f(z)dz=2\pi i \sum_{k=1}^n \underset{z=z_{k}}{\operatorname{\mathrm{Res}}}f(z),
$$
 where
 $$
\underset{z=z_{k}}{\operatorname{Res}}f(z):=c_{-1},
$$
(the $-1$-th coefficient of the Laurent series) for an annulus enclosing $z_{k}$ and no other $z_{i}$.

---
Parking garage analogy: taking a loop around a single level of a parking garage is like integrating over an analytic function. Maybe you have some up and downs from speed bumps, but you end up back at the same height you started. Taking a loop up a spiral to the next level is like integrating around a singular point. You end up in the same position but on a higher level (or function value, corresponding to the floor). 

There are three major types of singular points to consider:
- *Essential* singularities, where infinitely many of the coefficients $c_{n}$ are non-zero for $n<0$,
- *Removable* singularities, where every $c_n=0$ for $n<0$ and the pole can be "filled in" with the right value of $f(z_0)$ in order to make the function analytic at $z_0$, and
- *Poles* of order $m\in\mathbb{N}$, where $c_{n}$ may be non-zero only when $n>-m$. 
 
If $f$ has a pole of order $m$ at $z_0$, then
$$
f(z)=\frac{g(z)}{(z-z_{0})^m},
$$
where $g(z)$ is analytic at $z_{0}$. The residue is then:
$$
\underset{z=z_{0}}{\operatorname{Res}}f(z)=\lim_{ z \to z_{0} } \frac{1}{(m-1)!}\frac{d}{dz}\left(f(z)(z-z_{0})^m\right)=\frac{g^{(m-1)}(z_{0})}{(m-1)!}.
$$
##### Theorem:
If $p,q$ are analytic at $z_0$, $p(z_0),q'(z_{0})$ are non-zero, but $q(z_{0})=0$, then $z_{0}$ is a simple pole of $p(z)/q(z)$ and
$$
\underset{z=z_{0}}{\operatorname{Res} }\frac{p(z)}{q(z)}=\frac{p(z_{0})}{q'(z_{0})}.
$$
integrals: **2022 PM9, 2023 PM4**
