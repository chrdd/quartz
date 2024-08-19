---
tags:
  - SistemeAutomateCuEsantionare
aliases:
  - Curs 3 SAE
  - Curs 7 SAE
---



## Definitie
**Tranzformata Z** reprezinta o metoda analitica care transforma semnale (sau sisteme) discrete (esantionate) in reprezentarile lor in **[[Planul Z|domeniul Z]]**.

![[Pasted image 20240731104603.png]]

Ecuatia transformatei Z are urmatoarea forma:

$$X(z)=\sum^{\infty}_{n=-\infty}\mathrm{x}[n]z^{-n}$$

Iar aceasta se poate interpreta astfel:

> Pornim de la un semnal in domeniul timpului care este esantionat periodic, unde $n$ este numarul de esantionare. Dupa aceea, inmultim fiecare variabila cu o valoare $z$, la puterea numarului de esantionare negativ, iar dupa insumam rezultatul pe toata durata semnalului. Iesirea $X$ este o functie a noii variabile $z$.

## Calculul transformatei z

Sa incepem cu un sistem oarecare. La intrarea acestuia vom aplica un impuls discretizat in timp (prima valoare este egala cu 1, iar restul sunt 0). Sistemul va fi afectat de acel impuls intr-un anumit mod, masurand iesirea sistemului cu un senzor digital, astfel iesirea va fi discretizata in timp.

Vom alege mai multe sisteme ca si exemplu:

1. O sa alegem un sistem "pass-through" (intrarea si iesirea sunt identice):![[Pasted image 20240731105728.png]]Pentru a afla reprezentarea Z a acestui sistem, vom aplica transformata Z pentru semnalul de iesire.$$Y(z)=\sum^{\infty}_{n=0} y[n]z^{-n}$$Nu exista date pentru valori negative ale lui $n$, asa ca vom suma incepand de la 0.
	- Pentru $n=0$, semnalul are valoarea $1$
	- Pentru $n=1,2,\dots$, semnalul are valoarea $0$
	Aplicand formula generala, vom avea:$$Y(z)=\sum^{\infty}_{n=0} y[n]z^{-n}=1 \cdot z^{-0}+0 \cdot z^{-1}+ 0 \cdot z^{-2} + \dots=1$$

2. O sa alegem acum un alt sistem care intarzie semnalul cu un esantion:![[Pasted image 20240731110519.png]]
	- Pentru $n=0$, semnalul are valoarea $0$
	- Pentru $n=1$, semnalul are valoarea $1$
	- Pentru $n=2,3,\dots$, semnalul are valoarea $0$
	Aplicand formula generala, vom avea:$$Y(z)=\sum^{\infty}_{n=0} y[n]z^{-n}=0 \cdot z^{-0}+1 \cdot z^{-1}+ 0 \cdot z^{-2} + \dots=1 \cdot z^{-1} =\frac{1}{z}$$
3. O sa alegem acum un alt sistem, acesta fiind un integrator (semnalul de iesire este semnalul de intrare integrat, in cazul acesta produce 1 pe tot domeniul):![[Pasted image 20240731111231.png]]
	- Pentru $n=0,1,2,\dots$, semnalul are valoarea $1$
	Aplicand formula generala, vom avea:$$Y(z)=\sum^{\infty}_{n=0} y[n]z^{-n}=1 \cdot z^{-0}+1 \cdot z^{-1}+ 1 \cdot z^{-2} + \dots$$
	Rezultatul este o [[Serie geometrica|serie geometrica]]. Putem simplifica algebric seria:
	$$\begin{align}&\frac{z-1}{z-1}(z^{-0}+z^{-1}+z^{-2}+\dots) \\&=\frac{(z+\cancel{1}+\cancel{z^{-1}}+\cancel{z^{-2}}+\dots)-(\cancel{1}+\cancel{z^{-1}}+\cancel{z^{-2}}+\dots)}{z-1}  \\&=\frac{z}{z-1}\end{align}$$Astfel, $\frac{z}{z-1}$ este reprezentarea in planul z a unui integrator.

4. Se poate calcula transformata z direct din ecuatia diferentiala. Vom alege un sistem care poate fi descris de ecuatia $$y[n]+0.5 \cdot y[n-1]=u[n]$$![[Pasted image 20240731112607.png]] Aplicam transformata z pentru ambele parti ale ecuatiei:
	1. Pentru a afla transformata z a valorii $y[n]$, o vom inlocui in ecuatia generala, insa deoarece ecuatia generala a transformatei z are forma $Y(z)=\sum^{\infty}_{n=0} y[n]z^{-n}$ (adica este definitia) , rezulta ca iesirea va fi: $$Y(z)=\sum^{\infty}_{n=0} y[n]z^{-n}=Y(z)$$
	2. Se aplica aceeasi logica pentru $U(z)$, avand ecuatia:$$U(z)=\sum^{\infty}_{n=0} u[n]z^{-n}=U(z)$$
	3. Pentru termenul din mijloc, adaugam $0.5 \cdot y[n]$, insa iesirea $y[n]$ este intarziata cu un esantion. Din exemplul anterior (2), cunoastem ca o intarziere este echivalenta cu inversul lui z, astfel vom avea: $$\sum^{\infty}_{n=0}0.5 y[n-1]z^{-n}=0.5 \cdot z^{-1} \cdot Y(z)$$
	Inlocuind rezultatele si calculand, vom obtine: $$\begin{align}
&Y(z)+0.5 \cdot z^{-1} \cdot Y(z) = U(z) \\
&\frac{Y(z)}{U(z)} = \frac{1}{1+0.5 \cdot z^{-1}}= \frac{z}{z + 0.5}
\end{align}$$

## Ce reprezinta transformata z

Transformata Z este similara cu [[Transformata Fourier#Transformata fourier discreta|transformata Fourier discreta]] prin modul in care aceasta ne ofera informatii despre sistem. 

In timp ce tranformata Fourier discreta ne ofera o analiza a semnalului de iesire a unui sistem, transformata z ne ofera informatii despre sistem in sine.

Daca cunoastem sistemul, atunci putem afla si forma semnalului de iesire la un semnal de intrare dat si putem afla cum putem schimba marimea de intrare pentru a ajunge la un anumit semnal de iesire.

Matematic, transformata z are aceeasi forma ca si [[Transformata Fourier#Transformata fourier discreta|transformata Fourier discreta]], cu exceptia adaugarii termenului $r^{-n}$:

$$\sum_{n=-\infty}^{\infty}\underbrace{x[n]e^{-i \omega n}}_{\text{Fourier}}\cdot \underbrace{r^{-n}}_{\text{Z}}$$

Termenul $r$ este un numar real pozitiv, iar cand amplifici un numar real cu un exponent negativ $n$, rezulta o [[Functia exponentiala#^23c5e1|curba exponentiala]]. Daca $r<1$, curba creste exponential, iar daca $r>1$, curba scade exponential.

Astfel, ne putem gandi la transformata z ca fiind o functie care cauta corelatia dintre semnalul discretizat, sinusoide (din termenul $e$) si exponentiale (din termenul $r$).

Daca simplificam ecuatiile celor 2 semnale de cautare, vom avea:

$$e^{-i\omega n}\cdot r^{-n} = (r \cdot e^{i\omega})^{-n}=z^{-n}$$ unde $z=r e^{i\omega}$.

### De ce este importanta originea transformatei z

Daca un sistem liniar poate fi modelat sub forma unei ecuatii diferentiale, atunci putem garanta ca raspunsul va contine:

- Oscilatii (frecvente)
- Exponentiale
deoarece solutia pentru un sistem liniar contine aceste 2 componente.

Daca putem determina continutul exponential si frecvential al iesirii la o anumita intrare, atunci putem cunoaste sistemul care a generat acea iesire.

Practic, atunci cand utilizam transformata z, pentru fiecare esantion "probam" (testam) in acelasi timp 2 frecvente sinusoidale (date de [[Transformata Fourier#Transformata fourier discreta|transformata Fourier discreta]]) si semale exponentiale (convergenta lor).

Prin inmultirea cu $r^{-n}$, putem testa convergenta sau divergenta semnalului de iesire in functie de un semnal ales de noi, si prin extensie, unde se afla polii si zerourile.


![Understanding the Z-Transform](https://www.youtube.com/watch?v=XJRW6jamUHk)
![Applied DSP No. 9: The z-Domain and Parametric Filter Design](https://youtu.be/xIN5Mnj_MAk?si=AFQt6yo1Wi3UHKgD)
![](https://youtu.be/hewTwm5P0Gg?si=n-SDbPbrCmKKStsR)

---

Transformata $z$ reprezintă o metodă de analiză a semnalelor eşantionate şi a sistemelor liniare discrete. Metoda transformatei $Z$ oferă un mecanism simplu, bazat pe funcţii raţionale de variabilă complexă, pentru descrierea semnalelor eşantionate.

## Definitie

Se consideră un semnal eşantionat descris în domeniul timpului cu relaţia:

$$
\begin{align}
& f^{*}(t)=\left.f(t)\right|_{t=0} \delta(t)+\ldots+\left.f(t)\right|_{t=k T_{e}} \delta\left(t-k T_{e}\right)+\ldots \\
&=\sum_{k=0}^{+\infty} f\left(k T_{e}\right) \delta\left(t-k T_{e}\right)
\end{align}
$$

care are [[Transformata Laplace|transformata Laplace]]:

$$
F^{*}(s)=\sum_{k=0}^{+\infty} f\left(k T_{e}\right) e^{-s k T_{e}},
$$

unde $f\left(k T_{e}\right)$ reprezintă valorile semnalului continuu în momentele de eşantionare. Prin definiţie, transformata Z a semnalului eşantionat $f^{*}(t)$ este:

$$
\begin{align}
&F(z)=\left.F^{*}(s)\right|_{S=\left(1 / T_{e}\right) \ln z} \\
&=f(0)+f\left(T_{e}\right) z^{-1}+\cdots+f\left(k T_{e}\right) z^{-k}+\cdots \\
&=\sum_{k=0}^{+\infty} f\left(k T_{e}\right) z^{-k}
\end{align}
$$

Se remarcă faptul că la definirea transformatei Z se poate scrie suma de la $k=-\infty$ la $k=+\infty$, adică: $F(z)=\sum_{k=-\infty}^{+\infty} f\left(k T_{e}\right) z^{-k}$

fapt posibil, având în vedere că semnalele cauzale folosite în automatică sunt nule pentru $k<0$.

Transformata Z a unui semnal continuu $f(t)$ care este eşantionat se notează prin:

$$F(z)=Z\{f(t)\}$$

unde $Z$ este simbolul pentru transformata Z.

O altă variantă de definire a transformatei $Z$ are la bază descrierea specifică unui semnal discret . În acest caz transformata Z se defineşte cu relaţia:[^1]

$$F(z)=\sum_{k=-\infty}^{+\infty} f[k] z^{-k}$$

O proprietate calitativă a transformatei Z este faptul că aceasta nu este univoc definită. Proprietatea constituie un dezavantaj important al transformatei Z. De aici se vede că versiunile eşantionate ale semnalelor din figurile a şi b sunt similare cu toate că semnalele continue sunt diferite.

Matematic avem:

$$f_{1}(t) \neq f_{2}(t)$$

dar:

$$f_{1}^{*}(t)=f_{2}^{*}(t)$$

deci:

$$F_{1}(z)=F_{2}(z)$$

![](https://cdn.mathpix.com/cropped/2023_08_10_dbb5fbaf8687f27a4deag-6.jpg?height=408&width=711&top_left_y=1889&top_left_x=318)

![](https://cdn.mathpix.com/cropped/2023_08_10_dbb5fbaf8687f27a4deag-6.jpg?height=423&width=691&top_left_y=1876&top_left_x=1048)

## Calculul transformatei z pe baza [[Transformata Laplace|transformatei Laplace]]

Se consideră semnalul descris de [[Transformata Laplace|transformata Laplace]]:

$$
F(s)=\frac{B(s)}{A(s)}=\frac{B(s)}{\prod_{i=1}^{n}\left(s+p_{i}\right)},
$$

care are rădăcini simple, reale sau complexe, pentru polinomul de la numitor. Având în vedere descompunerea în fracţii simple:

$$F(s)=\sum_{i=1}^{n} \frac{c_{i}}{s+p_{i}}$$

unde:

$$c_{i}=\left.\left(s+p_{i}\right) \frac{B(s)}{A(s)}\right|_{s=-p_{i}}$$

şi perechile de transformate Laplace şi $Z$ prezentate mai înainte, rezultă transformata $Z$:

$$F(z)=\sum_{i=1}^{n} c_{i} \frac{z}{z-e^{-p_{i} T_{e}}}$$

## Proprietăţile şi teoremele transformatei $Z$

Calculul transformatelor Z se poate simplifica în mod considerabil prin utilizarea unor proprietăţi cu caracter general şi al unor teoreme. Lista proprietăţilor şi teoremelor transformatei $Z$ este prezentată sintetic în tabelul urmator:

![](https://cdn.mathpix.com/cropped/2023_08_10_dbb5fbaf8687f27a4deag-7.jpg?height=834&width=1627&top_left_y=1733&top_left_x=220)

![[Pasted image 20230810194533.png]]

## Exemplul 1

Să se determine transformatele $Z$ pentru semnalele $f_{1}(t)=\sin \omega t$ şi $f_{2}(t)=\cos \omega t, t \geq 0$ Se va calcula mai întâi transformata $Z$ pentru $f_{1}(t)=\sin \omega t$ care are transformata Laplace:

$$F_{1}(s)=\frac{\omega}{s^{2}+\omega^{2}}$$

cu rădăcinile simple $p_{12}= \pm j \omega$. Descompunerea în fracţii simple este:

$$F_{1}(s)=\frac{c_{1}}{s+j \omega}+\frac{c_{2}}{s-j \omega}$$

unde:

$$c_{1}=\left.(s+j \omega) \frac{\omega}{(s+j \omega)(s-j \omega)}\right|_{s=-j \omega}=\frac{\omega}{-2 j \omega}=-\frac{1}{2 \mathrm{j}}$$

$$c_{2}=\left.(s-j \omega) \frac{\omega}{(s+j \omega)(s-j \omega)}\right|_{s=+j \omega}=\frac{\omega}{2 j \omega}=\frac{1}{2 j}$$

Se obţine astfel: 

$$
F_{1}(s)=\frac{1}{2 \mathrm{j}}\left[\frac{1}{s-\mathrm{j} \omega}-\frac{1}{s+\mathrm{j} \omega}\right]
$$

În final rezultă:

$$
\begin{aligned}
& Z\{\sin \omega t\}=F_{1}(z)=\frac{1}{2 \mathrm{j}}\left[\frac{z}{z-\mathrm{e}^{\mathrm{j} \omega T_{e}}}-\frac{z}{z-\mathrm{e}^{-\mathrm{j} \omega T_{e}}}\right]\\
&=\frac{z}{2 \mathrm{j}} \frac{z-\mathrm{e}^{-\mathrm{j} \omega T_{e}}-z+\mathrm{e}^{\mathrm{j} \omega T_{e}}}{\left(z-\mathrm{e}^{\mathrm{j} \omega T_{e}}\right)\left(z-\mathrm{e}^{-\mathrm{j} \omega T_{e}}\right)}= \\
& =\frac{\mathrm{e}^{\mathrm{j} \omega T_{e}}-\mathrm{e}^{-\mathrm{j} \omega T_{e}}}{2 \mathrm{j}} \frac{z}{z^{2}-z\left(\mathrm{e}^{\mathrm{j} \omega T_{e}}+\mathrm{e}^{-\mathrm{j} \omega T_{e}}\right)+1}\\
&=\frac{z \sin \omega T_{e}}{z^{2}-2 z \cos \omega T_{e}+1} 
\end{aligned}
$$

[[Transformata Laplace|Transformata Laplace]] a funcţiei $f_{2}(t)=\cos \omega t$ este:

$$F_{2}(s)=\frac{s}{s^{2}+\omega^{2}}$$

cu descompunerea în fracţii simple se obţine:

$$F_{2}(s)=\frac{c_{1}}{s+j \omega}+\frac{c_{2}}{s-j \omega}$$

unde:

$$
\begin{align}
&c_{1}=\left.\frac{s}{s-j \omega}\right|_{s=-j \omega}=\frac{-j \omega}{-2 j \omega} \\
&=\frac{1}{2}, \quad c_{2}=\left.\frac{s}{s+j \omega}\right|_{s=+j \omega}=\frac{j \omega}{2 j \omega}=\frac{1}{2}
\end{align}
$$

Înlocuind $c_{1}$ şi $c_{2}$ în expresie se obţine în continuare:

$$
F_{2}(s)=\frac{1}{2}\left[\frac{1}{s+j \omega}+\frac{1}{s-j \omega}\right]
$$

de unde, rezultă:

$$
\begin{aligned}
& Z\{\cos \omega t\}=F_{2}(z)=\frac{1}{2}\left[\frac{z}{z-\mathrm{e}^{j \omega T_{e}}}+\frac{z}{z-\mathrm{e}^{-\mathrm{j} \omega T_{e}}}\right]=\\
&\frac{z}{2} \frac{z-\mathrm{e}^{-\mathrm{j} \omega T_{e}}+z-\mathrm{e}^{\mathrm{j} \omega T_{e}}}{z^{2}-2 z \cos \omega T_{e}+1}= \\
& =\frac{z\left[z-\left(e^{\mathrm{j} \omega T_{e}}+e^{-\mathrm{j} \omega T_{e}}\right) / 2\right]}{z^{2}-2 z \cos \omega T_{e}+1}=\frac{z\left(z-\cos \omega T_{e}\right)}{z^{2}-2 z \cos \omega T_{e}+1} .
\end{aligned}
$$
--- 

---

[[SAE_curs3.pdf]]

[^1]:La această versiune de calcul a transformatei $Z$, parametrul $T_{e}$ nu apare explicit în relaţiile care rezultă astfel (se consideră $T_{e}=1$ ).


# Transformata z inversa

Procesul de trecere de la o functie de variabila complexa $F(z)$ la un semnal esantionat (descris printr-o secvventa temporala $f(kT_e)$ sau $f[k]$) se numeste **transformata $Z$ inversa** [^1]. 

Transformata $Z$ inversa se notreaza cu :

$$f[k]=f(kT_e)=Z^{-1}\{F(z)\}$$

In practica, se utilizeaza 3 metode de evaluare:

- metoda formulei de inversiune
- metoda dezvoltarii in fractii simple 
- metoda seriilor infinite de puteri ale lui $z^{-1}$

## Metoda formulei de inversiune

Matematic $f(kT_e)$ se obtine din $F(z)$ cu formula urmatoare (numita si **formula de inversiune**):

$$f[k]=f(kT_e)=\frac{1}{2 \pi j} \int _{\Gamma} F(z)z^{k-1}dz$$

unde $\Gamma$ este o curba inchisa din planul $z$ care include toti polii si zerourile functiei complexe $F(z)z^{k-1}$.

### Dezvoltare

Pentru evaluarea concreta a integralei de inversiune se foloseste teorema rezidurilor.

Metoda se bazeaza pe faptul ca majoritatea semnalelor fizice au transformata $Z$ exprimata sub forma unor functii rationale de variabila $z$, conform expresiei:

$$F(z)=\frac{b_mz^m+b_{m-1}z^{m-1}+ \ldots +b_1z+b_0}{z^n+a_{n-1}z^{n-1}+ \ldots + a_1 z +a_0} \quad, n \ge m$$

Ca si in cazul sistemelor continue, sistemele discrete fizic realizabile trebuie sa indeplineasca conditia:

$$\text{grad } A(z) \ge \text{grad } B(Z) \quad \text{sau } n \ge m$$

Se considera ca $A(z)$ are radacini simple distincte reale sau complexe (notate $p_i$).

In acest caz,, integrantul din formula de inversiuni va fi:

$$F_0(z)=\frac{B(z)z^{k-1}}{\prod^{n}_{i=1}(z-p_i)}$$

iar evaluarea cu teorema rezidurilor conduce la rezultatul:

$$f[k]=f(kT_e)=\sum^{n}_{i=1}r_i(k)$$

unde $r_i$ se calculeaza cu relatia:

$$r_i[k]=(z-p_i)F_0(z)|_{z=p_i}$$

## Metoda dezvoltarii in fractii simple

Se considera ca functia complexa $F(z)$ este o functie rationala scrisa sub forma urmatoare:

$$F(z)=\frac{b_mz^m+b_{m-1}z^{m-1}+ \ldots +b_1z+b_0}{z^n+a_{n-1}z^{n-1}+ \ldots + a_1 z +a_0} \quad, n \ge m$$

Functiile de timp esantionate se pot obtine prin dezvoltarea in fractii simple a functiei $F(z)$ (similar cu [[Transformata Laplace#^883856|transformata Laplace inversa]]). 

### Etape
1. Se calculeaza $F_1(Z)=\frac{F(z)}{z}=\frac{B(z)}{zA(z)}$ [^2]
2. Daca $A(z)$ are poli distincti ($p_{d_i}$), se dezvolta in fractii simple ($F_1(z) = \frac{c_1}{z-p_{d_1}}  + \ldots +\frac{c_i}{z-p_{d_i}}+ \ldots + \frac{c_n}{z-p_{d_n}}$)
3. Se aplica transformata $Z$ inversa fractiilor simple multiplicate cu $z$ ($f[k]=f(kT_e)=c_1(p_{d_1})^k+ \ldots+ c_i(p_{d_i})^k+ \ldots +c_n(p_{d_n})^k$)
## Metoda seriilor infinite de puteri ale lui $z^{-1}$

Functia $F(z)$ se scrie sub forma unei serii infinite de puteri. 

Considerand forma rationala a functie complexe este:

$$F(z)=\frac{b_mz^m+b_{m-1}z^{m-1}+ \ldots +b_1z+b_0}{z^n+a_{n-1}z^{n-1}+ \ldots + a_1 z +a_0} \quad, n \ge m$$

Dupa impartirea realizata dupa regula impartirii infinite a polinoamelor [^3] rezulta:

$$F(z)=f_0+f_1z^{-1}+f_2z^{-2}+ \ldots$$

Daca se compara rezultatul cu relatia de definitie a [[Transformata Z|transformatei Z]] se constata:

$$f(0)=f_0,f(T_e)=f_1,f(2T_e)=f_2, \ldots, f(kT_e)=f_k, \ldots$$

--- 

[[SAE_curs7.pdf]]

[^1]: De obicei, prin aplicarea transformatei $Z$ inverse se obtine secventa temporala $f[k]$ in care nu apare explicit perioada de esantionare $T_e$.
[^2]: De obicei $B(z)$ contine pe $z$ ca factor, deci $z$ de la numitorul functiei $F_1(Z)$ se va simplifica si acesta va avea expresia $F_1(z)=\frac{B_1(z)}{A(z)}$
[^3]: Pentru aplicarea metodei seriilor infinite de puteri ale lui $z^{-1}$ este indicat ca inainte de impartirea polinoamelor, functia complexa sa fie scrisa in forma cu variabila $z^{-1}$ astfel: $F(z^{-1})=\frac{c_0+c_1z^{-1}+c_2z^{-2}\ldots}{1+d_1z^{-1}+d_2z^{-2}\ldots}$