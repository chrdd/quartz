---
tags:
  - SistemeAutomateCuEsantionare
aliases:
  - Curs 8 SAE
---

Stabilitatea sistemelor discrete cu reactie negativa poate fi evaluata, ca si la sisteme continue, pe baza pozitiei in planul $z$ a polilor functiei de transfer a sistemului in circuit inchis.

Pentru a putea determina aceasta, trebuie efectuata transformarea din planul $s$ in planul $z$.

## Transformarea din planul $s$ in planul $z$

Transformarea din planul $s$ in planul $z$ se face utilizand schimbarea de variabila cu formula:

$$z=e^{sT_e}$$

cu ajutorul careia se obtine functia de transfer $z$ din functia de transfer $s$. 

Astfel, semiplanul complex $s$ este transformat intr-un cerc de raza unitara in planul complex $z$. 

## Criteriul de stabilitate

Stabilitatea sistemelor continue absoluta este asigurata daca toti polii (radacinile polinomului de la numitor) functiei de transfer a sistemului in circuit inchis sunt plasati in semiplanul stang al spatiului complex $s$ (polii trebuie sa aiba **partea reala negativa**)

Prin urmare, sistemele discrete cu reactie negativa sunt stabile daca **toti polii functiei de transfer $z$ sunt amplasati in interiorul cercului de raza unitara (in planul $z$)**

Stabilitatea unui sistem liniar discret este o proprietate intrinseca a sistemului care nu depinde de marimea de intrare a sistemului. 

Polii transformatei $Z$ a marimii de intrare nu afecteaza proprietatea de stabilitate a sistemului, acestia determinand numai raspunsul stationar. 

Prin urmare, ca si la sistemele continue, problema stabilitatii se poate rezolva alegand polii functiei de transfer a sistemului inchis astfel încât aceştia să fie amplasaţi în planul $z$ în interiorul cercului de rază unitară. 

Polii sistemului închis cu $|p_i|=1$ vor produce, în cadrul răspunsului, oscilaţii întreţinute de amplitudine constantă. Se remarcă totuşi şi faptul că amplasarea tuturor polilor în interiorul cercului de razăunitară nu garantează valori satisfăcătoare pentru performanţele răspunsului.

Dacă polii complex conjugaţi dominanţi ai sistemului închis au modul $\approx 1$ (dar $<1$) raspunsul tranzitoriu poate să prezinte oscilaţii de amplitudine mari sau răspunsul estelent. 

În sistemele practice, pe lângă semnalele utile, există semnale parazite care pot face ca amplitudinea oscilaţiilor să crească cu o viteză determinată de puterea zgomotului, fiind posibilă apariţia pericolului ca sistemul să devină instabil.

## Notatii

Pentru stabilirea notatiilor se considera sistemul discret in circuit inchis cu esantionarea erorii, avand urmatoarea schema bloc:

![[2023-08-02T12:29:15,520440474+03:00.png]]

Conform [[Transformata Z#Transformata z inversa|transformatei Z inverse]], functia de transfer $z$ a sistemului in circuit inchis este:

$$G_0(z)=\frac{Y(z)}{R(z)}=\frac{G(z)}{1+GH(z)}=\frac{B(z)}{A(z)}$$

unde polinomul de la numitor are expresia generala:[^1]

$$A(z)=a_0z^n+a_1z^{n-1}+\ldots+a_kz^{n-k}+\ldots+a_{n-1}z+a_n$$

Notand cu $p_i$ radacinile polinomului $A(z)$ (*polii sistemului*), avem urmatoarea conditie de stabilirea a sistemului discret:

>[!info] 
>Daca toti polii $p_i$ ai functiei de transfer $G_0(z)$ sunt amplasati in planul $z$ in interiorul cercului de raza unitara, atunci toate componentele raspunsului tranzitoriu ajung la starea de echilibru si prin urmare sistemul discret este stabil.

Matematic, conditia de stabilitate se exprima astfel:

$$|p_i|<1, \quad i=1,\ldots,n$$

---

[[SAE_curs8.pdf]]

[^1]: De regula, $a_0=1$