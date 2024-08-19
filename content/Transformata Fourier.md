---
tags:
  - PrelucrareaSemnalelor
  - IdentificareaSistemelor
  - SistemeAutomateCuEsantionare
pdf: "[[MIS_03.pdf]]"
---
## Transformata fourier continua
### Definitii
#### Spectrul unui semnal

Spectrul unui semnal descrie continutul de semnale armonice ale semnalului analizat

#### Transformata fourier

^ffa3b7

Transformata Fourier este o metoda de analiza spectrala a semnalelor, adica o metoda de analiza in domeniul frecventei.

Formula matematica este urmatoarea:

$$X(\omega)=\int^{\infty}_{-\infty}x(t)e^{-j \omega t}dt$$

>[!info] Observatie
>Notatia uzuala este cea cu litera mare corespunzatoare notatiei pentru semnalul initial, iar functia obtinuta este complexa si are ca argument pulsatia.

>[!info] Observatie
> Variabila $j$ este echivalenta cu variabila complexa $i$, cu proprietatea ca $i^2=-1$

O alta notatie pentru tranformata Fourier este:

$$X(\omega)= \digamma\{x(t)\}$$
![](https://youtu.be/n2y7n6jw5d0?si=9eEFyMBQHVc5_qyk)

#### Pereche fourier

Functia de timp $x(t)$ si functia de pulsatie $X(\omega)$ formeaza o **pereche Fourier** (notat $x(t) \leftrightarrow X(\omega)$).

#### Transformata fourier inversa

Obtinerea functiei de timp dintr-o functie de pulsatie se face prin **transformata Fourier inversa**, definita de relatia:

$$x(t)=\frac{1}{2 \pi}\int^{\infty}_{-\infty}X(\omega)e^{j\omega t}d \omega$$

Care este echivalenta cu:

$$x(t)= \digamma^{-1}\{X(\omega)\}$$

#### Produsul de convolutie

Produsul de convolutie pentru 2 semnale continue $x(t)$ si $y(t)$ este definit astfel:

$$x(t)*y(t)=\int^{\infty}_{-\infty}x(t)y(t-\tau)d\tau$$

>[!important] Observatie
>Daca intro ecuatie se foloseste variabila $t$, atunci se foloseste o alta variabila legata de timp, si anume $\tau$.

$$\digamma\{x(t)+y(t)\}=X(\omega)Y(\omega)$$

#### Transformata fourier a unei expresii liniare

Transformata Fourier a unei expresii liniare de 2 semnale $x$ si $y$ este:

$$\digamma\{\alpha x(t)+\beta y(t)\}=\alpha X(\omega)+\beta Y(\omega)$$

#### Proprietatea de dualitate

Daca exista perechea Fourier $x(t) \leftrightarrow y(\omega)$, atunci mai exista inca 2 perechi Fourier, si anume:

$$y(t) \leftrightarrow 2 \pi x(- \omega)$$

$$y(-t) \leftrightarrow 2 \pi x (\omega)$$

>[!info] Observatie
>Doar la descrierea acestei proprietati sunt folosite notatii cu litera mica pentru functiile $x$ si $y$

**Exemplu:**
Consideram functia de timp impuls Dirac
$$\delta t=\{ \begin{align}\infty,t=0;\\ 0,t \neq 0\end{align}$$
$$\Delta(\omega)=\digamma\{\delta(t)\}=1(\omega)$$
Spectrul unui semnal care prezinta discontinuitati (ex: impulsul DIrac) este continuu si infinit. In practica nu avem discontinuitati in sens matematic, ci avem modificari rapide ale semnalului. 
Aceste modificari produc un spectru bogat.

#### Semnalul poarta temporala

Pentru semnalul $1(t) \leftrightarrow 2 \pi \delta(\omega)$

Functia **Poarta temporala centrata**

$$
W_T^C(t)=\{\begin{align}
1, -\frac{T}{2} \leq t \leq \frac{T}{2}\\
0, altfel
\end{align}
$$
![[Screenshot from 2023-03-04 08-33-53.png]]
Aceasta functie modeleaza matematic achizitia unei portiuni dintr-un semnal mixt $x(t)$ pentru intervalul egal cu $T$.

Transformata Fourirer a acestui semnal:

$$W_T^C=T \frac{\sin \frac{\omega T}{2}}{\frac{\omega T}{2}}$$
>[!info] Observatie
>1. Aici $T$ reprezinta latimea portii temporare
>2. Semnalul mai este denumit "Fereastra temporala centrata"

Avem de asemenea fereastra temporala necentrata care are functia:

$$
W_T(t)=\{\begin{align}
1, 0 \leq t \leq T\\
0, altfel
\end{align}
$$
 

![[Screenshot from 2023-03-04 08-41-13.png]]

Transformata Fourier va fi:

$$W_T(\omega)=e^{-j \frac{\omega t}{2}}T \sin(j \omega t)$$

Intr-o aplicatie practica, semnalul efectiv analizat este semnalul original $x(t)$ conditionat de semnalul poarta temporala necentrata, adica semnalul disponibil va fi:

$$x_t(t)=x(t)W_T(t)$$

## Transformata fourier discreta

#SistemeAutomateCuEsantionare 

### Definitie

Transformata Fourier discreta transforma semnalele discretizate din timpul domeniului in domeniul frecventei, adica cu ajutorul acesteia putem reprezenta un semnal in functie de frecventele continute in acesta.

Forma generala a transformatei Fourier discrete este urmatoarea:

$$X(\omega)=\sum_{n=-\infty}^{\infty}x[n]e^{-i \omega n}$$

Cu ajutorul acesteia, putem determina din ce frecvente este compusa frecventa semnalului de iesire.

![Understanding the Z-Transform](https://youtu.be/XJRW6jamUHk?si=WkOR5P22I4C99yB2&t=328)

---

#IdentificareaSistemelor 

### Definite

Fie $\{x_{p}[n]\}$ o secventa periodica a carei perioada este continua dintr-un numar finit de esantioane. 

![[Pasted image 20231007215232.png]]

**Transformata Fourier discreta** a secventei se defineste prin relatia:

$$TFD\{x_{p}[n]\}=X_{p}(k)=\sum^{N-1}_{n=0}x_{p}[n] \cdot \left( e^{-j \frac{2- \pi}{N}} \right)^{-n \cdot k}=\sum^{N-1}_{n=0}x_{p}[n] \cdot W^{-n \cdot k}$$
**Transformata Fourier discreta inversa** este data de relatia:

$$TFDI\{X_{p}(k)\}=x_{p}[n]=\frac{{1}}{N} \sum^{N-1}_{n=0}X_{p}(k) \cdot W^{n \cdot k}$$
Proprietatile marimii $W$ sunt urmatoarele:
1. $W^{N}=1$
2. $W^{\frac{N}{2}}=-1$
3. $W^{\frac{N}{4}}=+j$
4. $W^{\frac{3N}{4}}=-j$
5. $W^{K \cdot N}=1, \quad K \in N$
6. $W^{K \cdot N + r}=W^{r}, \quad K,r \in N$

Forma matriceala a transformatei Fourier discreta directa este urmatoarea:

$$
\begin{bmatrix}
x_{p}[0]\\x_{p}[1]\\x_{p}[2]\\\vdots\\x_{p}[N-1]
\end{bmatrix}= \begin{bmatrix}
1&1&\dots&1\\1&W^{-1}&\dots&W^{-(N-1)}\\1&W^{-2}&\dots&W^{-2(N-1)}\\\vdots&\vdots&\vdots&\vdots\\1&W^{-(N-1)}&\dots&W^{-(N-1)^{2}}
\end{bmatrix} \cdot \begin{bmatrix}
x_{p}[0]\\x_{p}[1]\\x_{p}[2]\\\vdots\\x_{p}[N-1]
\end{bmatrix}
$$
Forma matriceala a transformatei Fourier discreta inversa este urmatoarea:

$$
\begin{bmatrix}
x_{p}[0]\\x_{p}[1]\\x_{p}[2]\\\vdots\\x_{p}[N-1]
\end{bmatrix}= \begin{bmatrix}
1&1&\dots&1\\1&W^{-1}&\dots&W^{(N-1)}\\1&W^{-2}&\dots&W^{2(N-1)}\\\vdots&\vdots&\vdots&\vdots\\1&W^{(N-1)}&\dots&W^{(N-1)^{2}}
\end{bmatrix} \cdot \begin{bmatrix}
x_{p}[0]\\x_{p}[1]\\x_{p}[2]\\\vdots\\x_{p}[N-1]
\end{bmatrix}
$$


![[Pasted image 20231007220554.png]]

### Proprietatile transformatei fourier discrete

#### Teorema de liniaritate
Fiind date 2 secvente periodice cu aceeasi perioada $\{x_{p}[n]\}$ si $\{y_{p}[n]\}$ si 2 constante $a$ si $b$, atunci:

$$TFD\left[a \cdot \{x_{p}[n]\}+b \cdot \{y_{p}[n]\}\right]=a  \cdot X_{p} (k) + b \cdot Y_{p}(k)$$
#### Teorema inversiunii in timp
Fiind data o secventa periodica $\{x_{p}[n]\}$, atunci:

$$TFD\{x_{p}[-n]\}=X_{p}(-k)=X_{p}(N-k)$$

#### Teorema deplasarii ciclice in timp si in frecventa
Fiind data o secventa periodica $\{x_{p}[n]\}$ cu transformata Fourier discreta $X_{p}(k)$. Urmatoarele relatii sunt adevarate:
- $TFD\{x_{p}[n-r]\}=X_{p}(k) \cdot W^{-r \cdot k}$
- $TFDI\{X_{p}(k-r)\}=x_{p}[n] \cdot W^{n \cdot r}$

Fiind data o secventa periodica $\{x_{p}[n]\}$ cu transformata Fourier discreta $X_{p}(k)$. Transformata Fourier discreta a secventei date este egala cu transformata Fourier discreta complex conjugata a secventei inverse.

$$TFD \{x_{p}[n]\}=X_{p}(k)=X^{*}_{p}(-k)=X^{*}_{p}(N-k)$$
#### Convolutia circulara
Fiind date $\{x_{p}[n]\}$ si $\{ h_{p}[n] \}$ doua secvente periodice de perioada $N$, convolutia circulara a acestor secvente este data de relatia:

$$y_{p}[n]=\sum^{N-1}_{l=0}x_{p}[l] \cdot h_{p}[n-l]$$

Transformata Fourier discreta a produsului de convolutie a doua secvente periodice este egala cu produsul transformatelor Fourier discrete ale celor 2 secvente:

$$Y_{p}(k)=H_{p}(l) \cdot X_{p}(k)$$

Produsul de convolutie are forma matriceala:

$$
\begin{bmatrix}
y[0]\\y[1]\\y[2]\\ \vdots\\y[N-1]
\end{bmatrix}= \begin{bmatrix}
h[0]& h[N-1]& \dots&h[1]\\h[1]& h[0]& \dots&h[2]\\h[2]& h[1]& \dots&h[3]\\\vdots&\vdots&\vdots&\vdots\\h[N-1]& h[N-2]& \dots&h[0]
\end{bmatrix} \cdot \begin{bmatrix}
x[0]\\x[1]\\x[2]\\ \vdots\\x[N-1]
\end{bmatrix}
$$
### Formule de calcul



|**Nr.**|**Denumire**|**Expresia**|
----|----------|---------|
1.|Definitia $TFD$|$X_{p}(k)=\sum^{N-1}_{n=0}x_{p}[n] \cdot \left( e^{-j \frac{2 \cdot \pi}{N}} \right)^{-n \cdot k}=\sum ^{N-1} _{n=0} x_{p}[n] \cdot W^{-n \cdot k}$|
2.|Calculul $TFDI$| $x_{p}[n]=\frac{1}{N}\sum^{N-1}_{n=0}X_{p}(k) \cdot W^{n \cdot k}$|
3.|Liniaritatea $TFD$|$TFD\left[ a \cdot \{ x_{p}[n] \}+b \cdot \{ y_{p}[n] \} \right]=a \cdot X_{p}(k)+b \cdot Y_{p}(k)$|
4.| Inversiunea in timp|$TFD \{ x_{p}[-n] \}=X_{p}(-k)=X_{p}(N-k)$|
5.|Deplasari ciclice in timp si in frecventa| $\begin{cases} TFD \{ x_{p}[n-r] \}=X_{p}(k) \cdot W^{-r \cdot k}\\ TFDI \{X_{p}(k-r)\}=x_{p}[n] \cdot W^{n \cdot r} \end{cases}$|
6.|$TFD$ a secventei complex conjugata|$TFD \{ x_{p}[n] \} =X_{p}(k)=X^{*}_{p}(-k)=X_{p}^{*}(N-k)$|
7.|Definitia convolutiei circulare|$y_{p}[n]=\sum^{N-1}_{i=0}x_{p}[l] \cdot h_{p}[n-l]$|
8.| $TFD$ a produsului de convolutie|$Y_{p}(k)=H_{p}(k) \cdot X_{p}(k)$|



