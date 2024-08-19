---
tags:
  - PrelucrareaSemnalelor
---

![[Transformata Fourier#Transformata fourier continua]]

---

#TeoriaSistemelor 

## Definitie

Functiile de transfer constituie un instrument pentru modelarea, analiza si simularea sistemelor liniare inveriate in timp. 

In cele mai multe cazuri, procesele fizice (inclusiv cele electrice) pot fi considerate initial ca *sisteme liniare cu parametrii constanti in timp* (invariabile in timp). 

Aceasta abordare se foloseste pentru a simplifica metodele de analiza si proiectare a sistemelor de reglare.

Functia de transfer a unui sistem liniar invariabil in timp se defineste ca fiind raportul dintre [[Transformata Laplace|transformata Laplace]] a marimii de iesire si [[Transformata Laplace|transformata Laplace]] a marimii de intrare, toate conditiile initiale fiind nule.

Sistemele fizice au functii de transfer care respecta conditia $n>m$. Gradul polinomului de la numitorul functiei de transfer ($n$) determina **ordinul sistemului** (de obicei se spune ca functia de transfer este de ordinul $n$). 

>[!important] Observatii
>Functia de transfer este un model matematic asociat unui proces fizic care descrie complet comportarea dinamica a acestuia.
>
>Functia de transfer este proprietate intrinseca a sistemului modelat, fiind independenta de natura si valoarea numerica a marimii de intrare.
>
>Functia de transfer nu prezinta nici o informatie despre natura fizica a sistemului.
>
>Functia de transfer include in coeficientii ei unitatile de masura ale marimilor de intrare si iesire.
>
>Functia de transfer se poate determina experimental daca nu este cunoscuta prin aplicarea unei marimi de intrare cunoscute si studierea raspunsului ulterior.

Functia de transfer reprezinta o descriere intrare-iesire a sistemelor si se obtine aplicand [[Transformata Laplace|transformata Laplace]] in conditii initiale nule ecuatiei diferentiale.

In cazul sistemelor liniare continue in timp, functia de transfer $G(s)$ este data de un raport de doua polinoame de variabila complexa $s$, adica $G(s)$ de forma 

$$G(s)=\frac{Y(s)}{U(s)}=\frac{b_0s^m+b_1s^{m-1}+\ldots+b_{m-1}s+b_m}{s^n+a_1s^{n-1}+\ldots+a_{n-1}s+a_n}$$

unde $n \geq m$.

Rădăcinile polinomului de la numărătorul funcției $G(s)$ se numesc **zerourile sistemului**, iar radacinile polinomului de la numitorul functiei $G(s)$ se numesc **polii sistemului**. 

Ecuatia obtinuta prin egalarea cu zero a numitorului lui $G(s)$ se numeste **ecuatia caracteristica a sistemului**:

$$s^n+a_1s^{n-1}+\ldots+a_{n-1}s+a_n=0$$

In MatLab , pentru a reprezenta o functie de transfer, se foloseste functia **$\text{tf}$** astfel:

```MatLab
G=tf(num,den)
```

unde $\text{num}, \text{den}$ reprezinta numaratorul, respectiv numitorul functiei de transfer, rezultand astfel un sistem continuu; aceste se pot introduce in MatLab ca vectori linie continand coeficientii polinomului in ordinea descrescatoare puterilor variabilei; 

Daca se specifica si perioada de esantionare atunci va rezulta un sistem discret, sau

```MatLab
s=tf('s')
G=1/(s^2+3*s+1);
```

Rădăciniile funcției de transfer, adică polii și zerourile, se pot determina folosind funcția **$\text{roots}$** sau reprezenta grafic folosind funcția **$\text{pzmap}$**, astfel:

```MatLab
pzmap(num,den)
```

Zerourile sunt reprezentate cu "$o$" şi polii cu "$x$".[^1]

## Exemplu

Sa se determine functia de transfer pentru circuitul in serie $RL$ cu schema urmatoare:

![[Circuit RL.png]]

Marimea de intrare este tensiunea aplicata la bornele $u(t)=u_i(t)$, iar marimea de iesire se considera curentul de circuit $y(t)=I(t)$.

### Rezolvare

Scriind legea a doua a lui Kirchhoff pentru circuitul din figură rezultă ecuaţia diferenţială:

$$
u_i(t)=u_R(t)+u_L(t)=R i(t)+L \frac{d i(t)}{d t} \text {. }
$$

Aplicând în continuare [[Transformata Laplace|transformata Laplace]] acestei ecuaţii, în ipoteza unei condiţii iniţiale nule pentru curent $i(0)=0$, se obţine ecuaţia algebrică:

$$
U_i(s)=l(s)(R+s L)
$$

de unde, conform definiţiei funcţiei de transfer, rezultă:

$$
G(s)=\frac{I(s)}{U_i(s)}=\frac{Y(s)}{U(s)}=\frac{1}{s L+R}
$$

Funcţia de transfer dedusă mai înainte se poate scrie în formă echivalentă :

$$
G(s)=\frac{I(s)}{U_i(s)}=\frac{Y(s)}{U(s)}=\frac{K}{s T+1}, \text { unde } K=\frac{1}{R} \text { şi } T=\frac{L}{R} \text {. }
$$

Coeficientul $K$ se numeşte factor de amplificare (câştig) de regim staţionar (DC-gain). În general, factorul de amplificare se obţine cu relaţia:

$$
K=\lim _{s \rightarrow 0} G(s)
$$

Procesele fizice modelate prin funcţii de transfer de forma:

$$
G(s)=\frac{b_0}{a_0 s+a_1} \text {, }
$$

se numesc sisteme de ordinul întâi. $\mathrm{O}$ formă echivalentă pentru functiia de transfer a unui element de ordinul întâi, numită în continuare formă standard, este conform relatiei:

$$
G(s)=\frac{K}{T s+1}
$$

unde $K$ şi $T$ au semnificaţiile din exemplul 1.16.

Sistemele de ordinul întâi vor fi notate în cadrul cursului cu acronimul T1. Sistemele T1 posedă un singur pol real:

$$
-p_1=-\left(a_1 / a_0\right) \text { sau }-p_1=-(1 / T)
$$

[^1]: Daca funcția pzmap se apelează $[p,z]=pzmap$ atunci se determină polii și zeorurile fără a fi reprezentați grafic.