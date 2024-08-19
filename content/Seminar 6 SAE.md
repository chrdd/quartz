---
tags:
  - SistemeAutomateCuEsantionare
---
## Exercițiul 1
  

Se consideră funcția de transfer Z a unui sistem în circuit deschis de forma (avem în vedere că $H(z)=1)$. Să se traseze locul rădăcinilor:

  

$$G(z)=K \frac{\left(T_{e}+e^{-T_{e}}-1\right) z+1-e^{-T_{e}}-T_{e} e^{-T_{e}}}{(z-1)\left(z-e^{-T_{e}}\right)}=K \frac{z b_{1}+b_{0}}{(z-1)\left(z-e^{-T_{e}}\right)}$$

  

unde $b_{1}=T_{e}+e^{-T_{e}}-1, b_{0}=1-e^{-T_{e}}-T_{e} e^{-T_{e}}$.

  

---
  

### Pasul 1

Ecuaţia caracteristică a sistemului de reglare este

  

$$1+G H(z)=1+K b_{1} \frac{z+b}{z^{2}-\left(1+e^{-T_{e}}\right) z+e^{-T_{e}}}$$

  

unde

  

$$b=\frac{b_{0}}{b_{1}}=\frac{1-e^{-T_{e}}-T_{e} e^{-T_{e}}}{T_{e}+e^{-T_{e}}-1}$$

  

Cu un program simplu în MATLAB se poate vedea că pentru $T_{e} \in(0 ; 2) \mathrm{sec}$, $b_{1} \in(0 ; 1,17)$ şi $b_{1} \in(1 ; 0,524)$. Factorul de amplificare $K$ se presupune pozitiv şi variabil de la 0 la $\infty$.

  

### Pasul 2

Deoarece gradul polinomului de la numitor este $n=2$, locul rădăcinilor are 2 ramuri. Funcţia de transfer a sistemului deschis are 2 poli:

$p_{1}=1, p_{2}=e^{-T_{e}}$, сu $0<p_{2}<1$, şi un zero:

$z_{1}=-b$ , cu $z_{1} \in(-1 ;-0,524)$ când $T_{e} \in(0 ; 2) \mathrm{sec}$.

În figura 4.58 se prezintă repartiţia poli-zero pentru sistemul cu funcţia de transfer dată în cazul $T_{e}=0,3 \mathrm{~s}$. În această situaţie $p_{2}=0,7408$ şi $z_{1}=-0,9049$.

  

![](https://cdn.mathpix.com/cropped/2024_08_09_197c17df9d350146dfb3g-2.jpg?height=883&width=1234&top_left_y=255&top_left_x=411)

### Pasul 3

Locul rădăcinilor pe axa reală are două porţiuni şi anume:

- între polii $p_{1}$ şi $p_{2}$;
- între zeroul $z_{1}=-b=-0,9049$ şi $-\infty$.
### Pasul 4

Numărul asimptotelor este $n-m=1$. Ca şi în exemplul precedent, singura asimptotă este pe axa reală şi corespunde locului rădăcinilor cuprins între $z_{1}$ şi $-\infty$.

### Pasul 5

Deoarece există porţiuni ale locului pe axa reală între doi poli respectiv zerouri (unul finit, altul la infinit) vom avea puncte de ramificaţie. Aceste puncte se determină rezolvând ecuaţia

$$\frac{d K}{d z}=0$$unde $K=\frac{(z-1)\left(z-e^{-T_{e}}\right)}{b_{1}(z+b)}$.

Se obţine succesiv:

$$\frac{b_{1}(z+b)\left(2 z-1-e^{-T_{e}}\right)-b_{1}\left[z^{2}-\left(1+e^{-T_{e}}\right) z+e^{-T_{e}}\right]}{\left[b_{1}(z+b)\right]^{2}}=0$$

respectiv

$$z^{2}+2 b z-\left(b+e^{-T_{e}}+b e^{-T_{e}}\right)=0$$

cu soluţiile

$$z_{r 1,2}=-b \pm \sqrt{b^{2}+b+(b+1) e^{-T_{e}}}$$

Pentru $T_{e}=0,3 \mathrm{sec}$, valorile celor două rădăcini sunt $z_{r 1}=0,8657$ şi $Z_{r 2}=-2,6755$. Se poate vedea că aceste puncte de pe axa reală sunt într-adevăr puncte de ramificaţie fiind amplasate între cei doi poli ( 0,7405 şi 1 ), respectiv între zerouri $(-0,9049$ şi $-\infty)$.

Ca şi în exemplul precedent, între cele două puncte de ramificaţie locul rădăcinilor are forma unui cerc. Procedând ca mai înainte se obţine ecuaţia:

$$(x+b)^{2}+y^{2}=b^{2}+b+(b+1) e^{-T_{e}}$$  

deci cercul are centrul în punctul $(-b, 0)$ şi raza $R=\sqrt{b^{2}+b+(b+1) e^{-T_{e}}}$. Pentru $T_{e}=0,3$, centrul cercului va fi în punctul $(-0,9049,0)$ şi are raza $R=1,77$.  

### Pasul 6

Funcţia de transfer z a sistemului deschis nu are poli sau zerouri cu valori complexe.

### Pasul 7

Locul rădăcinilor prezintă 3 puncte în care sistemul închis este la limita de stabilitate. Două din aceste puncte corespund unor rădăcini complex conjugate şi prin urmare în aceste puncte avem aceeaşi valoare a factorului de amplificare $K_{1}$. Pentru a datermina valoarea lui $K_{1}$ corespunzătoare rădăcinilor complexe, folosim criteriul Routh bazat pe transformarea omografică $r$. În acest scop se foloseşte relaţia:

  

$$
\begin{align}
& 1+G H(z)=1+K_{1} b_{1} \frac{z+b}{z^{2}-\left(1+e^{-T_{e}}\right) z+e^{-T_{e}}} \\
&=\frac{z^{2}+\left(K_{1} b_{1}-1-e^{-T_{e}}\right) z+K_{1} b_{1} b+e^{-T_{e}}}{z^{2}-\left(1+e^{-T_{e}}\right) z+e^{-T_{e}}}
\end{align}
$$

  

de unde rezultă ecuaţia caracteristică în $z$ :

$$
z^{2}+\left(K_{1} b_{1}-1-e^{-T_{e}}\right) z+K_{1} b_{1} b+e^{-T_{e}}=z^{2}+a_{1} z+a_{0}=0
$$

în care $b_{1} b=b_{0}=1-e^{-T_{e}}-T_{e} e^{-T_{e}}$ şi $b_{1}=T_{e}+e^{-T_{e}}-1$.

În continuare, cu substituţia

$$
z=\frac{r+1}{r-1}
$$

se determină ecuaţia caracteristică în $r$ :

$$
\left(\frac{r+1}{r-1}\right)^{2}+a_{1}\left(\frac{r+1}{r-1}\right)+a_{0}=0
$$
  respectiv:

$$
\left(1+a_{1}+a_{0}\right) r^{2}+2\left(1-a_{0}\right) r+1-a_{1}+a_{0}=0
$$
  Tabelul Routh asociat acestei ecuaţii este:

| $r^{2}$ | $1+a_{1}+a_{0}$         | $1-a_{1}+a_{0}$ |
| ------- | ----------------------- | --------------- |
| $r^{1}$ | $2\left(1-a_{0}\right)$ | 0               |
| $r^{0}$ | $1-a_{1}+a_{0}$         | 0               |

La limita de stabilitate ecuaţia caracteristică în $r$ are rădăcinile imaginare $\pm j \omega_{r}$, deci în tabloul Routh trebuie să avem un rând de zerouri. Acest lucru este realizat dacă termenul din rândul $2\left(r^{1}\right)$ coloana 1 este egal cu zero, deci dacă:

$1-a_{0}=0$, respectiv $a_{0}=1$

de unde, având în vedere că

$$
a_{0}=K_{1} b_{0}+e^{-T_{e}}
$$
rezultă

$$
K_{1}=\frac{1-e^{-T_{e}}}{b_{0}}=\frac{1-e^{-T_{e}}}{1-e^{-T_{e}}-T_{e} e^{-T_{e}}}
$$
Pentru $T_{e}=0,3 \mathrm{sec}$ rezultă că factorul de amplificare pentru care sistemul discret analizat este la limita de stabilitate are valoarea $K_{1}=7,02$.

Al treilea punct în care sistemul este la limita de stabilitate este $z=-1$, iar factorul de amplificare corespunzător $K_{2}$ se calculează cu relaţia:

$$
K_{2}=\left|\frac{1}{G H(-1)}\right|=\left|\frac{z^{2}-\left(1+e^{-T_{e}}\right) z+e^{-T_{e}}}{z b_{1}+b_{0}}\right|_{z=-1}=\left|\frac{2\left(1+e^{-T_{e}}\right)}{b_{0}-b_{1}}\right|
$$
$$K_{2}=\left|\frac{2\left(1+e^{-T_{e}}\right)}{2\left(1-e^{-T_{e}}\right)-T_{e}\left(1+e^{-T_{e}}\right)}\right|$$

Pentru $T_{e}=0,3 \mathrm{sec}$ rezultă $K_{2}=448,44$, valoare care nu prezintă interes deoarece este mult mai mare decât $K_{1}=7,02$ obţinută la limita de stabilitate pentru rădăcinile complexe.

Locul rădăcinilor pentru o perioadă de eşantionare cu valoarea $T_{e}=0,1 \mathrm{sec}$ are următoarele date numerice:

- $p_{1}=1, p_{2}=0,9048, z_{1}=-0,9672$;
- $z_{r 1}=0,9518, z_{r 2}=-2,8863$
- $R=1,919$, centrul $(-0,9672,0)$;
- $K_{1}=20,34$.