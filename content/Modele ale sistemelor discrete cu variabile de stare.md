---
tags:
  - SistemeAutomateCuEsantionare
aliases:
  - Curs 9 SAE
---

Se considera sistemul continuu monovariabil $\sum(A,B,C)$ descris la stare de ecuatiile matriciale:[^1]

$$
\begin{aligned}
&\dot{x(t)}=Ax(t)+Bu(t)\\
&y(t)=Cx(t)
\end{aligned}
$$

unde $x$ este [[Analiza sistemelor modelate in spatiul starilor#Vectorul de stare|vectorul de stare]].

Sistemul discret cu variabile de stare poate fi reprezentat astfel:

![[2023-08-04T10:41:32,631706334+03:00.png]]

unde $EI$ constituie esantionatorul ideal, $EIF$ este un esantionator ideal fictiv, iar $ER0$ este elementul de retinere de ordinul $0$.

Pentru deducerea relatiilor care leaga matricele sistemului discret cu cele ale sistemului continuu se foloseste raspunsul sistemului continuu modelat la stare exprimat conform relatiei:

$$x(t)=e^{A(t-t_0)}x(t_0)+\int^{t}_{t_0}e^{A(t-\tau)}Bu(\tau)d \tau$$
Pentru discretizarea in ecuatia rapsunsului consideram $t_0=kT_e$ si $t=(k+1)T_e$, astfel $t-t_0=T_e$ si prin urmare expresia la stare devine:

$$x(kT_e+T_e)=e^{AT_e}x(kT_e)+\int^{kT_e+T_e}_{kT_e}e^{A(kT_e+T_e-\tau)}Bu(\tau) d \tau$$
Acest rezultat nu depinde de tipul elementului de retinere, deoarece $u$ este specificat prin evolutia sa in intervalul de esantionare.

## Simplificarea modelului discretizat

Pentru obtinerea unui model discretizat cat mai simplu se considera ca marimea de intrare se aplica (dupa esantionare) prin intermediul unui element de retinere de ordin 0:

$$u(\tau)=u(kT_e), \quad \text{pentru } \tau \in [kT_e,kT_e+T_e) $$

De asemenea, se face schimbarea de variabila:

$$v=kT_e+T_e-\tau$$
si astfel se obtine:

$$x(kT_e+T_e)=e^{AT_e}x(kT_e)+\left[ \int^{T_e}_{0} e^{Av}dv \right] Bu(kT_e)$$
Se definesc matricele:

$$\Phi=e^{AT_e} \quad \text{si} \quad  \Gamma= \left[ \int^{T_e}_{0}e^{Av}dv \right]B$$
>[!info] 
>Neglijand $T_e$ din relatia originala si considerand matricile definite anterior, se obtine ecuatia de stare in forma unei ecuatii cu diferente:
$$x[k+1]=\Phi x[k]+\Gamma u[k]$$
care impreuna cu ecuatia matriceala a iesirii:
$$y[k]=Cx[k]$$
formeaza **modelul cu variabile de stare a sistemului discret**.

Matricea de stare a sistemului discret egala cu exponentiala matriceala $e^{AT_e}$ se determina cu ajutorul dezvoltarii in serie Taylor folosind relatia:

$$\Phi=I+AT_e+\frac{A^2T_e^2}{2!}+\frac{A^3T_e^3}{3!}+ \ldots$$
care se poate scrie conform expresiei:

$$\Phi=I+AT_e \Psi$$
unde $\Psi=I+\frac{AT_e}{2!}+\frac{A^2T_e^2}{3!}+ \ldots$

Cu aceste notatii, matricea integrala $\Gamma$ poate fi evaluata termen cu termen, fiind:

$$\Gamma=\sum^{\infty}_{k=0}\frac{A^kT_e^{k+1}}{(k+1)!}B=\sum^{\infty}_{k=0}\frac{A^kT_e^{k+1}}{(k+1)!}T_eB=\Psi T_e B$$
unde $\Psi$ este:

$$\Psi=I+\frac{AT_e}{2}\left( I+\frac{AT_e}{3}\left( \ldots I+\frac{AT_e}{N-1}  \left( I+\frac{AT_e}{N} \right)\ldots\right) \right)$$
evaluare care ofera proprietati numerice mult mai bune decat evaluarea directa [^2]
Pentru $N=1,\Psi=I$ si matricele sistemului discret vor fi:

$$\Phi=I+AT_e \Psi=I+AT_e, \quad \text{respectiv} \quad \Gamma=\Psi T_e B = T_e B$$
iar daca $N=2, \Psi=I+AT_e$ si matricele sistemului sunt:
 
 $$\Phi=I+AT_e+\frac{A^2 T_e^2}{2}, \quad \text{respectiv} \quad \Gamma=BT_e+\frac{AB}{2}T_e^2$$

## Conversia modelului cu variabile de stare in functii de transfer $z$

Relatia generala de conversie a unui model discret din spatiul starilor intr-o functie de transfer se determina pornind de la ecutaiile de stare si iesire scrise sub forma matriceala:

$$
\begin{align}
&x[k+1]=\Phi x[k] + \Gamma u[k]\\
&y[k]=Cx[k]
\end{align}
$$
Prin aplicarea transformatei $z$ in ipoteza conditiilor initiale nule se obtine:
$$
\begin{align}
&zX(z)-X(0)=\Phi X(z) + \Gamma U(z) \\
&Y(z)=CX(z)
\end{align}
$$
unde $U(z)$ si $Y(z)$ sunt transformatele $z$ ale marimilor de intrare si iesire, iar $X(z)$ este vectorul transformatelor $Z$ ale variabilelor de stare.

Rezolvand in raport cu $X(z)$ prima ecuatie se obtine:

$$(zI-\Phi)X(z)=\Gamma U(z) \quad \text{respectiv} \quad X(z)=(zI-\Phi)^{-1}\Gamma U(z)$$
unde:
>[!info] 
>$$(zI-\Phi)^{-1}=\frac{adj(zI-\Phi)}{\det(zI-\Phi)}$$
>este **matricea fundamentala a sistemului discret**

Se inlocuieste $X(z)$ din relatia $X(z)=(zI-\Phi)^{-1}\Gamma U(z)$ in relatia $Y(z)=CX(z)$, astfel obtinandu-se:

$$Y(z)=C(zI-\Phi)^{-1}\Gamma U(z)$$
de unde rezulta:

$$G(z)=\frac{Y(z)}{U(z)}=C(zI-\Phi)^{-1}\Gamma$$
care este tocmai functia de transfer $z$ exprimata in functie de matricele sistemului discret modelat de stare.
## Conversia functiilor de transfer $z$ in modele cu variabile de stare

Variabele de stare nu sunt unic definite. Teoretic exista posibilitatea de a obtine un numar nelimitat de modele in spatiul starilor pornind de la o anumita functie de transfer. Vom numi realizare in spatiul starilor un model cu variabile de stare care se deduce pornind de la o functie de transfer data. 

Modelele diferite cu variabile de stare care se determina pornind de la aceeasi functie de transfer se numesc **realizari** sau **forme echivalente**.

In literatura s-au impus 3 tipuri de realizari cu variabile de stare numite **realizari (forme) standard**:
1. **complet controlabila** (alternativ **cu variabile de faza**)
2. **complet observabila**
3. **canonica diagonala**

Aceste realizari standard se determina exact in acelasi mod ca la sisteme comune.

### Realizarea complet controlabila
#### Varianta de baza
Exista diverse modalitati pentru obtinerea acestei realizari. Vom ilustra deducerea acestei forme folosind cazul particular al functiei de transfer:

$$G(z)=\frac{Y(z)}{U(z)}=\frac{b_2z^2+b_1+b_0}{z^3+a_2z^2+a_1z+a_0}$$
Se introduce variabila auxiliara $x(t)$, cu [[Transformata Z|transformata Z]], $X(z)$, care se defineste conform relatiei:

$$\frac{Y(z)}{X(z)} \frac{X(z)}{U(z)}=(b_2z^2+b_1z+b_0)\frac{1}{z^3+a_2z^2+a_1z+a_0}$$
de unde rezulta:

$$\frac{X(z)}{U(z)}=\frac{1}{z^3+a_2z^2+a_1z+a_0}$$
si

$$\frac{X(z)}{U(z)}=b_2z^2+b_1z+b_0$$
 care se pot scrie conform expresiilor
 
 $$(z^3+a_2z^2+a_1z+a_0)X(z)=U(z) \quad \text{si} \quad Y(z)=(b_2z^2+b_1z+b_0)X(z)$$
 
Aplicam [[Transformata Z#Transformata z inversa|transformata Z inversa]] ecuatiei 

$$(z^3+a_2z^2+a_1z+a_0)X(z)=U(z)$$ in conditii initiale nule si avand in vedere ca:

$$
\begin{cases}
Z^{-1}\{U(z)\}=u[k]\\ 
Z^{-1}\{X(z)\}=x[k]\\
Z^{-1}\{zX(z)\}=x[k+1]\\
Z^{-1}\{z^2X(z)\}=x[k+2]\\
Z^{-1}\{z^3X(z)\}=x[k+1]
\end{cases}
$$
>[!info] rezulta **ecuatia cu diferente**:
>$$x[k+3]+a_2x[k+2]+a_1x[k+1]+a_0x[k]=u[k]$$


Definim variabilele de stare conform schemei:

$$
\begin{cases}
x_1[k]=x[k]\\
x_2[k]=x[k+1]=x_1[k+1]\\
x_3[k]=x[k+2]=x_2[k+1]
\end{cases}
$$
si folosim ecuatia cu diferente pentru a obtine diferenta pentru ultima marime de stare:
$$
x[k+3]=x_3[k+1]=-a_2x_3[k]-a_1x_2[k]-a_0x_1[k]+u[k]
$$
Astfel rezulta sistemul de ecuatii de stare exprimat conform relatiilor:

$$
\begin{cases}
x_1[k+1]=x_2[k]\\
x_2[k+1]=x_3[k]\\
x_3[k+1]=-a_2x_3[k]-a_1x_2[k]-a_0x_1[k]+u[k]
\end{cases}
$$
Ecuatia iesirii pentru modelul cu variabile de stare se deduce in baza relatiei $Y(z)=(b_2z^2+b_1z+b_0)X(z)$, scrisa in domeniul timpului pentru conditiile initiale nule:

$$
y[k]=Z^{-1}\{b_2z^2X(z)+b_1zX(z)+b_0X(s)\}=b_2x[k+2]+b_1x[k+1]+b_0x[k]
$$
de unde avand in vedere relatiile de definitie ale variabilei de stare rezulta:

$$
y[k] =b_2x_3[k]+b_1x_2[k]+b_0x_1[k]
$$
>[!info] In concluzie **modelul corespunzator  formei complet controlabile este:**
>
>$$
>\begin{cases}
x_1[k+1]=x_2[k]\\
x_2[k+1]=x_3[k]\\
x_3[k+1]=-a_2x_3[k]-a_1x_2[k]-a_0x_1[k]+u[k]\\
y[k]=b_0x_1[k]+b_1x_2[k]+b_2x_3[k]
\end{cases}$$
de unde prin identificarea cu forma matriceala rezulta:
>$$\Phi=\begin{bmatrix}
0&1&0\\
0&0&1\\
-a_0&-a_1&-a_2
\end{bmatrix} , \Gamma=\begin{bmatrix}
0\\0\\1
\end{bmatrix}, C=\begin{bmatrix}
b_0&b_1&b_2
\end{bmatrix}
$$

Variabilele de stare obtinute conform schemei prezentate se numesc **variabile de faza**

Generalizand rezultatul pentru o **functie de transfer de ordinul $n$**:

$$
G(z)=\frac{Y(z)}{U(z)}=\frac{b_{n-1}z^{n-1}+\ldots+b_1z+b_0}{n^n+a_{n-1}z^{n-1}+\ldots+a_1z+a_0}
$$
**Modelul de stare in forma controlabila va fi descris de matricele:**

$$
\begin{bmatrix}
0&1&0&0&\ldots&0&0\\
0&0&1&0&\ldots&0&0\\
\vdots& \vdots& \vdots& \vdots& \vdots& \vdots& \vdots\\
-a_0&-a_1&-a_2&-a_3&\ldots&-a_{n-2}&-a_{n-1}
\end{bmatrix}_{(n \times n)}, \Gamma=\begin{bmatrix}
0\\0\\\vdots&\\1
\end{bmatrix}_{(n \times 1)}, C=\begin{bmatrix}
b_0&b_1&\ldots&b_{n-1}
\end{bmatrix}_{(1 \times n)}
$$

Matricea $\Phi$ cu forma prezentata anterior se mai numeste **matrice companion inferioara**.

#### Varianta pentru realizarea complet controlabila
Folosim forma complet controlabila utilizand cazul particular al functiei de transfer:

$$
\begin{align}
& G(z)=\frac{Y(z)}{U(z)}=\frac{b_2z^2+b_1+b_0}{z^3+a_2z^2+a_1z+a_0} \\
&=\frac{Y(z)}{X(z)} \frac{X(z)}{U(z)}=(b_2z^2+b_1z+b_0)\frac{1}{z^3+a_2z^2+a_1z+a_0}
\end{align}
$$

In prima etapa se procedeaza in acelasi mod ca la forma de baza. 
Se introduce variabila auxiliara $X(z)$ si dupa aplicarea [[Transformata Z#Transformata z inversa|transformatei Z inverse]] se obtin ecuatiile cu diferente:

$$x[k+3]+a_2x[k+2]+a_1x[k+1]+a_0x[k]=u[k]$$
si
$$y[k]=b_2x[k+2]+b_1x[k+1]+b_0x[k]$$

Variabilele in stare se aleg insa acum astfel:

$$
\begin{cases}
x_3[k]=x[k]\\
x_2[k]=x[k+1]=x_3[k+1]\\
x_1[k]=x[k+2]=x_2[k+1]
\end{cases}
$$
Substituind variabilele de starea astfel definite in cele 2 ecuatii se obtin:
$$x_1[k+1]+a_2x_1[k]+a_1x_2[k]+a_0x_3[k]=u[k] \quad \text{si} \quad y[k]=b_2x_1[k]+b_1x_2[k]+b_0x_3[k]$$
>[!info] Din cele prezentate rezulta **modelul cu variabile de stare pentru varianta formei complet controlabile** descris de ecuatiile:
>
>$$
>\begin{cases}
x_1[k+1]=-a_2x_1[k]-a_1x_2[k]-a_0x_3[k]+u[k]\\
x_2[k+1]=x_1[k]\\
x_3[k+1]=x_1[k]\\
y[k]=b_2x_1[k]+b_1x_2[k]+b_0x_3[k]
\end{cases}$$
>
>de unde prin identificare cu forma matriceala generala, vom obtine matricele:
>$$\Phi=\begin{bmatrix}
-a_2&-a_1&-a_0\\
0&1&0\\
0&0&1
\end{bmatrix} , \Gamma=\begin{bmatrix}
1\\0\\0
\end{bmatrix}, C=\begin{bmatrix}
b_2&b_1&b_0
\end{bmatrix}
$$

### Realizarea complet observabila
Se introduce pornind de la forma complet controlabila, folosind proprietaatea de echivalenta a celor 2 realizari.

In baza acestei proprietati cele 2 forme (complet controlabila si complet observabila) au aceeasi functie de transfer $G(z)$.

Pentru simplificarea expunerii consideram din nou cazul functiei de transfer de ordinul 3:
$$G(z)=\frac{b_2z^2+b_1z+b_0}{z^3+a_2z^2+a_1z+a_0}$$
In acest caz forma complet controlabila este descrisa la stare de matricele:

$$
\Phi=\begin{bmatrix}
0&1&0\\
0&0&1\\
-a_0&-a_1&-a_2
\end{bmatrix} , \Gamma=\begin{bmatrix}
0\\0\\1
\end{bmatrix}, C=\begin{bmatrix}
b_0&b_1&b_2
\end{bmatrix}
$$

Deoarece $G(z)$ este o functie scalara avem proprietatea:
$$G(z)=G^T(z)=[C(zI-\Phi)^{-1}\Gamma]^T$$

unde indicele superior $T$ specifica operatia de transpunere matriceala.

Avand in vedere proprietatea de transpunere a unui produs matriceal se poate scrie:
$$G(z)=G^T(z)=\Gamma^T[(zI-\Phi)^{-1}]^TC^T=\Gamma^T(zI-\Gamma^T)^{-1}C^T=C_0(zI-\Phi_0)^{-1}\Gamma_0$$
unde $\Phi_0,\Gamma_0,C_0$ reprezinta noile matrice ale formei complet observabile care rezulta prin identificarea din ultima egalitate conform expresiilor:

$$
\begin{align}
& \Phi_0=A^T=\begin{bmatrix}
0&1&0\\
0&0&1\\
-a_0&-a_1&-a_2
\end{bmatrix}^T=\begin{bmatrix}
0&0&-a_0\\
1&0&-a_1\\
0&1&-a_2
\end{bmatrix},\Gamma_0=C^T=\begin{bmatrix}
b_0&b_1&b_2
\end{bmatrix}^T \\
&=\begin{bmatrix}
b_0\\b_1\\b_2
\end{bmatrix},C_0=B^T=\begin{bmatrix}
0\\0\\1
\end{bmatrix}^T=\begin{bmatrix}
0&0&1
\end{bmatrix}
\end{align}
$$


>[!info] In consecinta modelul corespunzator **formei complet observabile este descris de ecuatiile:**
>$$\begin{cases}
x_1[k+1]=-a_0x_3[k]+b_0u[k]\\
x_2[k+1]=x_1[k]-a_1x_3[k]+b_1u[k]\\
x_3[k+1]=x_2[k]-a_2x_3[k]+b_2u[k]\\
y[k]=x_3[k]
\end{cases}$$

Generalizand rezultatul pentru o functie de transfer de ordinul $n$ se obtine modelul la stare in forma complet observabila descris de matricele:

$$
\begin{bmatrix}
0&0&0&0&\ldots&0&-a_0\\
1&0&0&0&\ldots&0&-a_1\\
0&1&0&0&\ldots&0&-a_2\\
\vdots&\vdots&\vdots&\vdots&\vdots&\vdots&\vdots\\
0&0&0&0&\ldots&1&-a_{n-1}
\end{bmatrix}_{(n \times n)}, \Gamma=\begin{bmatrix}
b_0\\b_1\\\vdots\\b_{n-1}
\end{bmatrix}_{(n \times 1)}, C=\begin{bmatrix}
0&0&\ldots&0&1
\end{bmatrix}_{(1 \times n)}
$$

### Realizarea canonica diagonala
Se deduce pornind de la functia de transfer scrisa cu polinomul caracteristic sub forma factorizata. 
Consideram mai intai cazul in care functia de transfer are poli distrincti. Functia de transfer se descompune in fractii simple conform procedeului:

$$
\frac{Y(z)}{U(z)}=\frac{B(z)}{(z-p_1)(z-p_2)\ldots(z-p_n)}=\frac{c_1}{z-p_1}+\frac{c_2}{z-p_2}+\ldots+\frac{c_n}{z-p_n}
$$
unde $c_j=\left[ (z-p)_j \frac{B(z)}{A(z)} \right]_{z=p_i}$, cu $A(z)=(z-p_1)(z-p_2)\ldots(z-p_n)$

Variabilele de stare se definesc initial cu relatiile:
$$X_j(z)=\frac{1}{z-p_j}U(z), \quad j=1,2,\ldots,n$$
scrise apoi conform expresiilor
$$zX_j(z)=p_jX_j(z)+U(z), \quad j=1,2,\ldots,n$$
de unde, prin aplicarea TLI rezulta ecuatiile de stare:

$$
\begin{cases}
x_1[k+1]=p_1x_1[k]+u[k]\\
x_2[k+1]=p_2x_2[k]+u[k]\\
\vdots\\
x_n[k+1]=p_nx_n[k]+u[k]
\end{cases}
$$
Ecuatia iesirii se obtine din descompunenrea in fractii simple conform relatiei:
$$y[k]=c_1x_1[k]+c_2x_2[k]+\ldots+c_nx_n[k]$$

Modelul cu variabile de stare in forma diagonala este descris de matricele:

$$
\Phi=\begin{bmatrix}
p_1&0&\ldots& 0 & 0\\
0& p_2 & \ldots & 0 & 0\\
\vdots&\vdots&\vdots&\vdots&\vdots\\
0&0&\ldots&p_{n-1}&0\\
0&0&\ldots&0&p_n
\end{bmatrix}, \Gamma=\begin{bmatrix}
1\\1\\\vdots\\1
\end{bmatrix},C=\begin{bmatrix}
c_1&c_2&\ldots&c_n
\end{bmatrix}
$$
unde $p_j$ sunt toti polii distincti, iar $c_j$ sunt coeficientii dezvoltarii in fractii simple a functiei de transfer $G(z)$.

#### Cazul polilor multiplii
Un caz special apare cand $G(z)$ contine poli multipli. 
Consideram cazul unei functii de transfer de ordinul 4 cu un pol triplu, exprimata conform relatiei:
$$ \frac{Y(z)}{U(z)}=G(z)=\frac{B(z)}{(z-p_1)^3(z-p_2)} $$
Dezvoltarea in fractii simple va fi:
$$ \frac{Y(z)}{U(z)}=\frac{c_{11}}{(z-p_1)^3}+\frac{c_{12}}{(z-p_1)^2}+\frac{c_{13}}{z-p_1}+\frac{c_2}{z-p_2}$$
unde 
$$
\begin{aligned}
& c_{11}=\left.\frac{B(z)}{z-p_2}\right|_{z=p_1}\\&c_{12}=\left.\frac{\mathrm{d}}{\mathrm{d} z}\left[\frac{B(z)}{z-p_2}\right]\right|_{z=p_1} \\
&c_{13}=\left.\frac{\mathrm{d}^2}{\mathrm{~d} z^2}\left[\frac{B(z)}{z-p_2}\right]\right|_{z=p_1} \\
& c_2=\left.\frac{B(z)}{\left(z-p_1\right)^3}\right|_{z=p_2} 
\end{aligned}
$$
Variabilele de stare se adoptă conform algoritmului:

$$
\begin{aligned}
& X_4(z)=\frac{U(z)}{z-p_2}, z X_4(z)=p_2 X_4(z)+U(z), \\
& X_3(z)=\frac{U(z)}{z-p_1}, z X_3(z)=p_1 X_3(z)+U(z), \\
& X_2(z)=\frac{U(z)}{\left(z-p_1\right)^2}=\frac{X_3(z)}{z-p_1}, z X_2(z)=p_1 X_2(z)+X_3(z), \\
& X_1(z)=\frac{U(z)}{\left(z-p_1\right)^3}=\frac{X_2(z)}{z-p_1}, s X_1(z)=p_1 X_1(z)+X_2(z),
\end{aligned}
$$
de unde, după aplicarea TLI, rezultă sistemul de ecuaţii diferenţiale al reprezentării canonice diagonale cu poli multipli:

$$
\begin{aligned}
& x_1[k+1]=p_1 x_1[k]+x_2[k], \\
& x_2[k+1]=p_1 x_2[k]+x_3[k], \\
& x_3[k+1]=p_1 x_3[k]+u[k], \\
& x_4[k+1]=p_2 x_4[k]+u[k] .
\end{aligned}
$$

Ecuaţia ieşirii se deduce din expresia dezvoltării în fracţii simple în care se înlocuiesc variabilele de stare definite mai înainte:
$$

y[k]=c_{11} x_1[k]+c_{12} x_3[k]+c_{13} x_3[k]+c_2 x_4[k] \text {. }

$$
După identificarea cu forma matriceală generală rezultă matricele reprezentării canonice diagonale cu poli multipli:

$$
\boldsymbol{\Phi}=\left[\begin{array}{ccc|c}p_1 & 1 & 0 & 0 \\0 & p_1 & 1 & 0 \\0 & 0 & p_1 & 0 \\\hline 0 & 0 & 0 & p_2 \end{array}\right], \boldsymbol{\Gamma}=\left[\begin{array}{l}0 \\0 \\1 \\1\end{array}\right], \boldsymbol{C}=\left[\begin{array}{lll|}c_{11} & c_{12} & c_{13} \mid c_2\end{array}\right] 
$$
în care prin partiţionare sunt puse în evidenţă submatricele corespunzătoare polului multiplu.
Forma diagonală obţinută în acest caz se numeşte **forma Jordan**, iar submatricea:

$$
\boldsymbol{J}=\left[\begin{array}{ccc}
p_1 & 1 & 0 \\
0 & p_1 & 1 \\
0 & 0 & p_1
\end{array}\right],
$$
este numită **bloc sau minor Jordan**. Se observă că dimensiunea blocului Jordan este egală cu ordinul de multiplicitate al polului.


## Controlabilitate si observabilitate
### Controlabilitatea
Controlabilitatea unui sistem caracterizează capacitatea de modificare (de control) a întregului set de variabile de stare de către mărimea de intrare. 

>[!important] 
>Un sistem descris la stare de matricele $(\Phi, \Gamma)$ se spune că este controlabil dacă există o mărime de intrare $u[k]$ care poate transfera orice stare iniţială $x[0]$ în orice altă stare dorită $x[k]$. 
Pentru sistemul modelat la stare cu ecuaţia diferenţială matriceală $$\boldsymbol{x}[k+1]=\boldsymbol{\Phi} \boldsymbol{x}[k]+\boldsymbol{\Gamma} \boldsymbol{u}[k]$$

Proprietatea de controlabilitate se poate verifica analitic cu ajutorul matricei de controlabilitate care este de dimensiune $n \times n$, unde $n$ este ordinul sistemului (dimensiunea vectorului de stare).

Matematic sistemul considerat este controlabil dacă rang $\boldsymbol{P}=n$, condiţie care este îndeplinită dacă determinantul matricei de controlabilitate, $\boldsymbol{P}$ este diferit de zero.

O altă metodă de evaluare a controlabilităţii unui sistem foloseşte [[Grafuri de fluenta (semnal)|graful de fluenţă]] al modelului cu variabile de stare. 

>[!info] 
>În acest caz, sistemul este controlabil, dacă semnalul de intrare, $u[k]$, este conectat cu toate variabilele de stare, sau altfel spus, dacă în graf există căi de la mărimea de intrare la toate variabilele de stare. 

Un sistem modelat la stare cu variabile de fază este intotdeauna controlabil.

### Observabilitatea

Observabilitatea unui sistem caracterizează capacitatea de estimare a unei variabile de stare din valorile mărimii de ieşire. 

Spunem că un sistem este observabil, dacă mărimea de ieşire are componentele determinate (este influenţată) de toate variabilele de stare. 

Proprietatea de observabilitate poate fi, de asemenea, evaluată cu ajutorul [[Grafuri de fluenta (semnal)|grafurilor de fluenţă (semnal)]]. 

În acest caz se spune că un sistem este observabil dacă în graful de fluenţă există o cale între orice variabilă de stare şi mărimea de ieşire.

>[!important] 
>Un sistem este observabil daca, si numai daca, o stare initiala $x[0]$ poate fi determinata prin observaream pe un interval de timp finit $T$, a marimii de iesire $y[k]$ si a marimii de intrare $u[k]$. 

Consideram sistemul monovariabil descris de stare de relatiile matriceale:
$$x[k+1]=\Phi x[k]+\Gamma u[k], \quad \text{si} \quad y[k]=Cx[k]$$
unde $C$  este un vector linie, iar $x[k]$ este un vector coloana. SIstemul este observatil daca determinantul matricei de observabilitate

$$
Q=\begin{bmatrix}
C\\C
\Phi\\
\vdots\\
C \Phi^{n-1}
\end{bmatrix}_{n \times n}
$$
este diferita de 0 (sau rangul acesteia este *n*).

>[!info] 
>Un sistem care este descris in  forma controlabila cu variabile de faza este intotdeauna si observabil.




---
[[SAE_curs9.pdf]]

[^1]: In modelul matricial se presupune (asa cum se intampla de obicei in practica) ca matricea de transfer direct $D$ este nula.
[^2]: In practica, de obicei se alege $N=1$ sau $2$ 