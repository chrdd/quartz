---
tags:
  - PrelucrareaSemnalelor
  - SistemeAutomateCuEsantionare
pdf:
---
 
Din punct de vedere tehnic, semnalul reprezintă o mărime fizică care are proprietatea de a se propaga într-un anumit mediu.

Orice semnal are un continut informational (un mesaj destinat unui receptor). 
Pe lângă componenta utilă (informaţională) semnalele, din procesele fizice reale, conţin una sau mai multe componente perturbatoare, care apar în procesul de generare, transmitere şi recepţie a acestora.

Din punct de vedere matematic un semnal se descrie prin funcţii de timp de forma:
$$x:T \rightarrow M \space \text{cu} \space t \in T \space \text{si} \space x(t) \in M$$
sau prin functii de frecventa:
$$X : \Omega \rightarrow N \space \text{cu} \space \omega \in \Omega \space \text{si} \space X(\Omega) \in N$$
## Clasificarea semnalelor
### Dupa domeniul de definitie
- Dupa domeniul de definite $T$ al functiilor de timp $x(t)$, semnalele se clasifica in:
	1. Semnale continue in timp (analogice) ($T=R \space \text{sau} \space T \subset Z, t \in Z$) 
	2. Semnale discrete (esantionate) ($T=Z \space \text{sau} \space T \subset Z, t \in Z$)
- Dupa numaril nivelelor pe care le poate lua semnalul in amplitudine:
	1. Semnale continue in amplitudine, caz in care $M \in R \space \text{si} \space x(t) \in R$, $M$ fiind o multime infinita (ca numar de elemente)
	2. Semnale cuantificate (cuantizate), situaţie în care $M$ este o mulţime cu un număr finit de elemente.[^1]
- După modul în care se poate predetermina (prestabili sau previziona) evoluţia ulterioară a semnalelor
	1. Semnale deterministe
		1. Semnale periodice : armonice (*SPA*) şi oarecare (*SPO*)
		2. Semnale neperiodice : quasi-periodice şi tranzitorii (*speciale*)
	2. Semnale aleatoare (nedeterministe) [^2]
## Semnale periodice
### Semnale periodice armonice
Un semnal periodic armonic este exprimat analitic prin relaţii de forma:
$$x(t)=A \sin(\frac{2 \pi t}{T})=A \sin (2 \pi f_1 t)=A \sin (\omega_1 T)$$
>[!info] 
>Valabile în cazul fazei iniţiale nule

Se poate utiliza în egală măsură şi funcţia trigonometrică $\cos$.

Un semnal armonic este complet caracterizat dacă se cunosc amplitudinea ($A$) şi pulsaţia ( $\omega_1$ ) sau frecvenţa ( $f_1$ ), respectiv perioada ( $T$ ).

### Semnale periodice oarecare

Semnalele periodice oarecare sunt descrise prin funcţii de timp care au proprietatea:
$$x(t)=x(t \pm nT), n \in N, T \in R$$
unde $T$ este perioada de repetitie a semnalului.

Semnalele periodice pot fi exprimate printr-o descompunere în serie Fourier conform relaţiei:
$$
x(t)=A_{0} / 2+\sum_{n=1}^{\infty}\left[A_{n} \cos \left(n \omega_{1} t\right)+B_{n} \sin \left(n \omega_{1} t\right)\right]
$$
sau în mod echivalent:
$$
x(t)=A_{0} / 2+\sum_{n=1}^{\infty} M_{n} \cos \left(n \omega_{1} t+\varphi_{n}\right), \text { cu } n \in \boldsymbol{N}, t \in \boldsymbol{R}
$$
unde:
$$
\omega_{1}=2 \pi / T, M_{n}=\sqrt{A_{n}^{2}+B_{n}^{2}}, \varphi_{n}=\operatorname{arctg}\left(-B_{n} / A_{n}\right)
$$

Din relaţiile anterioare se observă că semnalele periodice oarecare au un spectru discret, care conţine numai armonici multiplu întreg al armonicii fundamentale.

Armonicile conţinute în spectrul unui semnal periodic oarecare prezintă proprietatea:
$$
\frac{\omega_{i}}{\omega_{j}}=\frac{i \omega_{1}}{j \omega_{1}}=\frac{i}{j} \in \boldsymbol{Q}
$$
deoarece $i, j \in N$.

## Semnale neperiodice
### Semnalele neperiodice quasi-periodice
Semnalele neperiodice quasi-periodice sunt descrise analitic prin relaţii de forma:
$$
x(t)=A_{0} / 2+\sum_{n=1}^{\infty} M_{n} \cos \left(\omega_{n} t+\varphi_{n}\right)
$$
dar în acest caz 
$$
\frac{\omega_{i}}{\omega_{j}}=\in \boldsymbol{R} \backslash \boldsymbol{Q} \text { (numere iraţionale). }
$$
### Semnalele neperiodice tranzitorii (speciale)
Semnalele neperiodice tranzitorii (speciale) sunt semnale care nu îndeplinesc nici una dintre proprietăţile menţionate. În această subclasă sunt cuprinse şi semnale tipice utilizate în automatică:
#### Impulsul Dirac

^e2a860

Definit cu relaţiile:
$$
\delta(t)=\left\{\begin{array}{l}
\infty \text { pentru } t=0 \\
0 \text { altfel }
\end{array} \text { şi } \int_{-\infty}^{\infty} \delta(t) \mathrm{d} t=1\right.
$$
cu proprietatea numită de filtrare exprimată prin:
$$
\int_{-\infty}^{\infty} \mathrm{f}(t) \delta\left(t-t_{0}\right) \mathrm{d} t=\mathrm{f}\left(t_{0}\right)
$$

![[Pasted image 20231005162710.png]]
#### Treapta unitară
Descrisă de:
$$
x_{1}(t)=1_{+}(t)=\left\{\begin{array}{l}
1 \text { pentru } t \geq 0 \\
0 \text { altfel }
\end{array} .\right.
$$
Treapta unitară se corelează cu impulsul Dirac cu relaţia:
$$
\frac{\mathrm{d} 1_{+}(t)}{\mathrm{d} t}=\delta(t)
$$


![[Pasted image 20231005162638.png]]
#### Rampa unitara
Definita prin:
$$
x_{2}(t)=\left\{\begin{array}{l}
t \text { pentru } t \geq 0 \\
0 \text { altfel }
\end{array},\right.
$$
corelată cu treapta unitară conform expresiei:
$$
\frac{\mathrm{d} x_{2}(t)}{\mathrm{d} t}=1_{+}(t)
$$

![[Attachments/image-removebg-preview.png]]
#### Semnalul armonic unitar
descris prin funcţia definită pe porţiuni:
$$
x_{3}(t)=\left\{\begin{array}{cc}
\sin \omega t & \text { pentru } t \geq 0 \\
0 & \text { altfel }
\end{array}\right.
$$
![[Pasted image 20231005162832.png]]

[[Metode de analiza a semnalelor deterministe]]

[^1]:  Aceste semnale sunt specifice echipamentelor de prelucrare numerică, fiind obţinute la ieşirea convertoarelor numeric-analogice. Un caz particular de semnal cuantizat, este semnalul logic sau binar, care poate avea numai două nivele, $0$ şi $U$ (informaţional $0$ sau $1$).

[^2]: Semnalele aleatoare au un caracter general, deoarece toate procesele fizice reale prelucrează semnale de acest tip, semnalele deterministe fiind de fapt idealizări prin care se aproximează, în anumite condiţii, în scopul simplificării studiului, evoluţia mărimilor cu caracter aleator. Semnalele deterministe pot fi descrise prin relaţii analitice.