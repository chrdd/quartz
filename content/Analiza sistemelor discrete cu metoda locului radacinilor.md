---
tags:
  - SistemeAutomateCuEsantionare
aliases:
  - Curs 13 SAE
---

Metoda locului radacinilor poate fi aplicata cu usurinta si in cazul sistemelor cu esantionare. 

In aplicarea metodei pornim de la functia de transfer $z$ a sistemului deschis. 

Consideram sistemul cu esantionare a erorii urmator:

![[Pasted image 20240809170245.png]]

[[Functii de transfer|Functia de transfer]] $z$ a sistemului inchis este: [^1]

$$\frac{Y(z)}{R(z)}=\frac{G(z)}{1+GH(z)}$$

Radacinile sistemului inchis, care ofera informatia necesara pentru evaluarea stabilitatii sistemului discret de reglare, sunt determinate exclusiv de ecuatia caracteristica a sistemului:

$$1+GH(z)=0$$

Deoarece $GH(z)$ este o functie cu valori complexe, ecuatia caracteristica poate fi scrisa sub forma echivalenta:

$$GH(z)=|GH(z)|e^{j \varphi}=1 \cdot e^{j(2k+1)\pi}$$

de unde, din egalarea modulului si argumentului din ambii membrii, rezulta conditia mmodulului:

$$|GH(z)|=1$$

si conditia argumentului:

$$\varphi=\angle GH(z) = \pm 180(2k+1), \quad k=0,1,\ldots$$

Valorile lui $z$ care indeplinesc conditiile modulului si argumentului sunt radacinile ecuatiei caracteristice sau polii sistemului in circuit inchis.

Pentru ca un punct sa apartina locului radacinilor, este insa suficienta indeplinirea uneia dintre cele 2 conditii. Prin urmare, reprezentarea grafica a punctelor din planul complex, care satisfac,d de exemplu, numai conditia fazei este de fapt locul radacinilor pentru sistemul in circuit inchis. Valorile radacinilor ecuatiei caracteristice (polii sistemului in circuit inchis) care corespund unei valori date a factorului de amplificare se pot determina din conditia modului. 

In cele mai multe cazuri, factorul de amplificare $K$ prezinta un parametru al functiei de tranfer a sistemului deschis, $GH(z)$ si ecuatia caracteristica se poate scrie conform expresiei:

$$1+\frac{K(z-z_1)(z-z_2)\ldots(z-z_m)}{(z-p_1)(z-p_2)\ldots(z-p_n)}=0$$

Prin urmare, locul radacinilor este locul geometric al polilor sistemului inchis cand amplificarea $K$ se modifica de la $0$ la $\infty$.

>[!info] 
>Pentru a incepe desenarea locului radacinilor a unui sistem, trebuie sa cunoastem valorile polilor si zerourilor functiei $GH(z)$

## Reguli generale de trasare a locului rădăcinilor

Pentru [[Sisteme|sisteme]] complexe, cu mai multe singularităţi (poli şi zerouri), trasarea locului rădăcinilor este aparent complicată, dar, dacă se aplică sistematic o serie de reguli, construcţia grafică a locului rădăcinilor se simplifică mult. 

Astfel, prin amplasarea punctelor particulare şi a asimptotelor, după evaluarea unghiurilor de plecare (sosire) a ramurilor locului din polii complexi (în zerourile complexe) se poate schiţa fără dificultate forma de variaţie a locului rădăcinilor pentru un caz dat. 

Avantajele cel mai însemnate ale metodei locului rădăcinilor apar, de fapt, în cazul sistemelor de ordin ridicat pentru care găsirea polilor funcţiei de transfer în circuit închis cu alte metode este extrem de laborioasă.

Având în vedere că trasarea locului rădăcinilor are acelaşi regim de construcţie ca în cazul sistemelor continue, în continuare se vor prezenta, în rezumat, fără prea multe justificări, regulile generale de trasare a locului rădăcinilor pentru un sistem cu eşantionare închis cu reacţie negativă neunitară.

### Pasul 1: se determină ecuaţia caracteristică

$$1+G H(z)=0$$

care se aranjează astfel încât să se pună în evidenţă, parametrul care ne interesează, ca un factor multiplicativ, conform expresiei

$$1+\frac{K B(z)}{A(z)}=1+\frac{K\left(z-z_{1}\right)\left(z-z_{2}\right) \cdots\left(z-z_{m}\right)}{\left(z-p_{1}\right)\left(z-p_{2}\right) \cdots\left(z-p_{n}\right)}=0$$

În discuţia de faţă, vom presupune că parametrul considerat este factorul de amplificare $K$, unde $K>0$. Dacă se acceptă valori negative ale factorului de amplificare $(K<0)$, caz în care avem de fapt o reacţie pozitivă, va fi necesar să se modifice condiţia fazei (a argumentului).

### Pasul 2: se determină numărul ramurilor locului rădăcinilor care este egal cu $n$ (numărul polilor funcţiei de transfer a sistemului deschis)

Se plasează, în planul complex, polii şi zerourile funcţiei $G H(z)$. Polii se marchează cu un $\times$ iar zerourile cu un o. Locul rădăcinilor începe în polii sistemului deschis şi se termină în zerouri (cu valoare finită sau la infinit).

### Pasul 3: la stânga unui număr impar de poli reali plus zerori reale, se desenează locul rădăcinilor de pe axa reală

### Pasul 4: se desenează asimptotele ramurilor locului rădăcinilor

- Numărul asimptotelor este egal cu $n-m$; - Unghiurile asimptotelor,

$$\varphi_{k}=\frac{ \pm 180^{\circ}(2 k+1)}{n-m},(k=0,1,2, \ldots) $$

- Abscisa punctului de intersecţie a aimptotelor,

$$\sigma_{a}=\frac{\sum p_{i}-\sum z_{j}}{n-m}$$

### Pasul 5: se găsesc punctele de ramificaţie (de sosire şi de plecare)

În acest scop scriem ecuaţia caracteristică conform expresiei

$$1+\frac{K B(z)}{A(z)}=0 \text{, sau }K=-\frac{A(z)}{B(z)}$$

Punctele de ramificaţie ale locului rădăcinilor se determină prin rezolvarea ecuaţiei

$$\frac{\mathrm{d} K}{\mathrm{~d} z}=\frac{B^{\prime}(z) A(z)-B(z) A^{\prime}(z)}{B^{2}(z)}=0$$

unde caracterul prim indică operaţia de derivare în raport cu variabila $z$. Este important să remarcăm însă că punctele de ramificaţie vor fi numai acele rădăcini reale ale ecuaţiei (7) care se află pe porţiunea considerată a locului rădăcinilor de pe axa reală.

### Pasul 6: se determină unghiul de plecare (unghiul de sosire) al locului rădăcinilor dintrun pol complex (într-un zero complex)

- Unghiul de plecare dintr-un pol complex $=\varphi_{p}=180^{\circ}-\sum \theta_{j}+\sum \Phi_{i}$;

- Unghiul de sosire într-un zero complex $=\varphi_{s}=180^{\circ}-\sum \Phi_{i}+\sum \theta_{j}$;

$\Phi$ sunt unghiurile vectorilor care încep în zerouri, iar $\theta$ sunt unghiurile vectorilor complexi care pleacă din poli.

### Pasul 7: se determină punctele în care locul rădăcinilor intersectează cercul de rază unitară

Aceste puncte se determină folosindu-se [[Criteriul de stabilitate Routh-Hurwitz|criteriul de stabilitate Routh-Hurwitz]] modificat, sau rezolvând pentru $\omega$ şi $K$ ecuaţia complexă,

$$1+\frac{K B\left(e^{j \omega T_{e}}\right)}{A\left(e^{j \omega T_{e}}\right)}=1+\frac{K\left(e^{j \omega T_{e}}-z_{1}\right)\left(e^{j \omega T_{e}}-z_{2}\right) \cdots\left(e^{j \omega T_{e}}-z_{m}\right)}{\left(e^{j \omega T_{e}}-p_{1}\right)\left(e^{j \omega T_{e}}-p_{2}\right) \cdots\left(e^{j \omega T_{e}}-p_{n}\right)}=0$$

### Pasul 8: se gradează, dacă este necesar, locul rădăcinilor

Valoarea lui $K$ corespunzătoare fiecărui punct de pe locul rădăcinilor din planul $z$ se determină cu relaţia:

$$
K=\frac{1}{\left|G H\left(z_{1}\right)\right|}=\left|\frac{A\left(z_{1}\right)}{B\left(z_{1}\right)}\right|
$$

## Exemplul 1

Să se schiţeze locul rădăcinilor pentru un sistem discret de reglare cu reacţie negativă unitara $H(z)=1$ 

Functia de transfer $z$ a sistemului in circuit deschis este:

$$
G(z)=\frac{K\left(1-e^{-T_{e}}\right) z}{(z-1)\left(z-e^{-T_{e}}\right)} .
$$

---

### Pasul 1

 Deoarece sistemul are reacţie negativă unitară, $H(s)=1$, ecuaţia caracteristică este:

$$
1+G H(z)=1+\frac{K z\left(1-e^{-T_{e}}\right)}{(z-1)\left(z-e^{-T_{e}}\right)} .
$$

Factorul de amplificare $K$ se presupune pozitiv şi variabil de la 0 la $\infty$.

### Pasul 2

Deoarece gradul polinomului sistemului deschis este $n=2$, rezultă că locul rădăcinilor are două ramuri. Funcţia de transfer a sistemului deschis are doi poli:

$$p_{1}=1, p_{2}=e^{-T_{e}}\text{, cu }0<p_{2}<1$$

şi un zero:

$$z_{1}=0$$

Repartiţia poli-zerouri pentru funcţia de transfer considerată în exemplu poate fi vizualizată în figura 4.57 care prezintă şi schiţa locului rădăcinilor.

### Pasul 3

Locul rădăcinilor pe axa reală are două porţiuni care respectă condiţia generală:

- între polii $p_{1}$ şi $p_{2}$;
- între zeroul $z_{1}=0$ şi $\infty$.

### Pasul 4

Numărul asimptotelor este:

$$n-m=2-1=1$$

Singura asimptotă este suprapusă axei reale (deoarece $\varphi_{1}=180^{\circ}(2 k+1)=180^{\circ}$ ) şi corespunde locului rădăcinilor cuprins între $z_{1}=0$ şi $\infty$.

### Pasul 5

Deoarece avem porţiuni ale locului pe axa reală între doi poli, respectiv zerouri (unul finit, celălalt la infinit), există 2 puncte de ramificaţie. Scriind ecuaţia caracteristică conform expresiei:

$$
K=\frac{(z-1)\left(z-e^{-T_{e}}\right)}{z\left(1-e^{-T_{e}}\right)}=\frac{z^{2}-\left(1+e^{-T_{e}}\right) z+e^{-T_{e}}}{z\left(1-e^{-T_{e}}\right)}=\frac{A(z)}{B(z)},
$$

punctele de ramificaţie sunt soluţile ecuaţiei

$$
\frac{d K}{d z}=\frac{z\left(1-e^{-T_{e}}\right)\left(2 z-1-e^{-T_{e}}\right)-\left(1-e^{-T_{e}}\right)\left[z^{2}-\left(1+e^{-T_{e}}\right) z+e^{-T_{e}}\right]}{z^{2}\left(1-e^{-T_{e}}\right)^{2}}=0,
$$

respectiv

$$
z^{2}\left(1-e^{-T_{e}}\right)-e^{-T_{e}}\left(1-e^{-T_{e}}\right)=0,
$$

$$z_{r 1,2}= \pm \sqrt{e^{-T_{e}}}$$

Se verifică uşor că, deoarece $e^{-T_{e}}<1, \sqrt{e^{-T_{e}}}>e^{-T_{e}}$, deci $z_{r 1} \in\left(p_{2}, p_{1}\right) \equiv\left(e^{-T_{e}}, 1\right)$.

### Pasul 6

Funcţia de transfer $z$ a sistemului deschis nu are poli complecşi sau zerouri complexe.

Pentru o schiţare mai exactă vom arăta că forma locului rădăcinilor pentru cazul rădăcinilor complexe ale sistemului închis este un cerc. În acest scop se înlocuieşte $z=x+j y$ în funcţia de transfer $z$ a sistemului deschis:

$$
G(x+j y)=\frac{\left(1-e^{-T_{e}}\right)(x+j y)}{[(x-1)+j y]\left[\left(x-e^{-T_{e}}\right)+j y\right]},
$$

şi se scrie condiţia argumentului, de unde rezultă:

$$
\angle G(z)=\operatorname{arctg} \frac{y}{x}-\operatorname{arctg} \frac{y\left(2 x-1-e^{-T_{e}}\right)}{(x-1)\left(x-e^{-T_{e}}\right)-y^{2}}=(2 k+1) 180^{\circ}
$$

![](https://cdn.mathpix.com/cropped/2023_08_08_b683b8c6715240203458g-5.jpg?height=871&width=1196&top_left_y=1124&top_left_x=424)

Se aplică apoi funtia tangentă relaţiei de mai sus în ambii membrii şi se obţine:

$$
\operatorname{tg} \angle G(z)=\frac{\frac{y}{x}-\frac{y\left(2 x-1-e^{-T_{e}}\right)}{(x-1)\left(x-e^{-T_{e}}\right)-y^{2}}}{1+\frac{y}{x} \frac{y\left(2 x-1-e^{-T_{e}}\right)}{(x-1)\left(x-e^{-T_{e}}\right)-y^{2}}}=\operatorname{tg}(2 k+1) 180^{\circ}=0 .
$$

De aici avem

$$
\frac{y}{x}-\frac{y\left(2 x-1-e^{-T_{e}}\right)}{(x-1)\left(x-e^{-T_{e}}\right)-y^{2}}=0,
$$

de unde, după simplificare, rezultă: 

$$
x^2+y^2=e^{-T_e}
$$

deci locul geometric al rădăcinilor este un cerc cu centrul în origine şi raza $R=\sqrt{e^{-T_e}}$.

### Pasul 7

Cercul de rază unitară este intersectat o singură dată de locul rădăcinilor. Acest punct se obţine pentru $z_i=-1$. Factorul de amplificare pentru care sistemul discret este la limita de stabilitate se determină cu relaţia:

$$
K_1=\frac{1}{\left|G H\left(z_i\right)\right|}=\left|\frac{A\left(z_i\right)}{B\left(z_i\right)}\right|=\left|\frac{-2\left(-1-e^{-T_e}\right)}{-1\left(1-e^{-T_e}\right)}\right|=2 \frac{1+e^{-T_e}}{1-e^{-T_e}} \text {. }
$$
### Pasul 8

Vom calcula factorul de amplificare pentru valorile variabilei z pentru care locul rădăcinilor intersectează axele reală şi imaginară:

$$
\begin{aligned}
& K_2=\frac{1}{\left|G\left(\sqrt{e^{-T_e}}\right)\right|}=\left|\frac{\left(\sqrt{e^{-T_e}}-1\right)\left(\sqrt{e^{-T_e}}-e^{-T_e}\right)}{\sqrt{e^{-T_e}}\left(1-e^{-T_e}\right)}\right|=\frac{\left(1-\sqrt{e^{-T_e}}\right)^2}{1-e^{-T_e}}, \\
& K_3=\frac{1}{\left|G\left(-\sqrt{e^{-T_e}}\right)\right|}=\left|\frac{\left(-\sqrt{e^{-T_e}}-1\right)\left(-\sqrt{e^{-T_e}}-e^{-T_e}\right)}{-\sqrt{e^{-T_e}}\left(1-e^{-T_e}\right)}\right|=\frac{\left(1+\sqrt{e^{-T_e}}\right)^2}{1-e^{-T_e}}, \\
& K_4=\frac{1}{\left|G\left(j \sqrt{e^{-T_e}}\right)\right|}=\left|\frac{\left(j \sqrt{e^{-T_e}}-1\right)\left(j \sqrt{e^{-T_e}}-e^{-T_e}\right)}{j \sqrt{e^{-T_e}}\left(1-e^{-T_e}\right)}\right|=\frac{1+e^{-T_e}}{1-e^{-T_e}}, \\
& K_5=\frac{1}{\left|G\left(-j \sqrt{e^{-T_e}}\right)\right|}=\left|\frac{\left(-j \sqrt{e^{-T_e}}-1\right)\left(-j \sqrt{e^{-T_e}}-e^{-T_e}\right)}{-j \sqrt{e^{-T_e}}\left(1-e^{-T_e}\right)}\right|=\frac{1+e^{-T_e}}{1-e^{-T_e}} .
\end{aligned}
$$

Particularizând pentru $T_e=0.3 \mathrm{~s}$, vom avea următoarele valori pentru parametrii locului rădăcinilor:

- raza $R=0,8607$
- factorul de amplificare la limita de stabilitate $K_1=13,4332$
- factorul de amplificare pentru $z=z_{1 r}, K_2=0,0749$
- factorul de amplificare pentru $z=-z_{1 r}, K_3=13,3583$
- factorul de amplificare pentru $z= \pm j z_{1 r}, K_{4,5}=6,7166$.

>[!note]
>Interesantă este analiză valorilor obţinute şi a locului rădăcinilor când se modifică perioada de eşantionare. Astfel dacă $T_e$ scade la valoarea $T_e=0.1$, se constată că raza corespunzătoare locului pentru rădăcini complexe creşte la valoarea $R=0,9512$, deci se apropie periculos de mult de limita de instabilitate, dar, aparent paradoxal, valoarea factorului de amplificare la limita de stabilitate creşte la $K_1=40,033$.
>
>O explicaţie pentru aceste valori contradictorii este în faptul că, deşi sistemul este stabil chiar la valori mari ale factorului de amplificare, în cazul rădăcinilor complexe, gradul de oscilaţie este extrem de pronunţat, deoarece sistemul discret este foarte aproape de limita de stabilitate.

---

[[SAE_curs13.pdf]]

[^1]: De regula $G(z)$ include si functia de transfer a elementului de retinere $GH(z)=Z\{G(s)H(s)\}$