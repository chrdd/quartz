---
tags:
  - TeoriaSistemelor2
---
#TeoriaSistemelor2 
## Introducere
În analiza şi proiectarea sistemelor de reglare s-au impus două abordări majore:
1. cu modele descrise prin funcții de transfer 
2. cu modele în spaţiul stărilor

Prima abordare cuprinde aşa numitele metode de analiză în domeniul frecvenţei care utilizează relaţii algebrice cu variabile complexe. Avantajul major al tehnicilor de analiză în domeniul frecvenţei rezultă din faptul că acestea furnizează, într-un mod direct, informaţii despre stabilitatea şi răspunsul tranzitoriu al sistemului.

Dezavantajele principale ale metodelor bazate pe funcţii de transfer sunt determinate în primul rând de aria limitată de aplicare. Aceste metode pot fi utilizate numai în cazul sistemelor liniare, invariante în timp cu o singură intrare şi ieşire.

Abordarea bazată pe reprezentarea în spaţiul stărilor cuprinde metode de analiză în domeniul timpului, care utilizează pentru modelarea sistemelor, seturi de ecuaţii diferenţiale de ordinul întâi. Este o abordare modernă, care se poate aplica unei game largi de sisteme.

De exemplu, abordarea în spaţiul stărilor poate fi utilizată pentru descrierea sistemelor neliniare (cu joc în transmisia mecanică, cu saturaţie sau zonă moartă), în analiza sistemelor cu condiţii iniţiale nenule sau cu coeficienţi variabili în timp.

Modelele cu variabile de stare pot fi, de asemenea, utilizate pentru analiza sistemelor cu mai multe mărimi de intrare şi ieşire (multivariabile).

Remarcăm faptul că cele două abordări nu se exclud reciproc existând diverse metode de conversie a modelelor cu variabile de stare în funcţii de transfer şi invers.

## Modele cu variabile de stare
Variabila de stare este o variabila interna a sistemului dinamic, notata in general $x_i(t)$, cu $i=1,2,...,n$, care poseda proprietatile urmatoare:
- este o functie continua in timp
- are capacitatea de a memora evolutia sistemului
- nu este unic definita

Nu este obligatoriu ca variabilele de stare sa fie marimi masurabile ale procesului fizic.

### Starea unui sistem dinamic
Starea unui sistem dinamic este setul minim de variabile de stare care caracterizeaza complet comportarea dinamica a sistemului.

Starea unui sistem dinamic la momentul $t$ este determinata unic daca se cunoaste starea de la momentul $t_0$ ($t \geq t_0$) si variatia marimii de intrare in intervalul $(t_0,t)$ (de obicei $t_0$ este egal cu 0).

#### Vectorul de stare
Vectorul de stare este notat astfel:
$$x(t)=[x_1(t)x_2(t)\ldots x_n(t)]^T$$
unde indicele $T$ specifica operatia de transpunere.

Daca sistemul dinamic are mai multe marimi de intrare (de exemplu $m$) si de iesire (de exemplu $r$), se vor defini vectorul intrarilor si vectorul iesirilor astfel:
$$u(t)=[u_1(t)u_2(t) \ldots u_m(t)]^T$$
$$y(t)=[y_1(t)y_2(t) \ldots y_r(t)]^T$$
Cunoscand aceste notatii sistemul multivariabil din figura *a)* se poate reprezenta ca in figura $b)$

![[Pasted image 20230308111543.png]]

#### Spatiul starilor
Spatiul starilor este un spatiu n-dimensional ale carui axe de coordonate sunt variabile de stare $x_1 \ldots x_n$.

Fiecare stare a sistemului (caracterizat de vectorul $x(t)$) va fi reprezentat in spatiul starilor printr-un punct.

Comportarea dinamica a unui sistem liniar invariat in timp va fi descrisa de ecuatiile matriceale:
$$\dot{x(t)}=Ax(t)+Bu(t)$$
$$y(t)=Cx(t)+Du(t)$$
unde:
$$\dot{x(t)}=\left[  \frac{dx_1(t)}{dt}\frac{dx_2(t)}{dt} \ldots \frac{dx_n(t)}{dt} \right]^T$$
>[!note] Observatie
>Relatia $\dot{x(t)}=Ax(t)+Bu(t)$ constituie un sistem de ecuatii diferentiale de ordinul 1, numita **ecuatie de stare** a sistemului, iar relatia $y(t)=Cx(t)+Du(t)$ este numita **ecuatie a iesirii**. Acestea pot fi reprezentate grafic prin urmatoarea schema bloc:
>![[Pasted image 20230309153318.png]]
#### Matricile sistemului

Matricea $A$ cu dimensiunea $n \times n$ este numita *matricea starii* sau *matricea sistemului* 
Matricea $B$ cu dimensiunea  $n \times m$ este *matricea intrarilor*.
Matricea $C$ cu dimensiunea $r \times n$ reprezinta *matricea iesirilor*.

## Conversia modelelor din spatiul starilor in [[Functii de transfer#Definitie|functii de transfer]]
Formula generala este:
$$
\boldsymbol{G}(s)=\frac{\boldsymbol{Y}(s)}{U(s)}=\boldsymbol{C} \Phi(s) \boldsymbol{B}+\boldsymbol{D}
$$
Aceasta este similara cu o functie de transfer, motiv pentru care matricea $\boldsymbol{C} \boldsymbol{\Phi}(s) \boldsymbol{B}+\boldsymbol{D}$ este numită **matricea (funcțiilor) de transfer a sistemului multivariabil la intrare şi ieşire**.

În cazul sistemelor cu o singură intrare şi ieşire (monovariabile) $C$ este un vector linie, $B$ un vector coloană, iar $\boldsymbol{D}$ un scalar.

În aceste condiţii $\boldsymbol{C} \boldsymbol{\Phi}(s) B$ va fi, de asemenea un scalar şi ecuatia reprezinta functia de transfer uzuala.

>[!info] Observatie
>Polinomul caracteristic al funcției sau matricei de transfer este determinat numai de matricea $\boldsymbol{A}$, fiind egal cu $\operatorname{det}(\boldsymbol{s} \mathbf{l}-\boldsymbol{A})$.


### Explicatie matematica
Relația generală de conversie a unui model din spațiul stărilor într-o funcție de transfer se determină pornind de la ecuațiile de stare şi ieşire scrise sub formă matriceală
$$
\begin{aligned}
& \dot{\boldsymbol{x}}(t)=\boldsymbol{A} \boldsymbol{x}(t)+\boldsymbol{B} \boldsymbol{u}(t), \\
& \boldsymbol{y}(t)=\boldsymbol{C} \boldsymbol{x}(t)+\boldsymbol{D} \boldsymbol{u}(t) .
\end{aligned}
$$
Prin aplicarea [[Transformata Laplace|transformatei Laplace]] în ipoteza condiţiilor inițiale nule se obţine:
$$
\begin{aligned}
& s \boldsymbol{X}(s)-\underbrace{\boldsymbol{X}(0)}_{=0}=\boldsymbol{A X}(s)+\boldsymbol{B} U(s), \\
& \boldsymbol{Y}(s)=\boldsymbol{C X}(s)+\boldsymbol{D} \boldsymbol{( s )},
\end{aligned}
$$
unde $\boldsymbol{U}(s), \boldsymbol{X}(s)$ şi $\boldsymbol{Y}(s)$ sunt vectorii [[Transformata Laplace|transformatelor Laplace]] ale mărimilor de intrare, stare şi ieşire.

Rezolvând în raport cu $\boldsymbol{X}(s)$ prima ecuaţie rezultă :
$$
(s I-A) X(s)=\boldsymbol{B U}(s)
$$
sau
$$
\boldsymbol{X}(s)=(s \mathbf{I}-\boldsymbol{A})^{-1} \boldsymbol{B} U(s)=\boldsymbol{\Phi}(s) \boldsymbol{B} U(s),
$$
unde $\Phi(s)=(s \mathrm{~s}-\boldsymbol{A})^{-1}$ de dimensiune $n \times n$, se numeşte **matrice fundamentală a sistemului modelat la stare**. Reamintim că:
$$
\boldsymbol{\Phi}(s)=(s \mathbf{I}-\boldsymbol{A})^{-1}=\frac{\operatorname{adj}(s \mathbf{I}-\boldsymbol{A})}{\operatorname{det}(s \mathbf{I}-\boldsymbol{A})}
$$
Se înlocuieşte $\boldsymbol{X}(s)$ şi astfel se obține:
$$
\boldsymbol{Y}(s)=\boldsymbol{C} \Phi(s) \boldsymbol{B} \boldsymbol{U}(s)+\boldsymbol{D} U(s)=[\boldsymbol{C} \Phi(s) \boldsymbol{B}+\boldsymbol{D}] \boldsymbol{U}(s) \text {, }
$$
de unde rezultă:
$$
\boldsymbol{G}(s)=\frac{\boldsymbol{Y}(s)}{U(s)}=\boldsymbol{C} \Phi(s) \boldsymbol{B}+\boldsymbol{D}
$$

## Raspunsul in timp al sistemelor modelate in spatiul starilor

Se determină prin rezolvarea ecuaţiei diferenţiale matriceale, respectiv a sistemului de $n$ ecuaţii diferenţiale de ordinul întâi. Soluţia se poate obţine într-un mod similar cu abordarea utilizată la rezolvarea unei ecuaţii diferenţiale de ordinul întâi. Considerăm în acest sens o ecuaţie diferenţială:
$$
\frac{\mathrm{d} x}{\mathrm{~d} t}=a x+b u
$$
unde $x(t)$ şi $u(t)$ sunt funcţii scalare de timp.
Aplicând [[Transformata Laplace|transformata Laplace]] ecuaţiei diferenţiale în condiţii iniţiale nenule pentru variabila de stare, se obţine:
$$
s X(s)-x(0)=a X(s)+b U(s)
$$
de unde rezultă :
$$
X(s)=\frac{x(0)}{s-a}+\frac{b}{s-a} U(s)
$$
Funcţia scalară de timp, $x(t)$, se determină cu [[Transformata Laplace|transformata Laplace]] inversă având în vedere că :
$$\mathbf{L}^{-1}\left\{\frac{x(0)}{s-a}\right\}=x(0) \mathrm{e}^{a t}$$
şi
$$\mathbf{L}^{-1}\left\{\frac{b}{s-a} U(s)\right\}=b e^{a t} * u(t)$$
unde simbolul * specifică produsul de convoluţie al funcţiilor $u(t)$ şi $\mathrm{e}^{a t}$ (operaţie comutativă).
Scriind explicit produsul de convoluţie se obţine soluţia ecuaţiei diferenţiale:
$$
x(t)=e^{a t} x(0)+\int_0^t e^{a(t-\tau)} b u(\tau) d \tau
$$
Procedând în mod similar pentru ecuaţia matriceală de stare:
$$
\dot{\boldsymbol{x}}(t)=\boldsymbol{A} \boldsymbol{x}(t)+\boldsymbol{B} \boldsymbol{u}(t)
$$
prin generalizarea formală a relaţiei obţinute pentru o ecuaţie diferenţială, se poate considera că răspunsul modelului cu variabile de stare este :
$$
\boldsymbol{x}(t)=\mathrm{e}^{\boldsymbol{A t}} \boldsymbol{x}(0)+\int_0^t \mathrm{e}^{\boldsymbol{A}(t-\tau)} \boldsymbol{B} \boldsymbol{u}(\tau) \mathrm{d} \tau=\boldsymbol{x}_n(t)+\boldsymbol{x}_f(t)
$$
Prima componentă, $\boldsymbol{x}_n(t)$ este răspunsul natural (liber) iar a doua $\boldsymbol{x}_f(t)$ reprezintă răspunsul forţat la stare produs de mărimea de intrare.
Funcţia matriceală $\mathrm{e}^{A t}$ se poate calcula folosind dezvoltarea în serie (vezi AnexaC):
$$
\mathrm{e}^{\boldsymbol{A} t}=\exp (\boldsymbol{A} t)=\mathbf{I}+\boldsymbol{A} t+\frac{\boldsymbol{A}^2 t^2}{2 !}+\ldots+\frac{\boldsymbol{A}^k t^k}{k !}+\ldots
$$
care este convergentă pentru orice $t$ finit.
Exponenţiala matriceală se notează de obicei :
$\boldsymbol{\varphi}(t)=\exp (\boldsymbol{A} t)$
unde $\boldsymbol{\varphi}(t)$ este o matrice pătrată de funcţii de timp numită matricea de tranziţie a stărilor. Din definiţie rezultă următoarele proprietăţi mai importante ale matricei de tranziţie a stărilor:
$$
\begin{aligned}
& -\boldsymbol{\varphi}(0)=\mathbf{I} \\
& -\boldsymbol{\varphi}^{-1}(t)=\boldsymbol{\varphi}(-t) \\
& -\boldsymbol{\varphi}\left(t-t_1\right) \boldsymbol{\varphi}\left(t_1-t_0\right)=\boldsymbol{\varphi}\left(t-t_0\right) .
\end{aligned}
$$
$\mathrm{O}$ altă cale pentru calculul matricei de tranziţie a stărilor rezultă aplicând [[Transformata Laplace|transformata Laplace]] ecuaţiei de stare (vezi şi secţiunea anterioară) în condiţii iniţiale nule. Se obţine astfel relaţia:
$$
\boldsymbol{X}(s)=(s \mathrm{I}-\boldsymbol{A})^{-1} \boldsymbol{x}(0)+(s \mathrm{I}-\boldsymbol{A})^{-1} \boldsymbol{B} U(s)=\boldsymbol{\Phi}(s) \boldsymbol{x}(0)+\boldsymbol{\Phi}(s) \boldsymbol{B} U(s),
$$
de unde după aplicarea [[Transformata Laplace#^883856|transformatei Laplace inverse]] se observă că:
$$
\boldsymbol{\varphi}(t)=\mathbf{L}^{-1}\left\{(s \mathbf{I}-\boldsymbol{A})^{-1}\right\}=\mathbf{L}^{-1}\{\boldsymbol{\Phi}(s)\}
$$
deci matricea de tranziţie a stărilor este egală cu TLI a matricei fundamentale $\boldsymbol{\Phi}(s)$. Din cele prezentate se obţine rezultatul remarcabil exprimat prin relaţia:
$$
\boldsymbol{\varphi}(t)=\exp (\boldsymbol{A} t)=\mathbf{L}^{-1}\left\{(s \mathbf{I}-\boldsymbol{A})^{-1}\right\}
$$
şi prin urmare răspunsul în timp al sistemelor modelate în spaţiul stărilor poate fi scris conform expresiei:
$$
\boldsymbol{x}(t)=\boldsymbol{\varphi}(t) \boldsymbol{x}(0)+\int_0^t \boldsymbol{\Phi}(t-\tau) \boldsymbol{B} U(\tau) \mathrm{d} \tau
$$
## Conversia functiilor de transfer in modele cu variabile de stare

Aşa cum s-a menţionat variabilele de stare nu sunt unic definite. Teoretic vorbind există posibilitatea de a obţine un număr nelimitat de modele în spaţiul stărilor pornind de la o anumită funcţie de transfer. 

Vom numi realizare în spaţiul stărilor un model cu variabile de stare care se deduce pornind de la o funcție de transfer dată. Modelele diferite cu variabile de stare care se determină pornind de la aceeaşi funcţie de transfer se numesc **realizări** sau **forme echivalente**. 

În literatură s-au impus trei tipuri de realizări cu variabile de stare numite realizări (forme) standard:
1.  complet controlabilă (alternativ cu variabile de fază);
2.  complet observabilă;
3. canonică diagonală;

### Realizarea complet controlabilă
#### Varianta de bază
Există diverse modalităţi pentru obţinerea acestei realizări. Vom ilustra deducerea acestei forme folosind cazul particular al funcţiei de transfer:
$$
G(s)=\frac{Y(s)}{U(s)}=\frac{b_2 s^2+b_1 s+b_0}{s^3+a_2 s^2+a_1 s+a_0}
$$
Se introduce variabila auxiliară, $X(s)$, care se defineşte conform relaţiei:
$$
\frac{Y(s)}{X(s)} \cdot \frac{X(s)}{U(s)}=\left(b_2 s^2+b_1 s+b_0\right) \cdot \frac{1}{s^3+a_2 s^2+a_1 s+a_0},
$$
de unde rezultă :
$$
\frac{X(s)}{U(s)}=\frac{1}{s^3+a_2 s^2+a_1 s+a_0}
$$
şi
$$
\frac{Y(s)}{X(s)}=b_2 s^2+b_1 s+b_0
$$
care se pot scrie conform expresiilor
$$
\left(s^3+a_2 s^2+a_1 s+a_0\right) X(s)=U(s)
$$
şi
$$
Y(s)=\left(b_2 s^2+b_1 s+b_0\right) \times(s) \text {. }
$$
Aplicăm TLI ecuaţiei în condiţii iniţiale nule şi având în vedere că:
$\mathbf{L}^{-1}\{U(s)\}=u(t), \mathbf{L}^{-1}\{X(s)\}=x(t)$
$\mathbf{L}^{-1}\{s X(s)\}=\frac{d x}{d t}, L^{-1}\left\{s^2 X(s)\right\}=\frac{d^2 x}{d t^2}, L^{-1}\left\{s^3 X(s)\right\}=\frac{d^3 x}{d t^3}$
se obţine ecuaţia diferenţială :
$$
\frac{\mathrm{d}^3 x}{\mathrm{~d} t^3}+a_2 \frac{\mathrm{d}^2 x}{\mathrm{~d} t^2}+a_1 \frac{\mathrm{d} x}{\mathrm{~d} t}+a_0 x=u
$$
Definim acum variabilele de stare conform schemei:
$$
\begin{aligned}
& x_1=x, \\
& x_2=\frac{d x}{d t}=\dot{x}_1, \\
& x_3=\frac{d^2 x}{d t^2}=\frac{d}{d t}\left(\frac{d x}{d t}\right)=\dot{x}_2,
\end{aligned}
$$
şi folosim ecuaţia diferenţială (6.20) pentru a obţine derivata ultimei mărimi de stare:
$$
\frac{\mathrm{d}^3 x}{\mathrm{~d} t^3}=\frac{\mathrm{d}}{\mathrm{d} t}\left(\frac{\mathrm{d}^2 x}{\mathrm{~d} t^2}\right)=\dot{x}_3=-a_2 x_3-a_1 x_2-a_0 x_1+u \text {, }
$$
Rezultă astfel sistemul de ecuaţii de stare exprimat conform relaţiilor:
$$
\begin{aligned}
& \dot{x}_1=x_2, \\
& \dot{x}_2=x_3, \\
& \dot{x}_3=-a_2 x_3-a_1 x_2-a_0 x_1+u .
\end{aligned}
$$
Ecuaţia ieşirii pentru modelul cu variabile de stare se deduce în baza relaţiei (6.19b), scrisă în domeniul timpului pentru condiţii iniţiale nule:

$$
y(t)=\mathrm{L}^{-1}\left\{b_2 s^2 X(s)+b_1 s X(s)+b_0 X(s)\right\}=b_2 \frac{\mathrm{d}^2 x}{\mathrm{~d} t^2}+b_1 \frac{\mathrm{d} x}{\mathrm{~d} t}+b_0 x,
$$
de unde având în vedere relaţiile de definiţie ale variabilelor de stare rezultă:
$$
y=b_2 x_3+b_1 x_2+b_0 x_1 \text {. }
$$
În concluzie modelul corespunzător formei complet controlabile este:
$$
\begin{aligned}
& \dot{x}_1=x_2 \\
& \dot{x}_2=x_3 \\
& \dot{x}_3=-a_0 x_1-a_1 x_2-a_2 x_3+u \\
& y=b_0 x_1+b_1 x_2+b_2 x_3
\end{aligned}
$$
de unde prin identificare cu forma matriceală rezultă:
$$
\boldsymbol{A}=\left[\begin{array}{ccc}
0 & 1 & 0 \\
0 & 0 & 1 \\
-a_0 & -a_1 & -a_2
\end{array}\right], \boldsymbol{B}=\left[\begin{array}{l}
0 \\
0 \\
1
\end{array}\right], \boldsymbol{C}=\left[\begin{array}{lll}
b_0 & b_1 & b_2
\end{array}\right]
$$
Variabilele de stare obţinute conform schemei prezentate se numesc variabile de fază. Generalizând rezultatul pentru o funcţie de transfer de ordinul $\boldsymbol{n}$ :
$$
G(s)=\frac{Y(s)}{U(s)}=\frac{b_{n-1} s^{n-1}+\ldots+b_1 s+b_0}{s^n+a_{n-1} s^{n-1}+\ldots+a_1 s+a_0}
$$
modelul la stare în forma controlabilă va fi descris de matricele:
$$
\begin{aligned}
\boldsymbol{A} & =\left[\begin{array}{ccccccc}
0 & 1 & 0 & 0 & \cdots & 0 & 0 \\
0 & 0 & 1 & 0 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \vdots & \cdots & \vdots & \vdots \\
0 & 0 & 0 & 0 & \cdots & 0 & 1 \\
-a_0 & -a_1 & -a_2 & -a_3 & \cdots & -a_{n-2} & -a_{n-1}
\end{array}\right]_{(n \times n)} \quad, \boldsymbol{B}=\left[\begin{array}{c}
0 \\
0 \\
\vdots \\
1
\end{array}\right]_{(n \times 1)}, \\
\boldsymbol{C} & =\left[\begin{array}{lllll}
b_0 & b_1 & \cdots & b_{n-1}
\end{array}\right]_{(1 \times n)} .
\end{aligned}
$$

Matricea $\boldsymbol{A}$ cu forma prezentată mai înainte se mai numeşte **matrice companion inferioară** 
#### Variantă pentru realizarea complet controlabilă
Realizarea complet controlabilă este prezentată, în unele lucrări din domeniu inclusiv în MATLAB, cu expresii modificate pentru tripletul matriceal $\boldsymbol{A}, \boldsymbol{B}, \boldsymbol{C}$, respectiv pentru relaţiile $(6.26 a, b, c$ sau $6.28 a, b, c)$
Vom ilustra această variantă a formei complet controlabile utilizând, de asemenea, cazul particular al funcţiei de transfer:
$$
G(s)=\frac{Y(s)}{U(s)}=\frac{b_2 s^2+b_1 s+b_0}{s^3+a_2 s^2+a_1 s+a_0}=\frac{Y(s)}{X(s)} \frac{X(s)}{U(s)}=\left(b_2 s^2+b_1 s+b_0\right) \frac{1}{s^3+a_2 s^2+a_1 s+a_0}
$$
În prima etapă se procedează în acelaşi mod ca la forma de bază. Se introduce variabila auxiliară $X(s)$ şi după aplicarea TLI se obţin ecuaţile diferenţiale
$$
\frac{\mathrm{d}^3 x}{\mathrm{~d} t^3}+a_2 \frac{\mathrm{d}^2 x}{\mathrm{~d} t^2}+a_1 \frac{\mathrm{d} x}{\mathrm{~d} t}+a_0 x=u
$$
şi
$$
y=b_2 \frac{\mathrm{d}^2 x}{\mathrm{~d} t^2}+b_1 \frac{\mathrm{d} x}{\mathrm{~d} t}+b_0 x
$$
Variabilele de stare se aleg însă acum conform algoritmului
$$
\begin{aligned}
& x_3=x, \\
& x_2=\frac{d x}{d t}=\dot{x}_3, \\
& x_1=\frac{d^2 x}{d t^2}=\dot{x}_2 .
\end{aligned}
$$
Substituind variabilele de stare astfel definite în cele două ecuaţii diferenţiale se obţine:
$$
\dot{x}_1+a_2 x_1+a_1 x_2+a_0 x_3=u
$$
şi
$$
y=b_2 x_1+b_1 x_2+b_0 x_3 \text {. }
$$
Din cele prezentate rezultă modelul cu variabile de stare pentru varianta formei complet controlabile descris de ecuaţiile:
$$
\begin{array}{ll}
\dot{x}_1=-a_2 x_1-a_1 x_2-a_0 x_3+u, & \text { (6.29a) } \\
\dot{x}_2=x_1, & \text { (6.29b) } \\
\dot{x}_3=x_2, & \text { (6.29c) } \\
y=b_2 x_1+b_1 x_2+b_0 x_3, & \text { (6.29d) }
\end{array}
$$
de unde, prin identificare cu forma matriceală generală, vom obţine matricele:
$$
\boldsymbol{A}=\left[\begin{array}{ccc}
-a_2 & -a_1 & -a_0 \\
1 & 0 & 0 \\
0 & 1 & 0
\end{array}\right], \boldsymbol{B}=\left[\begin{array}{l}
1 \\
0 \\
0
\end{array}\right], \boldsymbol{C}=\left[\begin{array}{lll}
b_2 & b_1 & b_0
\end{array}\right] . \quad(6.30 a, b, c)
$$
>[!info] Observatie
>Modelul dedus mai înainte se poate obţine direct dacă se fac substituţiile :$x_1\rightarrow x_3, x_2 \rightarrow x_2, x_3 \rightarrow x_1 \text {, }$în sistemul de ecuaţii de stare şi ieşire al variantei de bază.
### Realizarea complet observabilă
Se introduce pornind de la forma complet controlabilă, folosind proprietatea de echivalenţă a celor două realizări. În baza acestei proprietăţi cele două forme, complet controlabilă şi complet observabilă, au aceeaşi funcţie de transfer, $G(s)$. Pentru simplitatea expunerii considerăm din nou cazul particular al funcției de transfer de ordinul trei :
$$
G(s)=\frac{b_2 s^2+b_1 s+b_0}{s^3+a_2 s^2+a_1 s+a_0}
$$
Din secțiunea precedentă cunoaştem că, în acest caz, forma complet controlabilă este descrisă la stare de matricele:
$$
\boldsymbol{A}=\left[\begin{array}{ccc}
0 & 1 & 0 \\
0 & 0 & 1 \\
-a_0 & -a_1 & -a_2
\end{array}\right], \boldsymbol{B}=\left[\begin{array}{l}
0 \\
0 \\
1
\end{array}\right], \boldsymbol{C}=\left[\begin{array}{lll}
b_0 & b_1 & b_2
\end{array}\right], \text { şi } G(s)=\boldsymbol{C}(s \mathbf{I}-\boldsymbol{A})^{-1} \boldsymbol{B}
$$
Deoarece $G(s)$ este o functiie scalară avem proprietatea:
$$
G(s)=G^{\top}(s)=\left[C(s \mathbf{l}-A)^{-1} B\right]^{\top}
$$
unde indicele superior $\mathrm{T}$ specifică operaţia de transpunere matriceală.
Având în vedere proprietatea de transpunere a unui produs matriceal (vezi Anexa C) se poate scrie în continuare:
$$
G(s)=G^{\top}(s)=\boldsymbol{B}^{\top}\left[(s \mathbf{I}-\boldsymbol{A})^{-1}\right]^{\top} \boldsymbol{C}^{\top}=\boldsymbol{B}^{\top}\left(s \mathbf{I}-\boldsymbol{A}^{\top}\right)^{-1} \boldsymbol{C}^{\top}=\boldsymbol{C}_{\circ}\left(s \mathbf{I}-\boldsymbol{A}_{\circ}\right)^{-1} \boldsymbol{B}_{\circ}
$$
unde $\boldsymbol{A}_o, \boldsymbol{B}_{\mathrm{o}}, \boldsymbol{C}_o$ reprezintă noile matrice ale formei complet observabile care rezultă prin identificarea din ultima egalitate conform expresiilor:
$$
\begin{aligned}
& \boldsymbol{A}_o=\boldsymbol{A}^{\top}=\left[\begin{array}{ccc}
0 & 1 & 0 \\
0 & 0 & 1 \\
-a_0 & -a_1 & -a_2
\end{array}\right]^{\top}=\left[\begin{array}{lll}
0 & 0 & -a_0 \\
1 & 0 & -a_1 \\
0 & 1 & -a_2
\end{array}\right]^{\top}, \\
& \boldsymbol{B}_0=\boldsymbol{C}^{\top}=\left[\begin{array}{lll}
b_0 & b_1 & b_2
\end{array}\right]^{\top}=\left[\begin{array}{l}
b_0 \\
b_1 \\
b_2
\end{array}\right], \boldsymbol{C}_0=\boldsymbol{B}^{\top}=\left[\begin{array}{l}
0 \\
0 \\
1
\end{array}\right]^{\top}=\left[\begin{array}{lll}
0 & 0 & 1
\end{array}\right] .
\end{aligned}
$$
În consecinţă modelul corespunzător formei complet observabile este descris de ecuaţiile:
$$
\begin{aligned}
& \dot{x}_1=-a_0 x_3+b_0 u, \\
& \dot{x}_2=x_1-a_1 x_3+b_1 u, \\
& \dot{x}_3=x_2-a_2 x_3+b_2 u, \\
& y=x_3 .
\end{aligned}
$$
Generalizând rezultatul pentru o funcţie de transfer de ordinul $n$ se obţine modelul la stare în forma complet observabilă descris de matricele (se renunţă la scrierea indicelui inferior 0 ):
$$
\boldsymbol{A}=\left[\begin{array}{cccccc}
0 & 0 & . & . & 0 & -a_0 \\
1 & 0 & \cdots & . & 0 & -a_1 \\
0 & 1 & . & . & 0 & -a_2 \\
. & . & . & . & . & . \\
0 & 0 & . & . & 1 & -a_{n-1}
\end{array}\right]_{n \times n}, \boldsymbol{B}=\left[\begin{array}{c}
b_0 \\
b_1 \\
. \\
. \\
\cdot \\
b_{n-1}
\end{array}\right]_{n \times 1}, \boldsymbol{C}=\left[\begin{array}{llllll}
0 & 0 & . & . & 0 & 1
\end{array}\right]_{1 \times n}
$$
### Realizarea canonică diagonală
Se deduce pornind de la funcția de transfer scrisă cu polinomul caracteristic sub formă factorizată. Considerăm mai întâi cazul în care funcţia de transfer are poli distincţi. Funcţia de transfer se descompune în fracţii simple:
$$
\frac{Y(s)}{U(s)}=\frac{B(s)}{\left(s+p_1\right)\left(s+p_2\right) \ldots\left(s+p_n\right)}=\frac{c_1}{s+p_1}+\frac{c_2}{s+p_2}+\ldots+\frac{c_n}{s+p_n}
$$
unde $c_j=\left[\left(s+p_j\right) \frac{B(s)}{A(s)}\right]_{s=-p_j}$, cu $A(s)=\left(s+p_1\right)\left(s+p_2\right) \ldots\left(s+p_n\right)$.
Variabilele de stare se definesc iniţial cu relațiile:
$$
X_j(s)=\frac{1}{s+p_j} U(s), j=1,2, \ldots, n \text {, }
$$
scrise apoi conform expresiilor :
$$
s X_j(s)=-p_j X_j(s)+U(s), j=1,2, \ldots, n \text {, }
$$
de unde, prin aplicarea TLI, rezultă ecuaţiile de stare :
$$
\begin{gathered}
\dot{x}_1=-p_1 x_1+u, \\
\dot{x}_2=-p_2 x_2+u, \\
\ldots \ldots \ldots \ldots \ldots \ldots \ldots \\
\dot{x}_n=-p_n x_n+u .
\end{gathered}
$$
Ecuaţia ieşirii se obţine din descompunerea în fracţii simple fiind conform relaţiei:
$$
y=c_1 x_1+c_2 x_2+\cdots+c_n x_n
$$
Modelul cu variabile de stare în forma diagonală este descris de matricele:
$$
\boldsymbol{A}=\left[\begin{array}{ccccc}
-p_1 & 0 & \cdots & 0 & 0 \\
0 & -p_2 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
0 & 0 & \cdots & -p_{n-1} & 0 \\
0 & 0 & \cdots & 0 & -p_n
\end{array}\right], \boldsymbol{B}=\left[\begin{array}{c}
1 \\
1 \\
\vdots \\
1
\end{array}\right], \boldsymbol{C}=\left[\begin{array}{llll}
c_1 & c_2 & \cdots & c_n
\end{array}\right] . \quad(6.35 \mathrm{a}, \mathrm{b}, \mathrm{c})
$$
unde $-p_j$ sunt toţi polii distincţi iar $c_j$ reprezintă coeficienţii dezvoltării în fracţii simple a funcţiei de transfer $G(s)$.
Un caz special apare când $G(s)$ conţine poli multipli. Considerăm pentru simplitate cazul unei funcţii de transfer de ordinul patru cu un pol triplu, exprimată conform relatiei:
$$
\frac{Y(s)}{U(s)}=G(s)=\frac{B(s)}{\left(s+p_1\right)^3\left(s+p_2\right)} .
$$
În această situaţie dezvoltarea în fracţii simple va fi:
$$
\frac{Y(s)}{U(s)}=\frac{c_{11}}{\left(s+p_1\right)^3}+\frac{c_{12}}{\left(s+p_1\right)^2}+\frac{c_{13}}{s+p_1}+\frac{c_2}{s+p_2},
$$
unde
$$
\begin{aligned}
& c_{11}=\left.\frac{B(s)}{s+p_2}\right|_{s=-p_1}, c_{12}=\left.\frac{d}{d s}\left[\frac{B(s)}{s+p_2}\right]\right|_{s=-p_1}, c_{13}=\left.\frac{d^2}{d s^2}\left[\frac{B(s)}{s+p_2}\right]\right|_{s=-p_1}, \\
& c_2=\left.\frac{B(s)}{\left(s+p_1\right)^3}\right|_{s=-p_2} .
\end{aligned}
$$
Variabilele de stare se adoptă conform algoritmului:
$$
X_4(s)=\frac{U(s)}{s+p_2}, s X_4(s)=-p_2 X_4(s)+U(s)
$$


$$
\begin{aligned}
& X_3(s)=\frac{U(s)}{s+p_1}, s X_3(s)=-p_1 X_3(s)+U(s) \\
& X_2(s)=\frac{U(s)}{\left(s+p_1\right)^2}=\frac{X_3(s)}{s+p_1}, s X_2(s)=-p_1 X_2(s)+X_3(s) \\
& X_1(s)=\frac{U(s)}{\left(s+p_1\right)^3}=\frac{X_2(s)}{s+p_1}, s X_1(s)=-p_1 X_1(s)+X_2(s)
\end{aligned}
$$
de unde, după aplicarea TLI, rezultă sistemul de ecuaţii diferenţiale al reprezentării canonice diagonale cu poli multipli:
$$
\begin{array}{ll}
\dot{x}_1=-p_1 x_1+x_2,  \\
\dot{x}_2=-p_1 x_2+x_3,  \\
\dot{x}_3=-p_1 x_3+u,  \\
\dot{x}_4=-p_2 x_4+u
\end{array}
$$
Ecuaţia ieşirii se deduce din expresia dezvoltării în fracţii simple în care se înlocuiesc variabilele de stare definite mai înainte:
$$
y=c_{11} x_1+c_{12} x_3+c_{13} x_3+c_2 x_4 \text {. }
$$
După identificarea cu forma matriceală generală rezultă matricele reprezentării canonice diagonale cu poli multipli:
$$
\boldsymbol{A}=\left[\begin{array}{ccc|c}
-p_1 & 1 & 0 & 0 \\
0 & -p_1 & 1 & 0 \\
0 & 0 & -p_1 & 0 \\
\hline 0 & 0 & 0 & -p_2
\end{array}\right], \boldsymbol{B}=\left[\begin{array}{l}
0 \\
0 \\
\frac{1}{1}
\end{array}\right], \boldsymbol{C}=\left[\begin{array}{llll}
c_{11} & c_{12} & c_{13} \mid c_2
\end{array}\right] . \quad(6.37 a, b, c)
$$
în care prin partiţionare sunt puse în evidenţă submatricele corespunzătoare polului multiplu.
Forma diagonală obţinută în acest caz se numeşte **forma Jordan**, iar submatricea:
$$
\boldsymbol{J}=\left[\begin{array}{ccc}
-p_1 & 1 & 0 \\
0 & -p_1 & 1 \\
0 & 0 & -p_1
\end{array}\right] \text {, }
$$
este numită **bloc** sau **minor Jordan**. Se observă că dimensiunea blocului Jordan este egală cu ordinul de multiplicitate al polului.


---
[[TS2_curs1.pdf]]
[[TS2_curs2.pdf]]