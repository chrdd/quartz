---
tags:
  - SistemeAutomateCuEsantionare
---
## Exercițiul 1

Să se calculeze [[Transformata Z#Transformata z inversa|transformata Z inversa]] pentru funcţia complexă:

$$F(z)=\frac{z\left(1-\mathrm{e}^{-a T_{e}}\right)}{(z-1)\left(z-\mathrm{e}^{-a T_{e}}\right)}$$

---

1. Se detemină rezidurile funcţiei:$$F_{0}(z)=\frac{z^{k-1} z\left(1-\mathrm{e}^{-a T_{e}}\right)}{(z-1)\left(z-\mathrm{e}^{-a T_{e}}\right)}=\frac{z^{k}\left(1-\mathrm{e}^{-a T_{e}}\right)}{(z-1)\left(z-\mathrm{e}^{-a T_{e}}\right)}$$pentru polii $z=+1$ şi $z=\mathrm{e}^{-a T_{e}}$. Se obţine astfel semnalul eşantionat:$$\begin{align}&f[k]=r_{1}+r_{2}=\left.\frac{z^{k}\left(1-\mathrm{e}^{-a T_{e}}\right)}{z-\mathrm{e}^{-a T_{e}}}\right|_{z=1}+\left.\frac{z^{k}\left(1-\mathrm{e}^{-a T_{e}}\right)}{z-1}\right|_{z=\mathrm{e}^{-a T_{e}}} \\&=1-\mathrm{e}^{-a k T_{e}}\end{align}$$

2. Urmărindu-se etapele algoritmului metodei descompunerii în fracţii simple rezultă succesiv:$$\begin{align}&F_{1}(z)=\frac{F(z)}{z}=\frac{1-\mathrm{e}^{-a T_{e}}}{(z-1)\left(z-\mathrm{e}^{-a T_{e}}\right)}, \\&F_{1}(z)=\frac{c_{1}}{z-1}+\frac{c_{2}}{z-\mathrm{e}^{-a T_{e}}}\end{align}$$unde:$$\begin{align}&c_{1}=\left.\frac{1-\mathrm{e}^{-a T_{e}}}{z-\mathrm{e}^{-a T_{e}}}\right|_{z=1}=1,   \\&c_{2}=\left.\frac{1-\mathrm{e}^{-a T_{e}}}{z-1}\right|_{z=\mathrm{e}^{-a T_{e}}}=-1\end{align}$$Astfel, se obţine:$$F(z)=\frac{z}{z-1}-\frac{z}{z-\mathrm{e}^{-a T_{e}}}$$de unde, prin aplicarea transformatei $Z$ inverse, rezultă:$$f\left(k T_{e}\right)=1-\left(\mathrm{e}^{-a T_{e}}\right)^{k}, \quad k \geq 0$$

## Exercițiul 2

Să se determine secvenţa temporală a semnalului $f\left(k T_{e}\right)$ cu [[Transformata Z#Metoda seriilor infinite de puteri ale lui $z {-1}$|metoda seriilor infinite de puteri ale lui z-1]], pentru funcţia complexă:

$$

\begin{equation*}

F(z)=\frac{z(z+1)}{(z-1)(z-0,5)} \tag{4.145}

\end{equation*}

$$

---

Se calculează mai întâi forma în $z^{-1}$ :

$$F\left(z^{-1}\right)=\frac{1+z^{-1}}{1-1,5 z^{-1}+0,5 z^{-2}}$$

apoi se împart cele două polinoame conform schemei prezentate în continuare:

![[Pasted image 20240304170941.png]]

Prin comparaţie directă cu:

$$

F(z)=\sum_{k=0}^{+\infty} f[k] z^{-k}

$$

rezultă secvenţa temporală

$$f[0]=1 ; f[1]=2,5 ; f[2]=3,25 ; f[3]=3,625 ; \ldots$$

care poate fi scrisă în mod echivalent $$\left\{f\left(k T_{e}\right)\right\}=\{1 ; 2,5 ; 3,25 ; 3,625 ; \ldots\}$$

Calculul analitic cu metoda seriilor infinite de puteri ale lui $z^{-1}$ este laborios, preferându-se în acest caz calculul numeric asistat de calculator.

## Exercițiul 3

Se va analiza răspunsul sistemului discret cu element de reţinere de ordin zero, cu schema bloc prezentată în figura urmatoare:

![](https://cdn.mathpix.com/cropped/2024_03_04_e1e0bee3e9c9436e6cd4g-2.jpg?height=235&width=1219&top_left_y=1847&top_left_x=424)

---

Funcţia de transfer a elementului continuu cu ER se determină cu relaţiile succesive:

$$
\begin{align}
&G_{E R} G(z)=Z\left\{\frac{1-e^{-s T_{e}}}{s} G(s)\right\} \\
&=\left(1-z^{-1}\right) Z\left\{\frac{K}{s^{2}(s+1)}\right\}\\
&=K\left(1-z^{-1}\right) Z\left\{\frac{1}{s^{2}}-\frac{1}{s}+\frac{1}{s+1}\right\}
\end{align}
$$

respectiv

$$
G_{E R} G(z)=K\left(1-z^{-1}\right)\left[\frac{T_{e} z}{(z-1)^{2}}-\frac{z}{z-1}+\frac{z}{z-e^{-T_{e}}}\right]
$$
de unde după efectuarea calculelor se obţine:

$$
G_{E R} G(z)=K \frac{z\left(e^{-T_{e}}+T_{e}-1\right)+\left(1-e^{-T_{e}}-T_{e} e^{-T_{e}}\right)}{z^{2}-\left(1+e^{-T_{e}}\right) z+e^{T_{e}}}
$$

Înlocuind $T_{e}=0,3 \mathrm{~s}$ şi $K=1$ rezultă funcţiile de transfer $z$ ale sistemului discret în circuit deschis:

$$
G_{E R} G(z)=\frac{0,04082 z+0,03694}{z^{2}-1,741 z+0,7408}
$$

respectiv a sistemului în circuit închis:

$$
G_{0}(z)=\frac{0,04082 z+0,03694}{z^{2}-1,7 z+0,7778}
$$

Sistemul discret cu element de reţinere de ordinul zero a fost simulat în MATLAB şi răspunsul obținut este prezentat grafic în figura 4.46 .

Folosind meniul Characteristic în fereastra grafică MATLAB obţinută cu funcţia step se constată că în acest caz suprareglajul este de $\sim 23 \%$, deci mult mai mic decât la sistemul eşantionat fără ERO, fiind destul de aproape de valoarea suprareglajului sistemului continuu. Acest fapt rezultă ca urmare a valorii mici a perioadei de eşantionare.

Din grafic se observă, de asemenea, că timpul de stabilire (cu valoarea de 8,75) este mai mare decât la sistemul continuu şi la sistemul eşantionat fără ERO.

Cu toate că suprareglajul sistemului cu ERO este sensibil mai mic decât la sistemul eşantionat fără ERO, totuşi rezerva de stabilitate a primului este mult mai mică. Astfel, valoarea factorului de amplificare $K$ la limita de stabilitate este $K=7$ la sistemul cu ER0, faţă de $K=13,43$ cât este la sistemul eşantionat fără ERO.

![](https://cdn.mathpix.com/cropped/2024_03_04_e1e0bee3e9c9436e6cd4g-3.jpg?height=594&width=1008&top_left_y=1716&top_left_x=524)

Fig. 4.49

Din examinarea curbelor prezentate se constată că, în cazul unei perioade de eşantionare mai mică ( $T_{e}=0,15$ în loc de $0,3 \mathrm{~s}$ ) la sistemul eşantionat fără ER0 suprereglajul creşte în mod apreciabil (fiind acum de $60,7 \%$ faţă de $42 \%$ ). De asemenea, craşte gradul de oscilaţie în intervalul corespunzător regimului tranzitoriu. Cu toate acestea durata timpului de stabilire se modifică puţin (de la 7,5 la 7,3 s) şi în

mod aparent paradoxal rezerva de stabilitate creşte de aproximativ 3 ori (la limita de stabilitate avem $K=40,35$ pentru sistemul cu $T_{e}=0,1$, respectiv $K=13,43$ la sistemul cu $\left.T_{e}=0,3\right)$.

În ceea ce priveşte sistemul discret cu ERO se constată că la reducerea perioadei de eşantionare se reduce şi suprareglajul (de la $23 \%$ la $T_{e}=0,3$ la $18,4 \%$ pentru sistemul cu $T_{e}=0,1$ ). De asemenea, se reduce timpul de stabilire, care la $T_{e}=0,1$ este de $8,3 \mathrm{~s}$ şi în general răspunsul sistemului discret se apropie mult de cel al sistemului continuu. Cu toate acestea rezerva de stabilitate, care creşte de la 7 pentru $T_{e}=0,3$ la 20,7 pentru $T_{e}=0,1$, este cu mult mai mică decât cea a sistemului continuu.

Concluzionând, prin eşantionare se reduce rezerva de stabilitate şi creşte suprareglajul, respectiv gradul de oscilaţie (numai la sistemele fără ER0).

#### Exercițiul 4

Considerăm sistemul cu ecuaţia caracteristică în $z$

$$
A_{z}(z)=(z+1)(z+0.5)(z+2)=z^{3}+3.5 z^{2}+3.5 z+1
$$

Folosind criteriul Routh să se evalueze stabilitatea sistemului discret.

---

Din expresia factorizată a ecuaţiei caracteristice se constată uşor că sistemul este instabil deoarece o rădăcină este egală cu 1 (aşadar plasată pe cercul de rază unitară), iar alta are valoarea -2 , deci este în afara cercului de rază unitară.

Pentru a aplica criteriul Routh se aplică schimbarea de variabilă ecuaţiei caracteristice în z: Astfel se obţine:

$$
\begin{aligned}
& P(r)=\left(\frac{r+1}{r-1}\right)^{3}+3.5\left(\frac{r+1}{r-1}\right)^{2}+3.5\left(\frac{r+1}{r-1}\right)+1, \\
& P(r)=\frac{(r+1)^{3}+3.5(r+1)(r-1)(r+1+r-1)+(r-1)^{3}}{(r-1)^{3}}=\frac{9 r^{3}-r}{(r-1)^{3}},
\end{aligned}
$$

de unde se obţine ecuaţia caracteristică în $r, A_{r}(r)=9 r^{3}-r$ cu tabloul Routh:

| $r^{3}$ | 9 | -1 |
| :---: | :---: | :---: |
| $r^{2}$ | $0 ; 27$ | $0 ;-1$ |
| $r^{1}$ | $\frac{-9+27}{27}=-\frac{18}{27}=\frac{2}{3}$ | 0 |
| $r^{0}$ | -1 | 0 |

Deoarece coeficienţii din rândul doi sunt toți egali cu zero aceştia se înlocuiesc cu valorile obţinute după derivarea polinomului format cu coeficienţii din rândul anterior adică, $\frac{\mathrm{d} A_{r}(r)}{\mathrm{d} r}=27 r^{2}-1$. Examinând termenii din prima coloană se observă că există o schimbare de semn deci sistemul discret este instabil. Rezultatul obţinut (sistem instabil) era previzibil deoarece:

1. nu toţi coeficienţii polinomului caracteristic $A_{r}(r)$ sunt pozitivi şi diferiţi de zero;
2. rădăcinile ecuaţiei caracteristice $A_{r}(r)=9 r^{3}-r$, care se pot calcula uşor, sunt $r_{1}=0, r_{2,3}= \pm 1 / 3$. Prin urmare avem o rărdăcină nulă şi una în semiplanul complex drept.

O aplicaţie interesantă a criteriului Routh este analiza stabilităţii sistemele discrete în funcţie de valorile perioadei de eşantionare.
