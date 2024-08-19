---
tags:
  - TehniciDeInteligentaArtificiala
title: Bilete examen TIA
---
## Bilet 1

**Un controler fuzzy are 2 intrări şi o ieşire.**

**Prima variabilă de intrare este eroarea semnalului $u 1\left(e_{p}=p_{r}-p_{a}, p_{r}\right.$ este valoarea de referință a intrării 1 iar $p_{a}$ valoarea actuală) şi este definită pe domeniul $(-50,56)$ fiind caracterizată de funcțiile de apartenență:**

$$
\begin{align}
\mu_{N B}(u)=L(u,-42,-32),  \\
\mu_{N M}(u)=\Pi(u,-37,-32,-25,-10),  \\
\mu_{N S}(u)=\Pi(u,-18,-15,-10,0),  \\
\mu_{Z E}(u)=\Lambda(u,-6,0,8),  \\
\mu_{P S}(u)=\Lambda(u0,5,18),  \\
\mu_{P M}(u)=\Lambda(u, 14,30,45),  \\
\mu_{P B}(u)=\Gamma(u, 37,50)
\end{align}
$$

**Cea de a doua variabilă de intrare este eroare semnalului $u 2$ ($e_{s}=s_{r}-s_{a}, s_{r}$ este valoarea de referință a intrării 2 iar $\mathrm{s}_{\mathrm{a}}$ valoarea actuală) şi este definită pe domeniul $(-20,20)$ fiind caracterizată de funcțiile de apartenență:**

$$
\begin{align}
\mu_{N B}(u)=L(u,-15,-11),  \\
\mu_{N M}(u)=\Pi(u,-13,-11,-6,-4),  \\
\mu_{N S}(u)=\Pi(u,-6,-4,-1,0),  \\
\mu_{Z E}(u)=\Lambda(u,-1,0,1),  \\
\mu_{P S}(u)=\Pi(u0,1,4,6),  \\
\mu_{P M}(u)=\Pi(u, 4,6,11,15),  \\
\mu_{P B}(u)=\Gamma(u, 11,15)
\end{align}
$$

**Variația semnalul de comandă $\Delta y$ este caracterizată pe domeniul $(-23,23)$ de funcțiile:**

$$
\begin{align}
\mu_{N B}(u)=L(u,-21,-17),  \\
\mu_{N M}(u)=\Pi(u,-21,-17,-8,-5), \\
\mu_{N S}(u)=\Pi(u,-8,-7,-1,0), \\
\mu_{Z E}(u)=\Lambda (u,-1,0,3), \\
\mu_{P S}(u)=\Pi(u,0,6,10,13),  \\
\mu_{P M}(u)=\Pi(u, 11,15,17,21), \\
 \mu_{P B}(u)=\Gamma(u, 17,21)
\end{align}
$$

**Controlerul este caracterizat de urmărtoarea tabelă de inferență:**

| $e p \rightarrow$ <br> $e s \downarrow$ | NB | NM | NS | ZE | PS | PM | PB |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| NB | PB | PB | PB | PB | PB | PM | PM |
| NM | PM | PM | PM | PM | PS | PS | PS |
| NS | PS | PS | PS | PM | PS | PS | PS |
| ZE | ZE | ZE | ZE | ZE | ZE | ZE | ZE |
| PS | NS | NS | NS | NS | NS | NS | NS |
| PM | NS | NS | NS | NM | NM | NM | NM |
| PB | NS | NS | NM | NM | NM | NM | NM |

**Ştiind că $\mathrm{p}_{\mathrm{r}}=11, \mathrm{p}_{\mathrm{a}}=8.3$ şi $\mathrm{s}_{\mathrm{r}}=-21.3, \mathrm{~s}_{\mathrm{a}}=-9$, să se calculeze folosind metoda inaltimii si metoda primului maxim variatia $\Delta y$ la momentul actual.**

---

$$
\begin{align}
e_{p} - \text{eroarea semnaului }u_{1} (\text{prima variabila de intrare}) \\
p_{r}- \text{valoarea de referinta a intrarii }1 \\
p_{a}- \text{valoarea actuala }
\end{align}
$$

$$
e_{p}=p_{r}-p_{a}
$$

$$
e_{p}=(-50,56 ) (\text{pe acest domeniu este definita})
$$

$$
e_{p}= \begin{cases}
\mu_{NB}(e_{p})=L(e_{p},-42,-32) \\
\mu_{NM}(e_{p})= \Pi (e_{p},-37,-32,-25,-10) \\
\mu_{NS}(e_{p})=\Pi(e_{p},-18,-15,-10,0) \\
\mu_{ZE}(e_{p})=\Lambda(e_{p},-6,0,8) \\
\mu_{PS}(e_{p})=\Lambda(e_{p},0,5,18) \\ 
\mu_{PM}(e_{p})=\Lambda(e_{p},14,30,45) \\
\mu_{ZE}(e_{p})=\Gamma(e_{p},37,50) \\
\end{cases}
$$

$$
\begin{align}
e_{s} - \text{eroarea semnaului }u_{2} (\text{cea de-a doua variabila de intrare}) \\
s_{r}- \text{valoarea de referinta a intrarii }2 \\
s_{a}- \text{valoarea actuala }
\end{align}
$$

$$
e_{s}=s_{r}-s_{a}
$$

$$
e_{s}=(-20,20)(\text{pe acest domeniu este definita})
$$

$$
e_{s}= \begin{cases}
\mu_{NB}(e_{s})=L(e_{s},-15,-11) \\
\mu_{NM}(e_{s})= \Pi (e_{s},-13,-11,-6,-4) \\
\mu_{NS}(e_{s})=\Pi(e_{s},-6,-4,-1,0) \\
\mu_{ZE}(e_{s})=\Lambda(e_{s},-1,0,1) \\
\mu_{PS}(e_{s})=\Pi(e_{s},0,1,4,6) \\ 
\mu_{PM}(e_{s})=\Pi(e_{s},4,6,11,15) \\
\mu_{ZE}(e_{s})=\Gamma(e_{p},11,15) \\
\end{cases}
$$

Variatia semnalului de comanda $\Delta y$ este caracterizata pe domeniul:

$$
\Delta y=\begin{cases}
\mu_{NB}(\Delta y)=L(\Delta y,-21,-17) \\
\mu_{NM}(\Delta y)= \Pi (\Delta y,-21,-17,-8,-5) \\
\mu_{NS}(\Delta y)=\Pi(\Delta y,-8,-7,-1,0) \\
\mu_{ZE}(\Delta y)=\Lambda(\Delta y,-1,0,3) \\
\mu_{PS}(\Delta y)=\Pi(\Delta y,0,6,10,13) \\ 
\mu_{PM}(\Delta y)=\Pi(\Delta y,11,15,17,21) \\
\mu_{ZE}(\Delta y)=\Gamma(\Delta y,17,21) \\
\end{cases}
$$

Tabelul de inferenta:

| $e p \rightarrow$ <br> $e s \downarrow$ | NB | NM | NS | ZE | PS | PM | PB |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| NB | PB | PB | PB | PB | PB | PM | PM |
| NM | PM | PM | PM | PM | PS | PS | PS |
| NS | PS | PS | PS | PM | PS | PS | PS |
| ZE | ZE | ZE | ZE | ZE | ZE | ZE | ZE |
| PS | NS | NS | NS | NS | NS | NS | NS |
| PM | NS | NS | NS | NM | NM | NM | NM |
| PB | NS | NS | NM | NM | NM | NM | NM |

$$
\begin{cases}
e_{p}=p_{r}-p_{a} \implies e_{p}=11-8.3=2.7 \\
e_{s}=s_{r}-s_{a} \implies e_{s}=-21.3-(-9)=-12.3
\end{cases}
$$

![[Pasted image 20240119174158.png]]


$$
\begin{cases}
\mu_{NB}(2,7)=0 \\
\mu_{NM}(2,7)=0 \\
\mu_{NS}(2,7)=0 \\
\mu_{ZE}(2,7)=\frac{8-2,7}{8-0}=\frac{5,3}{8}=0,662 \\
\mu_{PS}(2,7)=\frac{2,7-0}{5-0}=\frac{2,7}{5}=0,54 \\
\mu_{PM}(2,7)=0 \\
\mu_{PB}(2,7)=0
\end{cases}
$$
![[Pasted image 20240119174710.png]]


$$
\begin{cases}
\mu_{NB}(12,3)=\frac{11-(-12,3)}{11-(-15)}=\frac{1,3}{4}=0,325 \\
\mu_{NM}(12,3)=-\frac{12,3-(-13)}{-11-(-13)}=\frac{0,7}{2}=0,35 \\
\mu_{NS}(12,3)=0 \\
\mu_{ZE}(12,3)=0 \\
\mu_{PS}(12,3)=0 \\
\mu_{PM}(12,3)=0 \\
\mu_{PB}(12,3)=0
\end{cases}
$$
Se realizeaza tabelul de inferenta

| $e p \rightarrow$ <br> $e s \downarrow$ | $NB$ <br> $0$ | $NM$ <br> $0$ | $NS$ <br> $0$ | $ZE$ <br> $0,662$ | $PS$ <br> $0,54$ | $PM$ <br> $0$ | $PB$ <br> $0$ |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| $NB$ <br> $0,325$ | 0 | 0 | 0 | $PB$ <br> $0,325$ | $PB$ <br> $0,325$ | 0 | 0 |
| $NM$ <br> $0,35$ | 0 | 0 | 0 | $PM$ <br> $0,35$ | $PS$ <br> $0,35$ | 0 | 0 |
| $NS$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| $ZE$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| $PS$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| $PM$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| $PB$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

![[Pasted image 20240119180348.png]]

1. **Metoda primului maxim**

$$
\frac{p-0}{6-0}=\frac{0,35}{1}\implies \frac{p}{6}=0,35 \implies p=2,1
$$
2. **Metoda ultimului maxim**

$$
\begin{align}
\frac{21-p}{21-17}=\frac{0,35}{1}\implies \frac{21-p}{4}=0,35\implies 21-p=4 \cdot 0,35 \\
\implies p=21-4 \cdot 0,35 \\
\implies p=21-1,4 \\
\implies p=19,6
\end{align}
$$
3. **Metoda mijlocului maxim**

$$
2,1+19,6=21,7 \div 2=10,85
$$
4. **Metoda inaltimii**

$$
\Delta y=\frac{\sum_{k=1}^{4}ck \cdot hk}{\sum_{k=1}^{4}hk} \quad(\text{formula centrului de greutate})
$$

$$
\begin{cases}
h_{1}=h_{2}=0,325 \\
h_{3}=h_{4}=0,35
\end{cases}
$$
**Calculul $C_{1}$**

$$
y_{1,1}=23
$$

$$
\begin{align}
\frac{y_{1,2}-17}{21-17}=\frac{h_{1}}{1} \implies y_{1,2}-17=(21-17)h_{1} \\
\implies y_{1,2}=(21-17)h_{1}+17 \\
\implies y_{1,2}=4 \cdot 0,325 + 17 \\
\implies y_{1,2}=1,3+17  \\
\implies y_{1,2}=18,3
\end{align}
$$


$$
\begin{align}
C_{1}= \frac{y_{1,1}+y_{1,2}}{2}=\frac{23+18,3}{2}=\frac{41,3}{2}=20,65 \\
\implies C_{1}=20,65
\end{align}
$$
**Calculul $C_{2}$**
$$
y_{2,1}=y_{1,1}\implies y_{2,1}=23
$$

$$
y_{2,2}=y_{1,2}\implies y_{2,2}=
18,3
$$

$$
C_{2}=\frac{y_{2,1}+y_{2,2}}{2}=20,65
$$



**Calculul $C_{3}$**
$$
\begin{align}
\frac{21-y_{3,1}}{21-17}=\frac{h_{3}}{1}\implies 21-y_{3,1}=(21-17) h_{3} \\
\implies -y_{3,1}=(21-17) h_{3} -21 \\
\implies -y_{3,1}=4 \cdot 0,35 -21 \\
\implies -y_{3,1}=1,4-21 \\
\implies -y_{3,1}=-19,6 \\
\implies y_{3,1}=-19,6
\end{align}
$$

$$
\begin{align}
\frac{y_{3,2}-11}{15-11}=\frac{h_{3}}{1}\implies y_{3,2}-11=(15-11) \cdot h_{3} \\
\implies y_{3,2}=(15-11) \cdot h_{3} + 11 \\
\implies y_{3,2}=4 \cdot 0,35 +11 \\
\implies y_{3,2}=1,4+11 \\
\implies y_{3,2}=12,4
\end{align}
$$

$$
\begin{align}
C_{3}=\frac{y_{3,1}+y_{3,2}}{2}=\frac{19,6+12,4}{2}=\frac{32}{2}=16 \\
\implies C_{3}=16
\end{align}
$$

**Calculul $C_{4}$**

$$
\begin{align}
 \frac{13-y_{4,1}}{13-10}=\frac{h_{4}}{1}\implies 13-y_{4,1}=(13-10)h_{4} \\
\implies -y_{4,1}=(13-10) h_{4} -13 \\
\implies -y_{4,1}=3 \cdot 0,35 -13 \\
\implies -y_{4,1}=1,05 -13 \\
-y_{4,1}=-11,95 \\
\implies y_{4,1}=11,95
\end{align}
$$


$$
\begin{align}
\frac{y_{4,2}-0}{6-0}=\frac{h_{4}}{1}\implies y_{4,2}=6\cdot h_{4} \\
\implies y_{4,2}=6 \cdot 0,35 \\
y_{4,2}=2,1
\end{align}
$$


$$
\begin{align}
C_{4}=\frac{y_{4,1}+y_{4,2}}{2}=\frac{11,95+2,1}{2}=\frac{14,05}{2} \\
\implies C_{4}=7,02
\end{align}
$$


**Calculul $\Delta y$**

$$
\Delta y=\frac{C_{1} \cdot h_{1} + C_{2} \cdot h_{2} + C_{3} \cdot h_{3} + C_{4} \cdot h_{4}}{h_{1}+h_{2}+h_{3}+h_{4}}
$$


$$
\Delta y=\frac{20,65 \cdot 0,325 + 20,65 \cdot 0,325+16 \cdot 0,35 + 7,02 \cdot 0,35}{0,325+0,325+0,35+0,35}=\frac{21,4795}{1,35}=15,91
$$

## Bilet 2

Un controler fuzzy are 2 intrări şi o ieşire.

Prima variabilă de intrare este eroarea semnalului ep ( $e_{p}=p_{r}-p_{a}, p_{r}$ este valoarea de referință a intrării 1 iar $p_{a}$ valoarea actuală) şi este definită pe domeniul $(-22,22)$ fiind caracterizată de funcțiile de apartenență:

$$
\begin{align}
\mu_{N B}(u)=L(u,-20,-16),\\ 
\mu_{N M}(u)=\Pi(u,-20,-16,-9,-6),\\ 
\mu_{N S}(u)=\Pi(u,-9,-6,-1,0), \\
\mu_{Z E}(u)=\Lambda(u,-1,0,1),\\
\mu_{P S}(u)=\Pi(u, 0,1,6,9),\\
\mu_{P M}(u)=\Pi(u, 6,9,16,20),\\
\mu_{P B}(u)=\Gamma(u, 16,20)\\
\end{align}
$$


Cea de a doua variabilă de intrare este eroare semnalului es $\left(e_{s}=s_{r}-s_{a}, s_{r}\right.$ este valoarea de referință a intrării 2 iar $\mathrm{s}_{\mathrm{a}}$ valoarea actuală) şi este definită pe domeniul $(-50,56)$ fiind caracterizată de funcțiile de apartenență:

$$
\begin{align}
 \mu_{N B}(u)=L(u,-42,-32),  \\
\mu_{N M}(u)=\Pi(u,-37,-32,-25,-10), \\
 \mu_{N S}(u)=\Pi(u,-18,-15,-10,0), \\
 \mu_{Z E}(u)=\Lambda(u,-6,0,8), \\
\mu_{P S}(u)=\Lambda(u,0,5,18),  \\
\mu_{P M}(u)=\Lambda(u, 14,30,45),  \\
\mu_{P B}(u)=\Gamma(u, 37,50)
\end{align}
$$


Variația semnalul de comandă $\Delta y$ este caracterizată pe domeniul $(-23,23)$ de funcțiile:

$$
\begin{align}
\mu_{N B}(u)=L(u,-21,-17), \\
\mu_{N M}(u)=\Pi(u,-21,-17,-8,-5), \\
\mu_{N S}(u)=\Pi(u,-8,-7,-1,0), \\
\mu_{Z E}(u)=\Lambda (u,-1,0,3), \\
\mu_{P S}(u)=\Pi(u,0,6,10,13),  \\
\mu_{P M}(u)=\Pi(u, 11,15,17,21), \\
 \mu_{P B}(u)=\Gamma(u, 17,21)
\end{align}
$$


Controlerul este caracterizat de urmărtoarea tabelă de inferență:

| $e p \rightarrow$ <br> $e s \downarrow$ | $\mathrm{NB}$ | $\mathrm{NM}$ | $\mathrm{NS}$ | $\mathrm{ZE}$ | $\mathrm{PS}$ | $\mathrm{PM}$ | $\mathrm{PB}$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| $\mathrm{NB}$ | $\mathrm{PB}$ | $\mathrm{PB}$ | $\mathrm{PB}$ | $\mathrm{PB}$ | $\mathrm{PB}$ | $\mathrm{PM}$ | $\mathrm{PM}$ |
| $\mathrm{NM}$ | $\mathrm{PM}$ | $\mathrm{PM}$ | $\mathrm{PM}$ | $\mathrm{PM}$ | $\mathrm{PS}$ | $\mathrm{PS}$ | $\mathrm{PS}$ |
| $\mathrm{NS}$ | $\mathrm{PS}$ | $\mathrm{PS}$ | $\mathrm{PS}$ | $\mathrm{PM}$ | $\mathrm{PS}$ | $\mathrm{PS}$ | $\mathrm{PS}$ |
| $\mathrm{ZE}$ | $\mathrm{ZE}$ | $\mathrm{ZE}$ | $\mathrm{ZE}$ | $\mathrm{ZE}$ | $\mathrm{ZE}$ | $\mathrm{ZE}$ | $\mathrm{ZE}$ |
| $\mathrm{PS}$ | $\mathrm{NS}$ | $\mathrm{NS}$ | $\mathrm{NS}$ | $\mathrm{NS}$ | $\mathrm{NS}$ | $\mathrm{NS}$ | $\mathrm{NS}$ |
| $\mathrm{PM}$ | $\mathrm{NS}$ | $\mathrm{NS}$ | $\mathrm{NS}$ | $\mathrm{NM}$ | $\mathrm{NM}$ | $\mathrm{NM}$ | $\mathrm{NM}$ |
| $\mathrm{PB}$ | $\mathrm{NS}$ | $\mathrm{NS}$ | $\mathrm{NM}$ | $\mathrm{NM}$ | $\mathrm{NM}$ | $\mathrm{NM}$ | $\mathrm{NM}$ |

Ştiind că $\mathrm{p}_{\mathrm{r}}=11, \mathrm{p}_{\mathrm{a}}=3,3$ şi $\mathrm{s}_{\mathrm{r}}=-42,7, \mathrm{~s}_{\mathrm{a}}=-7$, să se calculeze folosind metoda inaltimii si metoda ultimului maxim variatia $\Delta y$ la momentul actual.

---

$$
\begin{cases}
e_{p}=p_{r}-p_{a} = 11-3,3=7,7 \\
e_{s}=s_{r}-s_{a}=-42,7-(-7)=-35,7
\end{cases}
$$


![[Pasted image 20240119200443.png]]

$$
\begin{cases}
 \mu_{N B}(7,7)=0  \\
\mu_{N M}(7,7)=0 \\
 \mu_{N S}(7,7)=0 \\
 \mu_{Z E}(7,7)=0 \\
\mu_{P S}(7,7)=\frac{9-7,7}{9-6}=\frac{1,3}{3}=0,43 \\
\mu_{P M}(7,7)=\frac{7,7-6}{9-6}=\frac{1,7}{3}=0,56  \\
\mu_{P B}(7,7)=0
\end{cases}
$$


![[Pasted image 20240119201023.png]]

$$
\begin{cases}
 \mu_{N B}(7,7)=\frac{-32-(-35,7)}{-32-(-42)}=\frac{3,7}{10}=0,37  \\
\mu_{N M}(7,7)=\frac{-35,7-(-37)}{-32-(-37)}=\frac{1,3}{5}=0,26 \\
 \mu_{N S}(7,7)=0 \\
 \mu_{Z E}(7,7)=0 \\
\mu_{P S}(7,7)=0 \\
\mu_{P M}(7,7)=0  \\
\mu_{P B}(7,7)=0
\end{cases}
$$

Tabel de inferenta

| $e p \rightarrow$ <br> $e s \downarrow$ | $NB$ <br> $0$ | $NM$ <br> $0$ | $NS$ <br> $0$ | $ZE$ <br> $0$ | $PS$ <br> $0,43$ | $PM$ <br> $0.56$ | $PB$ <br> $0$ |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| $NB$ <br> $0,37$ | 0 | 0 | 0 | 0 | $PB$ <br> $0,37$ | $PM$ <br> $0,37$ | 0 |
| $NM$ <br> $0,26$ | 0 | 0 | 0 | 0 | $PS$ <br> $0,26$ | $PS$ <br> $0,26$ | 0 |
| $NS$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| $ZE$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| $PS$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| $PM$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| $PB$ <br> $0$ | 0 | 0 | 0 | 0 | 0 | 0 | 0 |



![[Pasted image 20240119201902.png]]

1. **Metoda primului maxim**
$$
\begin{align}
\frac{p-11}{15-11}=\frac{h_{3}}{1}\implies p_{pm}=(15-11)\cdot h_{3} + 11 \\
\implies p=4 \cdot 0,37+11=12,48
\end{align}
$$

2. **Metoda ultimului maxim**
$$
p_{um}=23
$$
3. **Metoda mijlocului maximelor**

$$
p_{mm}=\frac{12,48+23}{2}=\frac{35,48}{2}=17,74
$$
4. **Metoda inaltimii**
$$
\Delta y=\frac{\sum_{k=1}^{4}ck \cdot hk}{\sum_{k=1}^{4}hk} \quad(\text{formula centrului de greutate})
$$

$$
\begin{cases}  
h_{1}=h_{2}=0,26\\
h_{3}=h_{4}=0,37
\end{cases}
$$
**Calculul $C_{1}$**

$$
\begin{align}
\frac{y_{1,2}-17}{21-17}=\frac{h_{1}}{1} \implies 13- y_{1,2}=(13-10)h_{1} \\
\implies 13-y_{1,2}=3 \cdot h_{1} \\
\implies y_{1,2}-3 \cdot 0,26 +13 \\
\implies y_{1,2}=-0,78 +13  \\
\implies y_{1,2}=12,22
\end{align}
$$

$$
\begin{align}
C_{1}=\frac{1,56+12,22}{2}=\frac{13,78}{2}=6,89 \\
\implies C_{1}=6,89
\end{align}
$$
**Calculul $C_{2}$**

$$
y_{2,1}=y_{1,1}\implies y_{2,1}=1,56
$$

$$
y_{2,2}=y_{1,2}\implies y_{2,2}=12,22
$$

$$
C_{2}=C_{1} \implies C_{2}=6,89
$$

**Calculul $C_{3}$**

$$
\begin{align}
\frac{y_{1,3}-11}{15-11}=\frac{h_{3}}{1}\implies y_{1,3}-11=(15-11) \cdot h_{3} \\
\implies y_{1,3}=(15-11) \cdot h_{3} + 11 \\
\implies y_{1,3}= 4 \cdot 0,37 +11 \\
\implies y_{1,3}=1,48+11 \\
y_{1,3}=12,48
\end{align}
$$

$$
\begin{align}
\frac{21-y_{2,3}}{21-17}=\frac{h_{3}}{1}\implies 21-y_{2,3}=(21-17) h_{3} \\
\implies -y_{2,3}=(21-17) h_{3} -21 \\
\implies -y_{2,3}=4 \cdot 0,37 -21 \\
\implies -y_{2,3}=1,48-21 \\
\implies -y_{2,3}=-19,52 \\
\implies y_{2,3}=19,52
\end{align}
$$

$$
\begin{align}
\implies C_{3}=\frac{y_{1,3}+y_{2,3}}{2}=\frac{12,48+19,52}{2}=\frac{32}{2}=16 \\
\implies C_{3}=16
\end{align}
$$


**Calculul $C_{4}$**

$$
\begin{align}
\frac{y_{4,1}-17}{21-17}=\frac{h_{4}}{1}\implies y_{1,4}-17=(21-17) \cdot h_{4} \\
\implies y_{1,4}=(21-17) \cdot h_{4} + 17 \\
\implies y_{1,4}=4 \cdot 0,37+17 \\
\implies y_{1,4}=1,48+17 \\
\implies y_{1,4}=18,48
\end{align}
$$
$$
y_{2,4}=23
$$

$$
C_{4}=\frac{y_{1,4}+y_{2,4}}{2}=\frac{18,48+23}{2}=\frac{41,48}{2}=20,74
$$

**Calculul $\Delta y$**

$$
\Delta y=\frac{C_{1} \cdot h_{1} + C_{2} \cdot h_{2} + C_{3} \cdot h_{3} + C_{4} \cdot h_{4}}{h_{1}+h_{2}+h_{3}+h_{4}}
$$

$$
\begin{align}
\Delta y=\frac{6,89 \cdot 0,26+ 6,89 \cdot 0,26+ 16 \cdot 0,37+20,74 \cdot 0,37}{0,26+0,26+0,37+0,37}=\frac{17,1766}{1,26} \\
\implies \Delta y =13,63
\end{align}
$$
