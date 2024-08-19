---
tags:
  - TeoriaSistemelor
---

In principiu, grafurile de fluenta sau de semnal constituie o metoda grafica de reprezentare a unui sistem de ecuatii algebrice.

Pentru aplicarea metodei grafurilor de fluenta in analiza sistemelor de control este necesar, ca in prima etapa, sa transformam [[Ecuatii diferentiale|ecuatiile diferentiale]] in ecuatii algebrice de variabila $s$.
## Elemente de baza ale grafurilor de fluenta
Elementele grafice de baza ale grafurilor de fluenta sunt **nodurile si ramurile**.

**Nodul** reprezinta o variabila sau un semnal al sistemului.

**Ramura** este un segment orientat de linie (dreapta sau curba) care conecteaza doua noduri, actionand ca un amplificator de semnal. Directia de transmitere a semnalului este precizata cu o sageata plasata, de regula, in mijlocul ramurii, iar valoarea factorului de amplificare numit, de obicei, transmitanta este scrisa in zona sagetii.
## Semnale
In schemele cu grafuri care reprezinta sisteme dinamice, transmitantele sunt [[Functii de transfer#Definitie|functii de transfer]].

Semnalele furnizate de ramurile care intra intr-un nod (ramuri incidente) sunt insumate si transmise tuturor ramurilor care pleaca din nod (ramuri divergente).
## Tipuri de noduri
In schemele cu grafuri de fluenta exista 3 tipuri de noduri:
- Nod de intrare (sursa)
- Nod de iesire (receptor)
- Nod mixt

Nodul sursa este asociat unei variabile independente si are numai ramuri divergente. Nodul de iesire are numai ramuri incidente si este asociat unei variabile dependente. 

Un nod mixt are atat ramuri incidente cat si ramuri divergente.
## Calea directa
Calea directa ete traseul format din ramuri cu aceeasi directie care conecteaza un nod de intrare cu un nod de iesire, intersectand (numai) o singura data toate nodurile.

![[Pasted image 20221109121224.png]]
## Bucla
**Bucla** este un traseu format din ramuri cu aceeasi directie de parcurgere, care incepe si se termina in acelasi nod, intersectand (numai) o singura data toate celelalte noduri.
### Proprietatea de adiacenta
O notiune importanta utilizata in cadrul metodei grafurilor de fluenta este **adiacenta**. Doua bucle sunt adiacente daca ele au cel putin un nod comun. Similar o bucla este adiacenta unei cai directe, daca acestea (bucla si calea directa) au cel putin un nod comun.
## Reducerea la graf echivalent
Pentru a determina relatia dintre semnalele unui nod de iesire si a unui nod de intrare se poate utiliza **formula lui Manson**, care se va prezenta ulterior, sau se poate reduce graful de fluenta la un graf echivalent care contine numai nodurile de intrare si iesire. 

In acest scop se vor folosi urmatoarele reguli:
1. Valoarea semnalului dintr-un nod de iesire cu o singura ramura incidenta este $y=Tu$
	![[Pasted image 20221109121851.png]]
2. Transmitanta totala a ramurilor conectate in serie este egala cu produsul transmitantelor tuturor ramurilor. Ramurile conectate in serie pot fi combinate intr-o singura ramura prin multiplicarea transmitantelor
	
	![[Pasted image 20221109121913.png]]
3. Ramurile paralele se combina prin adunarea transmitantelor
	$$y=abu$$
	$$T_e=ab$$
	![[Pasted image 20221109121932.png]]

4. Eliminarea unui nod
	$$y=acu_1+bcu_2$$
	![[Pasted image 20221109122018.png]]
5. Eliminarea unei bucle
	![[Pasted image 20221109122307.png]]

Transmitanta totala a unei cai directe $T_{cd}$, sau a unei bucle $T_b$, este egala cu produsul transmitantelor tuturor ramurilor care apartin acestora.

## Modelarea sistemelor de reglare cu grafuri de fluenta
Schemele cu grafuri de fluenta ale sistemelor de reglare se deseneaza pornind, de regula, de la schemele bloc sau de la sistemul de ecuatii algebrice de variabila $s$ care modeleaza comportarea dinamica a acestora.

In acest scop sunt utile cateva reguli simple:
- Semnalele de intrare si de iesire, punctele de ramificacre si sumare se reprezinta in graful de fluenta prin noduri
- Blocurile sunt reprezentate in graf prin intermeiul ramurilor cu transmitanta egala cu functia de transfer
- Punctul de sumare din schemele bloc se reprezinta in graful de fluenta ca un nod, care constituie semnalul de iesire din sumator
- Un semnal de intrare conectat direct la un punct de sumare este reprezentat intr-un graf prin doua noduri si o ramura cu transmitia unitata conectata intre nodul corespunzator semnalul de intrare si nodul care reprezinta semnalul de iesire al sumatorului
![[Pasted image 20221109122922.png]]
## Formula lui Mason
$$G_e(s)=\frac{Y(s)}{R(s)}=\frac{1}{\Delta(s)}\sum_nG_{cdn}(s)\Delta_n(s)$$
unde $G_{cdn}(s)$ reprezinta functia de transfer a caii directe cu numarul de ordine $n$, $\Delta (s)$ este determinantul grafului =1 (suma funcţiilor de transfer ale tuturor buclelor individuale din graf) + (suma produselor funcţiilor de transfer pentru toate combinaţiile posibile de două bucle neadiacente) – (suma produselor funcţiilor de transfer pentru toate combinaţiile posibile de trei bucle neadiacente) + ...
$$
\Delta(s)=1-\sum_i G_{\mathrm{b} i}(s)+\sum_{i, j} G_{\mathrm{b} i}(s) G_{\mathrm{b} j}(s)-\sum_{i, j, k} G_{\mathrm{b} i}(s) G_{\mathrm{b} j}(s) G_{\mathrm{b} k}(s)+\ldots
$$
$\Delta_n(s)$ este cofactorul căii directe $n$, care se calculează eliminând din determinantul grafului buclele adiacente căii respective ( $\Delta_n$ se obţine din $\Delta$ considerând $G_{\mathrm{b}}=0$ pentru buclele adiacente căii directe $n$ ).

În relaţiile de mai sus funcția de transfer a unei căi directe, $G_{\text {od }}(s)$, sau a unei bucle, $G_{\mathrm{b}}(s)$, este egală cu produsul funcţilor de transfer ale tuturor ramurilor care aparţin acestora.