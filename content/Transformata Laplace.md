---
tags:
  - TeoriaSistemelor
---

^df8847

Transformata Laplace este o metoda de calcul operationala care poate fi folosita in mod avantajos pentru calculul ecuatiilor diferentiale si modelarea sistemelor dinamice.

>[!note] 
>Transformata Laplace este folosita pentru a transforma functii de timp in functii de frecventa.

Folosind transformata Laplace funcţiile de timp vor fi convertite in funcţii algebrice de variabilă complexă $s$, şi operaţiile de derivare si integrare vor fi transformate in operaţii algebrice. Astfel ecuaţiile diferenţiale se transformă in ecuaţii algebrice de variabilă $s$.

![[Pasted image 20221018184413.png]]

![](https://youtu.be/n2y7n6jw5d0?si=3v-deM28rMJ64j2S)
## Definitia transformatei laplace directe

Fie o funcţie de timp $f (t)$ definită pentru $t \geq 0$ (se consideră că $f ( t ) = 0$ pentru $t < 0$) şi o variabilă complexă $s=\sigma+j \omega$. Prin definiţie transformata Laplace (unilaterală) a funcţiei $f (t )$ este:

$$
F(s)=\mathrm{L}\{f(t)\}=\int_0^{\infty} e^{-s t} \mathrm{~d} t[f(t)]=\int_0^{\infty} f(t) e^{-s t} \mathrm{~d} t
$$

unde $L$ este simbolul operaţional care specifică operatorul integral cu nucleul $e^{-st}$.Procesul invers de determinare a funcţiei de timp $f (t )$ din transformata Laplace $F(s)$ se numeşte **transformată Laplace inversă** $(TLI)$. Notaţia simbolică pentru $TLI$ este

$$f(t)=L^{-1}\{F(s)\}$$

## Proprietăţile şi teoremele transformatei laplace

Calculul transformatelor Laplace se poate simplifica in mod considerabil prin utilizarea unor proprietăţi cu caracter general si al unor teoreme.

|     | Denumire proprietate sau teorema                        | Relatii:                                                                                                                                                                                                                                                                           |
| --- | ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1.  | Liniaritate (superpozitie)                              | $$\begin{align}&\mathcal{L}\{Af(t)\}=AF(s) \\&\mathcal{L}\{f_{1}(t)\pm f_{2}(t)\}=F_{1}(s)\pm F_{2}(s)\end{align}$$                                                                                                                                                                |
| 2.  | Deplasare (intarziere) in timp                          | $$\mathcal{L}\{f(t-\tau)1_{+}(t-\tau)\}=\mathcal{L}\{f(t-\tau)\}=e^{s\tau}F(s),\tau \geq 0$$                                                                                                                                                                                       |
| 3.  | Deplasarea in complex                                   | $$\mathcal{L}\{f(t)e^{-at}\}=F(s) \big\|_{s=s+a}=F(s+a)$$                                                                                                                                                                                                                          |
| 4.  | Schimbare (scalare) a scarii timpului                   | $$\mathcal{L}\left\{ f\left( \frac{t}{a} \right)=\|a\|F(as), \text{ sau }\mathcal{L} \{f(at)\}=\frac{1}{\|a\|}F\left( \frac{s}{a} \right)\right\}$$                                                                                                                                |
| 5.  | Proprietatea produsului de convolutie                   | $$\mathcal{L}\{f_{1}(t) \cdot f_{2}(t)\}=\mathcal{L} \{\int _{-\infty}^{\infty}f_{1}(\theta) f_{2}(t-\theta) \, d\theta\}=F_{1}(s)F_{2}(s)$$                                                                                                                                       |
| 6.  | Teorema TL pentru derivatele functiilor de timp         | $$\begin{align}& \mathcal{L}\left\{ \frac{d}{dt}f(t) \right\}=sF(s)-f(0) \\& \mathcal{L}\left\{ \frac{d^{2}f(t)}{dt^{2}} \right\}=\mathcal{L}\{f^{2}(t)\}=s^{2}F(s)-sf(0)-f^{1}(0) \\& \mathcal{L}\{f^{n}(t)\}=s^{n}F(s)-s^{n-1}f(0)-s^{n-2}f^{1}(0)-\dots-f^{n-1}(0)\end{align}$$ |
| 7.  | Teorema TL pentru integrala functiilor de timp          | $$\mathcal{L}\left\{ \int _{0}^{\infty} f(\tau)\, d\tau \right\}=\frac{F(s)}{s}$$                                                                                                                                                                                                  |
| 8.  | Teorema TL pentru derivatele functiilor complexe $F(s)$ | $$\begin{align}& \mathcal{L}\{tf(t)\}=-\frac{d}{ds}F(s) \\& \mathcal{L}\{t^{2}f(t)\}=\frac{d^{2}}{ds^{2}}F(s) \\& \mathcal{L}\{t^{n}f(t)\}=(-1)^{n} \frac{d^{n}}{ds^{n}}F(s), \space n=1,2,3,\dots\end{align}$$                                                                    |
| 9.  | Teorema valorii finale                                  | $$\lim_{ t \to \infty } f(t)=\lim_{ s \to 0 }sF(s) $$                                                                                                                                                                                                                              |
| 10. | Teorema valorii initiale                                | $$\lim_{ t \to 0 }f(t)=\lim_{ s \to \infty }sF(s)  $$                                                                                                                                                                                                                              |

## Proprietatea transformatei laplace în raport cu produsul de convoluţie

Produsul de convoluţie reprezintă o noţiune cu multiple aplicaţii în tehnicile moderne de analiză a sistemelor. Considerând funcţiile de timp $f_1(t)$ şi $f_2(t)$ existente pentru $t \geq 0$, prin definiţie, produsul de convoluţie este exprimat conform relaţiei integrale

$$
f_1(t) * f_2(t)=\int_{-\infty}^{\infty} f_1(\tau) f_2(t-\tau) \mathrm{d} \tau
$$

Deoarece $f_1(t)=0$ şi $f_2(t)=0$, pentru $t<0$, rezultă relaţia de definiţie echivalentă a produsului de convoluţie:

$$
f_1(t) * f_2(t)=\int_0^t f_1(\tau) f_2(t-\tau) \mathrm{d} \tau \text {. }
$$

Produsul de convoluţie este comutativ iar funcţia element neutru în raport cu operatia produs de convoluţie este impulsul unitar

Proprietatea transformatei Laplace legată de produsul de convoluţie este exprimată prin relatia:

$$\mathrm{L}\left\{f_1(t) * f_2(t)\right\}=\mathbf{L}\left\{\int_{-\infty}^{\infty} f_1(\tau) f_2(t-\tau) \mathrm{d} \tau\right\}=F_1(s) F_2(s)$$

unde $F_1(s)=\mathbf{L}\left\{f_1(t)\right\}$ şi $F_2(s)=\mathbf{L}\left\{f_2(t)\right\}$.

| $f(t)$             | $F(s)$                           |
| ------------------ | -------------------------------- |
| $$A1_+(t)$$        | $$A\frac{1}{s}$$                 |
| $$Ae^{-at}$$       | $$\frac{A}{s+a}$$                |
| $$At$$             | $$\frac{A}{s^2}$$                |
| $$\delta(t)$$      | $$1$$                            |
| $$A\sin \omega t$$ | $$\frac{A\omega}{s^2+\omega^2}$$ |
| $$A\cos \omega t$$ | $$\frac{As}{s^2+\omega^2}$$      |

### Transformata laplace pentru semnalul treapta

$$
1_+(t)=\begin{cases}
			1, & t\geq0\\
            0, & t<0
		 \end{cases}
$$

$$F(s)=L\{1_+(t)\}=\int_0^\infty Ae^{-st}dt=\frac{Ae^{-st}}{-s}\bigg\vert_0^\infty=\frac{A}{s}$$

### Transformata laplace pentru semanlul exponential
$$
f(t)=\begin{cases}
			Ae^{-at}, & t\geq0\\
            0, & t<0
		 \end{cases}
$$

$$F(s)=L\{1_+(t)\}=\int_0^\infty Ae^{-at}e^{-nt}dt=A\int_0^\infty e^{t(s+a)}dt=A\frac{e^{-t(s+a)}}{-(s+a)}\bigg\vert_0^{\infty}=\frac{A}{s+a}$$

### Transformata laplace pentru semnalul rampa unitara

$$f(t)=\begin{cases}t, &&t\geq0 \\ 0, &&t<0 \end{cases}$$

$$F(s)=L\{f(t)\}=\int_0^\infty A t e^{-st}dt=At\frac{e^{-st}}{-s}\bigg\vert_0^\infty+A\int_0^\infty\frac{e^{-st}}{s}dt=\frac{A}{s}\int_0^{\infty}e^{-st}dt=\frac{A}{s^2}$$

### Transformata laplace pentru semnalul sinusoidal

$$f(t)=\begin{cases}A\sin\omega t,&&t\ge0\\0,&&t<0\end{cases}$$

$$\sin\omega t=\frac{e^{j\omega t}-e^{-j\omega t}}{2}$$

$$F(s)=L\{f(t)\}=\int_0^\infty\frac{A}{2j}(e^{j\omega t}-e^{-j\omega t})e^{-st}dt=\frac{A}{2j}\int_0^\infty e^{-t(s-j\omega)}dt-\frac{A}{2j}\int_0^\infty e^{-t(s+j\omega)}dt=\ldots=\frac{A\omega}{s^2+\omega^2}$$

## Transformarea laplace inversa

^38a8cb

^883856

### Definitie

Este produsul invers de trecere dintr-o functie de variabila $s$ intr-o functie de variabila $t$

$$f(t)=\frac{1}{2\pi j} \int^{C+j \omega}_{C-j \omega}F(s)e^{st}dt$$

Unde:

- $C$- constanta reala care se alege astfel incat sa fie mai mare decat partea reala a tuturor radacinilor, polinoamelor din $F(s)$

### Metode de evaluare

Evaluarea cu metoda formulei de inversiune este impractica. Exista metode mai simple care permit determinarea functiei $f(t)$ din $F(s)$ fara a fi necesara calculul formulei de inversiune. Aceste metode pornesc de la faptul ca majoritatea semnalelor fizice au transformata Laplace exprimata sub forma unei functii rationale de variabila complexa $S$.

$$
\begin{align}
&L(a_0 \frac{d^ny(t)}{dt^n}+a_1 \frac{d^{n-1}y(t)}{dt^{n-1}}+ \ldots+a_ny(t))= \\
&b_0 \frac{d^mu(t)}{dt^m}+b_1 \frac{d^{m-1}u(t)}{dt^{m-1}}+\ldots+b_mu(t)
\end{align}
$$

![[Pasted image 20221029144929.png]]

### Metode
#### Cand $F(s)$ are poli distincti
##### Metoda cover-up

$$
\begin{align}
& A(s)=\underbrace{a_{0}}_{-p_{1}}s^{n}+\underbrace{a_{1}}_{-p_{2}}s^{n-1}+\dots+\underbrace{a_{n}}_{-p_{n}}=(s+p_{1})=(s+p_{1})(s+p_{2})\dots(s+p_{n}) \\
& s^{2}+3s+2=(s+1)(s+2) \\
& \implies F(s)=\frac{B(s)}{(s+p_{1})(s+p_{2})\dots(s+p_{n})} \\
& F(s)=\frac{c_{1}}{s+p_{1}}+\frac{c_{2}}{s+p_{2}}+\dots+\frac{c_{i}}{s+p_{i}}+\dots+\frac{c_{n}}{s+p_{n}} \bigg| \cdot(s+p_{i}) \\
&\implies (s+p_{i})F(s)=\underbrace{\frac{c_{1}(s+p_{i})}{s+p_{1}}}_{=0}+\underbrace{\frac{c_{2}(s+p_{i})}{s+p_{2}}}_{=0}+\dots+0+\dots \underbrace{\frac{c_{n}(s+p_{i})}{s+p_{n}}}_{=0}\bigg|_{s=-pi} \\
&s+pi=0\implies s=-pi \\
& C_{i}=(s+pi)F(0)|_{s=-pi} \\
& f(t)=C_{1}e^{-p_{1}t}+C_{2}e^{-p_{2}t}+\dots+C_{m}e^{-p_{m}t}, t\geq 0
\end{align}
$$

Exemplu:

$$
\begin{align}
&F(s)=\frac{3}{(s+1)(s+2)}=\frac{C_{1}}{s+1}+\frac{C_{2}}{s+2}\bigg| \cdot (s+1) \\
& f(t)=C_{1}e^{-t}+C_{2}e^{-2t} \\
& F(s)(s+1)=\frac{C_{1}\cancel{(s+1)}}{\cancel{(s+1)}}+ \underbrace{\frac{C_{2}(s+1)}{s+2}}_{=0}\bigg|_{s=-1} \\
&C_{1}=F(s)(s+1)\bigg|_{s=-1}=\frac{3}{\cancel{(s+1)}(s+2)}\cancel{(s+1)}\bigg|_{s=-1}=3 \\
& C_{2}= F(s)(s+2)\bigg|_{s=-2}=\frac{3}{(s+1)\cancel{(s+2)}}\cancel{(s+2)}\bigg|_{s=-2}=-3
\end{align}
$$






### Descompunerea in fractii simple in cazul radacinilor complexe simple

![[Pasted image 20221029145218.png]]

### Descompunerea in fractii simple in cazul radacinilor reale multiple

![[Pasted image 20221029145303.png]]

## Proprietatile si teoremele transformarii laplace

^518c4b

$$L\{f_1(t)\}=F_1(s)$$

$$L\{f_2(t)\}=F_2(s)$$

### Liniaritate

$$L\{Af(t)\}=AF(s)$$

$$L\{f_1(t)\pm f_2(t)\}=F_1(s)\pm F_2(s)$$

### Deplasarea in timp

$$F(s)=L\{f(t)1_+(t)\}$$

$$F(s)=L\{f(t-\tau)1_+(t-\tau)\}=e^{-s\tau}F(s)$$

![[Pasted image 20221018202233.png]]

### Deplasarea in complex

$$F(s)=L\{f(t)e^{(-at)}\}=F(s)\bigg\vert_{s=s+a}=F(s+a)$$

### Proprietatea produsului de convolutie

$$L\{f_1(t)*f_2(t)\}=L\{\int^{\infty}_{0}f_1(\tau)f_2(t-\tau)\}=F_1(s)F_2(s)$$

### Teorema transformarii laplace pentru derivatele functiilor de timp

$$L\{\frac{df(t)}{dt}\}=sF(s)-f(0)$$

$$L\{\frac{d^2f(t)}{dt^2}\}=s^2F(s)-sf(0)-f^{(1)}(0)$$

$$L\{\frac{d^nf(t)}{dt^n}\}=s^nF(s)-s^{n-1}f(a)-s^{n-2}f^{(1)}(0)-\ldots$$

### Teorema transformarii laplace pentru integrala functiilor de timp

$$L\{\int^{\infty}_{0}f(\tau)d \tau\}=\frac{F(s)}{s}$$

### Teorema transformarii laplace pentru integrala functiilor complexe

$$d\{tf(t)\}-\frac{d}{ds}F(s)$$

$$L\{t^2f(t)\}=\frac{d^2F(s)}{ds^2}$$

$$L\{t^nf(t)\}=(-1)^n \frac{d^nF(s)}{ds^n}$$

### Teorema valorii finale

$$s=\tau t j \omega$$

$$\lim_{t \to \infty}f(t)=\lim_{s \to 0}sF(s)=f(t)$$

Se poate aplica doar daca polii functiei $sF(s)$ se afla in semiplanul stang al planului $s$

![[Pasted image 20221029143101.png]]

## Transformata laplace

Fie semnalul continuu $x(t)$ definit pentru $t \geq 0$ cu $x(t)=0$ pentru $t<0$. Semnalul considerat are un mumăr finit de discontinuităţi şi este mărginit în sens exponenţial, adică:

$$

|x(t)|<M e^{a t}, M, a \in \boldsymbol{R}^{+} \text {. }

$$

Prin definiţie transformata Laplace unilaterală a semnalului $x(t)$, denumit original, este expresia integrală

$$

X(s)=\int_{0}^{\infty} x(t) e^{-s t} d t=\mathscr{L}\{x(t)\}

$$

unde $s=\sigma+j \omega \in \boldsymbol{C}$. Funcţia $X(s) \in \boldsymbol{C}$ se numeşte funcţie imagine Laplace.

Transformata Laplace a semnalelor întâlnite în practică este o funcţie raţională, raport a două polinoame de variabilă $s$ de forma:

$$
\begin{align}
&X(s)=\frac{B(s)}{A(s)}=\frac{b_{n b} s^{n b}+\ldots+b_{1} s+b_{0}}{s^{n a}+a_{n a-1} s^{n a-1}+\ldots+a_{1} s+a_{0}}= \\
&=\frac{B(s)}{\prod_{k=1}^{n a}\left(s+p_{k}\right)}, n a, n b \in N, a_{i}, b_{j} \in \boldsymbol{R} .
\end{align}
$$

Relaţia de mai sus reprezintă transformata Laplace a unui semnal real dacă, şi numai dacă, este îndeplinită condiţia de realizabilitate fizică exprimată prin inegalitatea $n a \geq n b$.

Semnalul original $x(t)$ se poate obţine din transformata Laplace $X(s)$ prin aplicarea transformatei Laplace inverse, cu relaţia integrală, cunoscută sub denumirea de formulă de inversiune:

$$

x(t)=\frac{1}{2 \pi j} \int_{c-j \infty}^{c+j \infty} X(s) e^{s t} d t

$$

Calculul transformatei Laplace inverse cu formula de inversiune este foarte complicată, necesitând determinare reziduurilor funcţiei complexe $X(s)$. Dacă $X(s)$ este o funcţie raţională, cu rădăcini simple la numitor, exprimată printr-o relaţie de forma:

$$

X(s)=\frac{B(s)}{A(s)}=\frac{B(s)}{\prod_{k=1}^{n a}\left(s+p_{k}\right)},

$$

atunci semnalul original $x(t)$ se poate calcula relativ simplu cu relaţia:

$$

x(t)=\sum_{k=1}^{n a} a_{k} e^{-p_{k} t}

$$

unde

$$
a_{k}=\left.\frac{B(s)}{A^{\prime}(s)}\right|_{s=p_{k}}, \text { sau } a_{k}=\left.\left(s+p_{k}\right) \frac{B(s)}{A(s)}\right|_{s=p_{k}} \text {. }
$$

Transformatele Laplace ale unor [[semnale]] simple.

$$-\mathscr{L}\{\delta(t)\}=1$$

$$-\mathscr{L}\left\{1_{+}(t)\right\}=\frac{1}{s}$$

$$-\mathscr{L}\{t\}_{t \geq 0}=\frac{1}{s^{2}}$$

$$-\mathscr{L}\left\{e^{-a t}\right\}=\frac{1}{s+a}$$

$$-\mathscr{L}\left\{\sin \left(\omega_{0} t\right)\right\}=\frac{\omega_{0}}{s^{2}+\omega_{0}^{2}}$$

$$-\mathscr{L}\left\{\sin \left(\omega_{0} t\right)\right\}=\frac{s}{s^{2}+\omega_{0}^{2}}$$

$$-\mathscr{L}\left\{e^{-a t} \sin \left(\omega_{0} t\right)\right\}=\frac{\omega_{0}}{(s+a)^{2}+\omega_{0}^{2}}$$

$$-\mathscr{L}\left\{e^{-a t} \cos \left(\omega_{0} t\right)\right\}=\frac{s+a_{0}}{(s+a)^{2}+\omega_{0}^{2}}$$

### Definitia transformatei laplace

^aefd30

$$F(s)=L\{f(t)\}=\int^{\infty}_{0}f(t)e^{-st}dt$$

unde cu $L\{f(t)\}$ s-a notat [[Modele în domeniul timpului ale sistemelor liniare continue (curs 3+4 TS)#Transformata Laplace|transformata Laplace]]. In urma aplicarii transformatei Laplace rezulta o functie de variabila complexa $s$, notata cu $F(s)$. Plecand de la relatia de definite se poate calcula transformata Laplace pentru o anumita functie $f(t)$, dar in alte cazuri, pentru simplificarea calculelor se folosesc anumite teoreme si proprietati.

Procesul invers de determinare a functiei de timp $f(t)$ din [[Modele în domeniul timpului ale sistemelor liniare continue (curs 3+4 TS)#Transformata Laplace|transformata Laplace]] $F(s)$ se numeste **[[Modele în domeniul timpului ale sistemelor liniare continue (curs 3+4 TS)#Transformarea Laplace inversa|transformata Laplace inversa]]** (TLI). Notatia simbolica pentru TLI este $f(t)=L^{-1}\{F(s)\}$

In MatLab, pentru a evalua [[Modele în domeniul timpului ale sistemelor liniare continue (curs 3+4 TS)#Transformata Laplace|transformata Laplace]] directa si inversa se folosesc functiile **$\text{laplace}$** si **$\text{ilaplace}$** cu urmatoarele sintaze:

```MatLab
F=laplace(f)
f=ilaplace(F)
```