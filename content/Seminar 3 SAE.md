---
tags:
  - SistemeAutomateCuEsantionare
---
## Exercițiul 1

Să se determine ecuaţia cu diferenţe pentru sistemul de ordinul întâi cu funcţia de transfer:

$$G(s)=\frac{K}{s T+1}$$

---

Având în vedere relaţia de definiţie a funcţiei de transfer, rezultă într-o primă etapă:

$$Y(s)=\frac{K}{s T+1} U(s)$$

respectiv:

$$s T Y(s)+Y(s)=U(s)$$

Ecuaţia diferenţială se obţine prin aplicarea transformatei Laplace inverse, folosind proprietatea de derivare a transformatei Laplace, în condiţii iniţiale nule, pentru mărimea de ieşire $Y(s)$ :

$$T \frac{\mathrm{d} y(t)}{\mathrm{d} t}+y(t)=K u(t)$$

Aproximând derivata cu diferenţa de ordinul unu se obţine succesiv:

$$
\begin{align}
&T \frac{y[k]-y[k-1]}{T_{e}}+y[k]=K u[k], \\
&y[k]\left(1+\frac{T}{T_{e}}\right)-\frac{T}{T_{e}} y[k-1]=K u[k], \\
&y[k]-\frac{T}{T_{e}+T} y[k-1]=\frac{K T_{e}}{T_{e}+T} u[k]
\end{align}
$$

respectiv:

$$
y[k]+a_{1} y[k-1]=b_{0} u[k]
$$

unde $a_{1}=-\frac{T}{T_{e}+T}$ şi $b_{0}=\frac{K T_{e}}{T_{e}+T}$.

![](https://youtu.be/YooRJ7pD9Zc?si=XZbEQFJG_yGjaRCS)
## Exercițiul 2

Să se determine funcţia de transfer operaţională pentru elementul de ordinul unu.

---

Ecuaţia cu diferenţe pentru elementul de ordinul unu este :
$$
y[k]+a_{1} y[k-1]=b_{0} u[k]
$$
Folosind operatorul de întârziere cu un pas:
$$y[t-1]=q^{-1} y[k]$$
în această ecuaţie, se obţine:
$$\left(1+a_{1} q^{-1}\right) y[k]=b_{0} u[k]$$

de unde rezultă într-o primă etapă:

$$y[k]=\frac{b_{0}}{1+a_{1} q^{-1}} u[k]$$

deci funcţia de transfer operaţională este:

$$G(q)=\frac{b_{0}}{1+a_{1} q^{-1}}$$
## Exercitiul 3

Se dă sistemul continuu cu funcţia de transfer

$$G(s)=K_{c} \frac{s+a}{s+b}$$cu $\begin{cases}a=1,\\ b=10,\\ K_{c}=10\end{cases}$

Să se determine [[Calculul analitic aproximativ al funcţiilor de transfer z#Calculul analitic aproximativ cu metoda transformatei z care conservă repartiţia poli-zerouri a sistemului continuu|transformata z matched]].

---

- **Pasul 1**: Având în vedere transformarea din s în $z$ a polului şi zeroului într-o primî etapă vom avea$$G(z)=K_{d} \frac{z-\mathrm{e}^{-a T_{e}}}{z-\mathrm{e}^{-b T_{e}}}$$

- **Pasul 2**: nu este necesar în acest caz.

- **Pasul 3** Se calculează factorul de amplificare al funcţiei de transfer $G(z)$ folosind relaţiile succesive $(\alpha=0)$ :
$$
\begin{align}&\lim _{s \rightarrow 0}\{G(s)\}=\lim _{z \rightarrow 1}\{G(z)\}, \lim _{s \rightarrow 0}\left\{K_{c} \frac{s+a}{s+b}\right\} \\&=\lim _{z \rightarrow 1}\left\{K_{d} \frac{z-\mathrm{e}^{-a T_{e}}}{z-\mathrm{e}^{-b T_{e}}}\right\}, \\&K_{c} \frac{a}{b}=K_{d} \frac{1-\mathrm{e}^{-a T_{e}}}{1-\mathrm{e}^{-b T_{e}}}, K_{d}=K_{c} \frac{a}{b} \frac{1-\mathrm{e}^{-b T_{e}}}{1-\mathrm{e}^{-a T_{e}}}\end{align}
$$

În final se obţine funcţia de transfer z matched cu expresia literală:

$$
G_{M a}(z)=K_{c} \frac{a}{b} \frac{1-\mathrm{e}^{-b T_{e}}}{1-\mathrm{e}^{-a T_{e}}} \frac{z-\mathrm{e}^{-a T_{e}}}{z-\mathrm{e}^{-b T_{e}}}
$$

## Exercitiul 4

Se dă sistemul continuu cu funcţia de transfer

$$G(s)=K_{c} \frac{s+a}{s(s+b)}$$ сu $\begin{cases}a=1,\\ b=10,\\ K_{c}=10\end{cases}$

Să se determine [[Calculul analitic aproximativ al funcţiilor de transfer z#Transformata z matched|transformata z matched]].

---
![[Calculul analitic aproximativ al funcţiilor de transfer z#Transformata z matched|transformata z matched]]

---

**Paşii 1 şi 2** furnizează funcţia de transfer z cu expresia:

$$
G(z)=K_{d} \frac{\left(z-\mathrm{e}^{-a T_{e}}\right)(z+1)}{(z-1)\left(z-\mathrm{e}^{-b T_{e}}\right)}
$$

**Pasul 3**: Se calculează factorul de amplificare al funcţiei de transfer $G(z)$ folosind relaţiile succesive $(\alpha=1)$ :

$$
\begin{align}
&\lim _{s \rightarrow 0}\{s G(s)\}=\lim _{z \rightarrow 1}\left\{\frac{z-1}{z T_{e}} G(z)\right\}, \\
& \lim _{s \rightarrow 0}\left\{K_{c} \frac{s+a}{s+b}\right\} =\lim _{z \rightarrow 1}\left\{\frac{z-1}{z T_{e}} K_{d} \frac{\left(z-\mathrm{e}^{-a T_{e}}\right)(z+1)}{(z-1)\left(z-\mathrm{e}^{-b T_{e}}\right)}\right\} \\
& K_{c} \frac{a}{b}=K_{d} \frac{2}{T_{e}} \frac{1-\mathrm{e}^{-a T_{e}}}{1-\mathrm{e}^{-b T_{e}}}, K_{d}=K_{c} \frac{T_{e}}{2} \frac{a}{b} \frac{1-\mathrm{e}^{-b T_{e}}}{1-\mathrm{e}^{-a T_{e}}}
\end{align}
$$

Funcţia de transfer z matched care se obţine are expresia literală

$$
G_{M a}(z)=K_{c} T_{e} \frac{a}{2 b} \frac{1-\mathrm{e}^{-b T_{e}}}{1-\mathrm{e}^{-a T_{e}}} \frac{(z+1)\left(z-\mathrm{e}^{-a T_{e}}\right)}{(z-1)\left(z-\mathrm{e}^{-b T_{e}}\right)}
$$




## Exercițiul 5

Pentru sistemul de ordinul doi cu funcţia de transfer standard

$$
G(s)=\frac{\omega_{n}^{2}}{s^{2}+2 \zeta \omega_{n} s+\omega_{n}^{2}}
$$
având $\omega_{n}=10$ rads $^{-1}$ şi $\zeta=0,5$

să se determine modelele discrete aproximative care rezultă cu metodele de integrare numerică a dreptunghiului înapoi (în spate), a dreptunghiului înainte (în faţă), şi a trapezului ([[Calculul analitic aproximativ al funcţiilor de transfer z]]).

Se adoptă $T_{e}=\frac{\frac{1}{\omega_{n}}}{5}=0.02s$.

---

Se determină funcțiile de transfer z

1. 
$$
\begin{align}&G_{\text {MDS }}(s)=\left.G(s)\right|_{s=\frac{z-1}{z T_{e}}}=\frac{\omega_{n}^{2}}{(z-1)^{2}+2 \omega_{n}(z-1)+\omega_{n}} \\&= \left(\frac{z-1}{z T_{e}}\right)^{2}+2 \zeta \omega_{n}\left(\frac{z-1}{z T_{e}}\right)+\omega_{n}^{2} \\&=\frac{\omega_{n}^{2} T_{e}^{2} z^{2}}{z^{2}\left(1+2 \zeta \omega_{n} T_{e}+\omega_{n}^{2} T_{e}^{2}\right)-z\left(2+2 \zeta \omega_{n} T_{e}\right)+1}=\frac{b_{2} z^{2}}{z^{2}+a_{1} z+a_{0}}\end{align}
$$
unde

$$
\begin{align}
&b_{2}=\frac{\omega_{n}^{2} T_{e}^{2}}{A} ,  \\
&a_{1}=\frac{-2(1+\zeta \omega_{n} T_{e})}{A} , \\
& a_{0}=\frac{1}{A},  \\
&A=1+2 \zeta \omega_{n} T_{e}+\omega_{n}^{2} T_{e}^{2}
\end{align}
$$
2. 

$$
\begin{align}&G_{\mathrm{MDF}}(s)=\left.G(s)\right|_{s=\frac{z-1}{T_{e}}}=\frac{\omega_{n}^{2}}{\left(\frac{z-1}{T_{e}}\right)^{2}+2 \zeta \omega_{n}\left(\frac{z-1}{T_{e}}\right)+\omega_{n}^{2}} \\& =\frac{\omega_{n}^{2} T_{e}^{2}}{z^{2}+2\left(\zeta \omega_{n} T_{e}-1\right) z+1-2 \zeta \omega_{n} T_{e}+\omega_{n}^{2} T_{e}^{2}}=\frac{b_{0}}{z^{2}+a_{1} z+a_{0}}\end{align}
$$
unde 

$$
\begin{aligned}& b_{0}=\omega_{n}^{2} T_{e}^{2},\\&a_{1}=2\left(\zeta \omega_{n} T_{e}-1\right), \\&a_{0}=1-2 \zeta \omega_{n} T_{e}+\omega_{n}^{2} T_{e}^{2}\end{aligned}
$$
3. 

$$
\begin{aligned}
&G_{MDF}(s)=G(s) \bigg{|}_{s= \frac{2}{T_{e}} \frac{z-1}{z+1}}=\frac{\omega_{n}^{2}}{ \frac{(z-1)^{2}}{\frac{T_{e}^{2}}{4}(z+1)^{2}}+2 \zeta \omega_{n} \frac{z-1}{\frac{T_{e}}{2}(z+1)}+\omega_{n}^{2}} \\
&= \frac{\omega_{n}^{2} \frac{T_{e}^{2}}{4}(z+1)^{2}}{(z-1)^{2}-2 \zeta \omega_{n} (z-1)(z+1) \frac{T_{e}}{2} + \omega_{n}^{2} \frac{T_{e}^{2}}{4}(z+1)^{2} } \\ \\
\\& G_{MT}(z)=\frac{\omega_{n}^{2} T_{e}^{2} \frac{z^{2}+2z+1}{4}}{z^{2}\left( 1+ \zeta \omega_{n} T_{e} + \frac{\omega_{n}^{2}T_{e}^{2}}{4} \right)+z\left( \omega_{n}^{2} \frac{T_{e}^{2}}{2}-2 \right)+1-2 \zeta \omega_{n}T_{e}+ \frac{\omega _{n}^{2}T_{e}^{2}}{4}} \\
& = \frac{b_{2}z^{2}+b_{1}z+b_{0}}{z^{2}+a_{1}z+a_{0}}\\ \\
& \text{unde}\\ \\
& b_{2}=\frac{\omega_{n}^{2} T_{e}^{2}}{4A} ,\\ &b_{1}=\frac{\omega_{n}^{2} T_{e}^{2}}{2A} , \\&b_{0}=\frac{\omega_{n}^{2} T_{e}^{2}}{4A} , \\& a_{1}=\frac{\frac{\omega_{n}^{2} T_{e}^{2}}{2} -2}{A} ,\\& a_{0}= \frac{1-2 \zeta \omega_{n} T_{e}+\frac{\omega_{n}^{2} T_{e}^{2}}{4} }{A},\\& A=1+2 \zeta \omega_{n} T_{e}+\frac{\omega_{n}^{2} T_{e}^{2} }{4}\end{aligned}
$$ 