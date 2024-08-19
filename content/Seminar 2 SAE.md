---
tags:
  - SistemeAutomateCuEsantionare
---

Transformata Z a unor semnale simple poate fi calculata folosindu-se definitia. Se va prezenta, in continuare, modul de calcul pentru cateva din semnalele speciale din automatica.

## Exercitiul 1

Sa se determine [[Transformata Z|transformata Z]] pentru [[Semnale#Impulsul Dirac|impulsul Dirac]] definit cu relatia:

$$
\delta (t)=\begin{cases}
\infty , \quad \text{pentru } t=0 \\
0, \quad \text{altfel}
\end{cases}
$$
---
Se poate vedea usor ca versiunea esantionata si semnalul original sunt identice, deci:

$$
\delta^{*}(t)=\delta(t)
$$
prin urmare, transformata Laplace esantionata va fi:

$$
\Delta^{*}(s)= \mathcal{L}\{\delta^{*}(t)\}=1
$$

de unde rezulta:

$$
\mathbb{Z}\{\delta(t)\}=1
$$
---
Jeg de explicatie din seminar, indienii la ajutor!
### Explicatie decenta
>[!note]
>Transformata Z se poate aplica doar pe semnale discrete, asa ca va trebui sa discretizam impulsul Dirac


Stim ca impulsul Dirac este de forma:
$$
\delta (t)=\begin{cases}
\infty , \quad \text{pentru } t=0 \\
0, \quad \text{altfel}
\end{cases}
$$
Asta inseamna ca la timpul 0, semnalul are valoarea 1, la celelalte valori de timp este egal cu 0.

Stim ca formula [[Transformata Z|transformatei Z]] este urmatoarea:

$$
Z \cdot T[x(n)]\sum_{n=-\infty}^{\infty}x(n)z^{-n}
$$
Inlocuind cu impulsul Dirac in formula generala, vom avea:

$$
\begin{align}
&Z \cdot T[\delta(n)]=\sum^{\infty}_{n=-\infty}\delta(n)z^{-n}= \\
&=\dots\delta(-2)z^{-2}+\delta(-1)z^{-1}+\delta(0)z^{-0}+\delta(1)z^{1}+\dots
\end{align}
$$

Insa stim ca impulsul Dirac are valoarea 1 doar in timpul 0, iar in rest 0, astfel vom avea:

$$
\dots 0 \cdot z^{-2}+0 \cdot z^{-1}+ 1 \cdot z^{0} + 0 \cdot z^{1}+\dots
$$

De unde rezulta ca transformata Z a impulsului Dirac are valoarea:

$$
Z(\delta(t))=1
$$


![](https://youtu.be/r48Poz_Lsvw?si=mwUMSCmmT2XtxQUj)
### Exercitiul 2
Un semnal specific sistemelor discrete, care poate fi realizat practic relativ uşor, într-o formă aproximativă, este impulsul unitar notat şi definit ca în relaţiile:

$$
\delta_{1}(t)=\begin{cases}
1, \quad \text{pentru } t=0 \\
0, \quad \text{altfel}
\end{cases}
$$
respectiv

$$
\delta_{1}[k]=\begin{cases}
1, \quad \text{pentru }k=0 \\
0, \quad \text{altfel}
\end{cases}
$$
---
Versiunea intarziata a acestui semnal este:

$$
\delta_{1}(t-\tau)=\begin{cases}
1, \quad \text{pentru }t=\tau \\
0, \quad \text{altfel}
\end{cases}
$$
respectiv

$$
\delta_{1}[k-l]=\begin{cases}
1, \quad \text{pentru }k=l \\
0, \quad \text{altfel}
\end{cases}
$$

unde $k,l \in \mathbb{Z}$ sau $\mathbb{N}$.

[[Transformata Z]] a impulsului unitar se poate calcula direct prin aplicarea relatiei de definitie:

$$
\mathbb{Z}\{\delta_{1}[k]\}=\sum_{k=-\infty}^{+\infty} \delta_{1}[k]z^{-k}=z^{0}=1
$$
### Exercitiul 3
Se  calculeaza [[Transformata Z|transformata Z]] pentru secventa [[Semnale#Treapta unitară|treapta unitara]] definita conform relatiei:

$$
1_{+}^{*}(t)=1_{+}(kT_{e})=\begin{cases}
1, \quad \text{pentru }k\geq 0 \\
0, \quad \text{pentru } k<0
\end{cases}
$$
---
Cand functia treapta unitara este esantionata ideal se obtine un tren de impulsuri unitare. Aplicandu-se relatia de definitie a [[Transformata Z|transformatei Z]] in acest caz se obtine:
$$
F(z)=Z\{1_{+}^{*}(t)\}=\sum^{+\infty}_{k=0}z^{-k}=1+z^{-1}+z^{-2}+z^{-3}+\dots
$$
Expresie care poate fi scris a in forma restransa:

$$
F(z)=\frac{1}{1-z^{-1}}=\frac{z}{z-1}. \quad \mid z\mid<1
$$
>[!note]
>Forma restransa se obtine considerandu-se suma o [[Serii de puteri|serie de puteri]] ale lui $z^{-1}$ si aplicandu-se apoi relatia: $$F(z)=\lim_{ k \to \infty } \frac{1-(z^{-1})^{k}}{1-z^{-1}}=\frac{1}{1-z^{-1}} $$ Rezultatul este valabil daca $\mid z\mid<-1$
>

^11a1b7

### Exercitiul 4
Sa se calculeze [[Transformata Z|transformata Z]] pentru functia exponentiala: 

$$
f(t)=e^{-at}, \quad t\geq 0
$$
Se considera ca pentru $t<0,f(t)=0$.

---
Aplicandu-se [[Transformata Z#Definitie|relatia de definitie]] se obtine:

$$
F(z)=\mathbb{Z} \{ e^{-at}\}=\sum_{k=0}^{+\infty}e^{-akT_{e}}z^{-k}=1+(ze^{aT_{e}})^{-1}+(ze^{aT_{e}})^{-2}+\dots
$$
Notand cu $x=(ze^{aT_{e}})^{-1}$, daca $\mid x\mid<1$, adica daca $\mid ze^{aT_{e}}\mid<1$, respectiv $\mid z\mid< e^{-aT_{e}}$ si folosind rationamentul de la [[Seminar 2 SAE#^11a1b7|treapta unitara]], rezulta:

$$
F(z)=\mathbb{Z}\{e^{-aT_{e}}\}=\frac{1}{1-(ze^{aT_{e}})^{-1}}=\frac{z}{z-e^{-aT_{e}}}
$$
### Exercitiul 5
Sa se calculeze [[Transformata Z|transformata Z]] pentru semnalul 

$$
f(t)=r^{t}
$$ unde $r>0$ si $\mid r\mid<1$.

---
O soluţie rapidă se poate obţine dacă se observă că funcţia putere $f(t)=r^{t}$ constituie de fapt un caz particular al functiei exponentiale, deoarece se poate scrie succesiv:

$$
f(t) = e^{-at}=(e^{-a})^{t}=r^{t}
$$
Asadar solutia problemei este:

$$
\mathbb{Z}\{r^{t}\}=\frac{z}{z-r^{T_{e}}}=\frac{z}{z-p}
$$ unde $p=r^{T_{e}}$.

>[!summary]
>Rezumand rezultatele obtinute in exemplele anterioare vom avea urmatoarele perechi de [[Transformata Laplace|transformate Laplace]] (*TL*) si [[Transformata Z|Z]] (*TZ*):
>
>|     |                                 | TL              | TZ                        |
| --- | ------------------------------- | --------------- | ------------------------- |
| 1   | Impuls Dirac, $\delta(t)$       | 1               | 1                         |
| 2   | Impuls unitar, $\delta_{1}(t)$  | 1               | 1                         |
| 3   | Trepta unitara, $1_{+}(t)$      | $\frac{1}{s}$   | $\frac{z}{z-1}$           |
| 4   | Functie exponentiala, $e^{-at}$ | $\frac{1}{s+a}$ | $\frac{z}{z-e^{-aT_{e}}}$ |
>
>Aceste rezultate sunt utile pentru introducerea unei metode simple, cu caracter general, pentru calculul [[Transformata Z|transformatelor Z]].

### Exercitiul 6
Sa se calculeze [[Transformata Z|transformata Z]] a functiei [[Semnale#Rampa unitara|rampa unitara]] 

$$
f(t)=t,\quad t\geq 0
$$

---

Se utilizeaza teorema derivarii partiale aplicata functiei exponentiale. Se observa ca: 

$$
t=\lim_{ a \to 0 } \left\{ - \frac{\varphi}{\varphi a}[e^{-at}] \right\}=\lim_{ a \to 0 }[t e^{-at}]  
$$
Solutia problemei va fi:

$$
\mathbb{Z}\{t\}_{t\geq 0}=-\lim_{ a \to 0 } \frac{\varphi}{\varphi -a}\left( \frac{z}{z-e^{-aT_{e}}} \right)=-\lim_{ a \to 0 } \frac{-zT_{e}e^{-aT_{e}}}{(z-e^{-aT_{e}})^{2}}=\frac{zT_{e}}{(z-1)^{2}}  
$$

### Exercitiul 7
Sa se determine [[Transformata Z|transformatele Z]] pentru semnalele:

$$
\begin{cases}
f_{1}(t)=\sin \omega t \\
f_{2}(t)=\cos \omega t 
\end{cases} \quad ,t \geq 0
$$

---
Se va calcula mai intai [[Transformata Z|transformata Z]] pentru $f_{1}(t)=\sin \omega t$, care are [[Transformata Laplace|transformata Laplace]]:

$$
F_{1}(s)=\frac{\omega}{s^{2}+\omega^{2}}
$$
cu radacinile simple $p_{1,2}=\pm j \omega$. 

Descompunerea in fractii simple este:

$$
F_{1}(s)=\frac{c_{1}}{s+j \omega}+\frac{c_{2}}{s-j \omega}
$$
unde:

$$
\begin{align}
& c_{1}=(s+j \omega) \frac{\omega}{(s+j \omega)(s- j \omega)}\Bigg{|}_{s=-j \omega}=\frac{\omega}{-2j \omega}=-\frac{1}{2j}, \\
& c_{2}=(s-j \omega) \frac{\omega}{(s+j \omega)(s- j \omega)}\Bigg{|}_{s=+j \omega}=\frac{\omega}{2j \omega}=\frac{1}{2j}
\end{align}
$$
Se obtine astfel:

$$
F_{1}(s)=\frac{1}{2j}\left[ \frac{1}{s-j\omega}-\frac{1}{s+j \omega } \right]
$$
In final rezulta:

$$
\begin{align}
& \mathbb{Z}\{\sin \omega t\}=F_{1}(z)=\frac{1}{2j}\left[ \frac{z}{z-e^{j \omega T_{e}}}-\frac{z}{z-e^{-j \omega T_{e}}} \right] \\
& =\frac{z}{2j} \frac{z-e^{-j \omega T_{e}}-z + e^{j \omega T_{e}}}{(z-e^{j \omega T_{e}})(z-e^{-j \omega T_{e}})} \\
& =\frac{e^{j \omega T_{e}}-e^{-j \omega T_{e}}}{2j} \frac{z}{z^{2}-z(e^{j \omega T_{e}}+e^{-j \omega T_{e}})+1} \\
&=\frac{z \sin \omega T_{e}}{z^{2}-2z \cos \omega T_{e}+1}
\end{align}
$$
[[Transformata Laplace]] a functiei $f_{2}(t)=\cos \omega t$ este:

$$
F_{2}(s)=\frac{s}{s^{2}+\omega^{2}}
$$
cu descompunerea in fractii simple se obtine:

$$
F_{2}(s)=\frac{c_{1}}{s+j \omega}+\frac{c_{2}}{s-j \omega}
$$
unde

$$
\begin{align}
&c_{1}=\frac{s}{s-j \omega} \Bigg{|}_{s=-j \omega}=\frac{-j \omega}{-2j \omega}=\frac{1}{2} \\
&c_{2}=\frac{s}{s+j \omega}\Bigg{|}_{s=j \omega}=\frac{j \omega}{2j \omega}=\frac{1}{2}
\end{align}
$$
Inlocuind $c_{1}$ si $c_{2}$ in descompunere se obtine in continuare:

$$
F_{2}(s)=\frac{1}{2} \left[ \frac{1}{s+j \omega}+\frac{1}{s-j \omega} \right]
$$
de unde rezulta:

$$
\begin{align}
&\mathbb{Z}\{\cos\omega t\}=F_{2}(z)=\frac{1}{2} \left[ \frac{z}{z-e^{j \omega T_{e}}}+\frac{z}{z-e^{-j \omega T_{e}}} \right] \\
&=\frac{z}{2} \frac{z-e^{-j \omega T_{e}}+z-e^{j \omega T_{e}}}{z^{2}-2z \cos \omega T_{e}+1} \\
& =\frac{z\left[ z-\frac{e^{j \omega T_{e}}+e^{-j \omega T_{e}}}{2} \right]}{z^{2}-2z \cos \omega T_{e} + 1} \\
&= \frac{z(z-\cos \omega T_{e})}{z^{2}- 2 z \cos \omega T_{e}+1}
\end{align}
$$

### Exercitiul 8
Sa se calculeze [[Transformata Z|transformata Z]] pentru semnalul 

$$
f(t)=te^{-at}
$$

---
Se cunoaste ca 

$$
\mathbb{Z}\{t\}_{t\geq 0}=\frac{zT_{e}}{(z-1)^{2}}=F_{1}(z)
$$
Se aplica in continuare teorema deplasarii in complex, de unde rezulta:

$$
\begin{align}
&F(z) = \mathbb{Z} \{te^{-at}\}=F_{1}(ze^{aT_{e}}), \\
& F(z)=\frac{zT_{e} e^{aT_{e}}}{(ze^{aT_{e}}-1)^{2}}=\frac{zT_{e}e^{-aT_{e}}}{(z-e^{-aT_{e}})^{2}}
\end{align}
$$

### Exercitiul 9
Sa se deermine [[Transformata Z|transformatele Z]] pentru functiile: 

$$
\begin{align}
&f_{1}(t)=e^{-at}\sin \omega t \\
& f_{2}(t)=e^{-at} \cos \omega t
\end{align}
$$

---
Se aplica teorema deplasarii in complex. In aceste conditii se obtine:

$$
\begin{align}
&F_{1}(z)=\frac{z \sin \omega T_{e}}{z^{2}-2z \cos \omega T_{e}+1}\Bigg{|}_{z=z e^{a T_{e}}}= \frac{z e^{a T_{e}} \sin \omega T_{e}}{z^{2} e ^{2 a T_{e}}-2 z e ^{a T_{e} } \cos \omega T_{e} +1} \\
&= \frac{z e ^{-a T_{e}} \sin \omega T_{e}}{z^{2} - 2 z e^{-a T_{e}}\cos \omega T_{e}+e^{-2aT_{e}}}, \\
& F_{2}(z)=\frac{z(z-\cos \omega T_{e})}{z^{2}-2z \cos \omega T_{e} +1}\Bigg{|} _{ z=z e ^{a T_{e}}} = \frac{z e ^{a T_{e}}(ze^{a T_{e}}-\cos \omega T_{e})}{z^{2} e^{2 a T_{e}}-2ze^{aT_{e}}\cos \omega T_{e}+1} \\
&= \frac{z^{2}-ze^{-aT_{e}}\cos \omega T_{e}}{z^{2} -2 ze^{-aT_{e}}\cos \omega T_{e}+e^{-2aT_{e}}}
\end{align}
$$

### Exercitiul 10
Fiind data functia complexa ([[Transformata Z|transformata Z]]):

$$
F(z)=\frac{0,792z^{2}}{(z-1)(z^{2}-0.416z+0.208)}
$$
Sa se determine valoarea finala $f(kT_{e}), \space k \to \infty$.

---
Deoarece functia complexa are polii in planul z in interiorul cercului de raza unitara, se poate aplica teorema valorii finale. Astfel, se obtine:

$$
\lim_{ k \to \infty } f(kT_{e})=\lim_{ z \to 1 }[(1-z^{-1})F(z)]=\lim_{ z \to 1 } \frac{0.792z^{2}}{z^{2}-0.416z+0.208}=1   
$$

