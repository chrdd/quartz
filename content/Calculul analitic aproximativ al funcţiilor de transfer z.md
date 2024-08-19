---
tags:
  - SistemeAutomateCuEsantionare
aliases:
  - Curs 5 SAE
---

În literatură se prezintă diverse modalităţi de calcul analitic aproximativ al funcţiilor de transfer $z$. În cele ce urmează se vor prezenta două metode.

## Calculul analitic aproximativ bazat pe substituţii algebrice de tipul $s=f(z)$

Prima metodă se bazează pe unele substituţii algebrice, prin care se înlocuieşte variabila complexă $s$ cu o anumită funcţie de variabilă $z$. Relaţiile de schimbare a variabilei $s$ se introduc pornind de la metodele de integrare prezentate în exemplul anterior. Având în vedere că funcţia de transfer a unui integrator analogic este $\frac{1}{s}$ şi funcţiile de transfer $z$ ale integratoarelor numerice prezentate mai înainte, rezultă următoarele relaţii de schimbare a variabilei $s$: 

$$s \rightarrow \frac{z-1}{z T_{e}}=\frac{1-z^{-1}}{T_{e}}, \operatorname{MDS} \text{(BRR-Backward Rectangular Rule)}$$


$$s \rightarrow \frac{z-1}{T_{e}}=\frac{1-z^{-1}}{z^{-1} T_{e}} \text{, MDF (FRR-Forward Rectangular rule)}$$


$$s \rightarrow \frac{2}{T_{e}} \frac{z-1}{z+1}=\frac{2}{T_{e}} \frac{1-z^{-1}}{1+z^{-1}}\text{, MT (TR-trapezoid rule)}$$


Funcţiile de transfer $z$ se calculează cu relaţiile:

$$G_{\text {MDS }}(z)=\left.G(s)\right|_{s=\frac{z-1}{z T_{e}}}\text{, MDS (BRR-Backward Rectangular Rule)}$$


$$G_{\text {MDF }}(z)=\left.G(s)\right|_{s=\frac{z-1}{T_{e}}} \text{, MDF (FRR-Forward Rectangular rule)}$$


$$G_{M T}(z)=\left.G(s)\right|_{s=\frac{2}{T_{e}} \frac{z-1}{z+1}} \text{, MT (TR-trapezoid rule)}$$

Se remarcă faptul că substituţiile se fac în funcţia de transfer a elementului continuu de sistem $G(s)$, dar procesul discretizat care este astfel modelat conţine totuşi şi elementul de reţinere de ordin zero. Substituţia bazată pe metoda de integrare a trapezului este cunoscută în literatură sub denumirea de [[Transformata Z|transformata Z]] biliniară sau **metoda Tustin**.

Precizia modelelor obţinute prin substituţii algebrice este puternic influenţată de valoarea adoptată a perioadei de eşantionare.

## Calculul analitic aproximativ cu metoda transformatei z care conservă repartiţia poli-zerouri a sistemului continuu

O altă modalitate de calcul aproximativ a [[Transformata Z|transformatei Z]] este metoda [[Transformata Z|transformatei Z]] care conservă repartiţia poli-zerouri a sistemului continuu (Pole-zero Matched Z Transform). La [[Transformata Z|transformata Z]] exactă s-a remarcat faptul că polii $p_{d}$ ai funcţiei de transfer $G(z)$ sunt corelaţi cu polii sistemului continuu, $-p_{c}$):

$$p_{d}=\mathrm{e}^{-p_{c} T_{e}}$$

[[Transformata Z|Transformata Z]] cu conservarea repartiţiei poli-zerouri a sistemului continuu presupune că o relaţie similară există şi pentru zerourile finite. Dacă $n>m$, unde $n$ este gradul polinomului de la numitorul lui $G(s)$ iar $m$ este gradul polinomului de la numărător, atunci funcţia de transfer $G(z)$ se completează cu $(n-1)$ factori $(z+1)$ la numărător. Factorul de amplificare $K_{d}$ al funcţiei de transfer discrete se determină, folosind comportarea în regim staţionar a sistemului continuu respectiv discret, cu relaţia:

$$\lim _{s \rightarrow 0}\left\{(s)^{\alpha} G(s)\right\}=\lim _{z \rightarrow 1}\left\{\left(\frac{z-1}{z T_{e}}\right)^{\alpha} G(z)\right\}$$

unde $\alpha=0$ sau 1 , este tipul sistemului determinat de $G(s)$, respectiv de ordinul integratorului care apare în funcţia de transfer a sistemului continuu. Rezumând, paşii de calcul ai transformatei Z matched sunt:

### Pasul 1

Se transformă polii şi zerourile finite conform relaţiei $p_{d}=\mathrm{e}^{-p_{c} T_{e}}, z_{d}=\mathrm{e}^{-z_{c} T_{e}}$; 

### Pasul 2 (opţional)

Dacă numărătorul funcţiei de transfer $G(s)$ are gradul mai mic decât cel al numitorului, în funcţia de transfer $G(z)$ se adaugă la numărător factori de forma $(z+1)$;

### Pasul 3

Se calculează factorul de amplificare $K_{d}$.

## Transformata z matched
Explicatia anterioara este inutila

Pasii necesari realizarii transformatei z matched sunt:
### Pasul 1: mapeaza fiecare pol si zero in planul z
Se realizeaza folosind [[Transformata Z|transformata z]].

### Pasul 2: adauga zerouri la infinit daca este necesar
Chiar daca nu exista zerouri scrise in functie, ele exista la infinit. Numarul de poli si zerouri intr-o functie de transfer este mereu egal. Se adauga astfel zerouri la infinit, adica $z=-1$ sau $(z+1)$ la numitor.

### Pasul 3: scoate zerourile la infinit pentru a crea o functie de transfer strict realizabila
Se sterg poli la infinit pana cand functia de transfer este strict realizabila, adica numarul de poli sa fie egal cu numarul de zerouri -1.


### Pasul 4: ajusteaza factorul de amplificare ($k_{d}$)

Pentru a afla factorul de amplificare in planul $s$, se echivaleaza $s$ cu $0$, iar in planul $z$, se echivaleaza $z$ cu $1$. Astfel, vom rezolva ecuatia: $$G(s)=G(z) \cdot k_{d}$$

![](https://youtu.be/TPNiLqsdwNI?si=-4mFzedBItjmfz_S)
