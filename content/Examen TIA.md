---
tags:
  - TehniciDeInteligentaArtificiala
title: Examen TIA
---
# Problema
![[Bilete examen TIA]]
Fuzzy - controller cu datele de intrare date (2 intrari si o iesire).
Calculati valoarea de iesire folosind o anumita metoda de defuzificare (4 metode).

8:30- V47 discutie subiecte

# Teorie

## Modelul neuronului artificial
### Schema
![[Retele neuronale 1.light.svg|Modelul de baza a unei unitati functionale]]

### Notatii specifice
- $x_{1},\dots,x_{n}$ - semnalele de intrare ale neuronului unificat
- $w_{1},\dots,w_{n}$ - ponderile asociate celor $n$ [[semnale]] de intrare
- $p$ - valoarea de prag
- $s$ - activarea totala a neuronului
- $f(s)$ - functia neuronala (descrie calculul simplu realizat de o unitate functionala din retea)

### Calculul realizat
Calculul realizat de neuronul artificial este descris de relatia:
$$
\begin{cases}
s=\sum_{i=1}^{N}x_{i} w_{i}-P \\
y=f(s)
\end{cases}
$$
>[!info]
>Relatia anterioara se numeste si **modelul neuronal de baza**


## Tipuri de functii neuronale

1. **Functia de activare neliniara cu prag asimetric**
$$
f(x)= \begin{cases}
1, \quad \text{pentru }x \geq 0 \\
0, \quad \text{pentru }x < 0
\end{cases}
$$
2. **Functia de activare neliniara cu prag simetric (signum)**
$$
f(x)=\begin{cases}
1, \quad \text{pentru }x \geq 0 \\
-1, \quad \text{pentru }x < 0
\end{cases}
$$
3. **Functia de activare liniara**
$$
f(x)=x
$$
4. **Functia de activare liniara cu limitare asimetrica**
$$
f(x)=\begin{cases}
0, \quad \text{pentru }x \leq 0 \\
x, \quad \text{pentru }x \in (0,1] \\
1, \quad \text{pentru }x > 0
\end{cases}
$$
5. **Functia de activare liniara cu limitare simetrica**
$$
f(x)=\begin{cases}
-1, \quad \text{pentru }x \leq -1 \\
x, \quad \text{pentru }x \in [-1,1] \\
1, \quad \text{pentru }x > 1
\end{cases}
$$
6. **Functia de activare sigmoidala**
$$
f(x)=\frac{1}{1+e^{-kx}} \text{ cu }k>0
$$
7. **Functia de activare tangenta hiperbolica**
$$
f(x)=\frac{e^{kx}-e^{-kx}}{e^{kx}+e^{-kx}} \text{ cu }k>0
$$
## Instruirea retelelor neuronale

Antrenarea unei retele neuronale consta in iterarea valorilor ponderilor din retea pe baza unor date de antrenare si conform unui algoritm de antrenare.

In functie de continutul datelor de antrenare exista 2 tipuri de algoritmi: **antrenare supervizata** si **antrenare nesupervizata**.
![[Retele neuronale#Algoritmi cu antrenare supervizata]]

![[Retele neuronale#Algoritmi cu antrenare nesupervizata]]


## Perceptronul
### Modelul detaliat

![[Curs 5 TIA 3.excalidraw.light.svg]]
unde:
- $x_{1},\dots,x_{n}$ - semnalele de intrare ale neuronului unificat
- $w_{1},\dots,w_{n}$ - ponderile asociate celor $n$ [[semnale]] de intrare
- $p$ - valoarea de prag / prag de excitatie
- $s$ - activarea totala a neuronului
- $f(s)$ - functia neuronala (descrie calculul simplu realizat de o unitate functionala din retea)
- $y$ - marimea de iesire

### Functia neuronala specifica
$$
f(s)=\begin{cases}
0, \quad s \leq 0\\ \\
1, \quad s > 0
\end{cases}
$$

## Probleme de clasificare
1. Un perceptron simplu poate avea 2 valori ale semnalului de iesire, $y \in \{0,1\}$ sau $y \in \{-1,1\}$. Astfel clasificarea datelor de intrare este:
	- Clasa A: $y=0$
	- Clasa B: $y=1$

2. Pentru o retea cu $m$ semnale de iesire, se poate face o clasificare liniara a datelor de intrare in $2^{m}$ clase
3. Pentru a putea face o clasare liniara, trebuie indeplinita **conditia de liniar-separabilitate**: daca se poate trasa o dreapta care sa separe punctele conform claselor predefinite, atunci multimea exemplelor de antrenare respecta conditia de liniar-separabilitate
## Reteaua liniara

![[Retele neuronale 1.light.svg|Modelul de baza a unei unitati functionale]]
- $x_{1},\dots,x_{n}$ - semnalele de intrare ale neuronului unificat
- $w_{1},\dots,w_{n}$ - ponderile asociate celor $n$ [[semnale]] de intrare
- $p$ - valoarea de prag
- $s$ - activarea totala a neuronului
- $f(s)$ - functia neuronala (descrie calculul simplu realizat de o unitate functionala din retea)

- Functia neuronala specifica:
	- liniara: $f(s)=s$ (identitate)
	![[Pasted image 20240120203919.png]]
	- liniara pe domeniu: $f(s)=\begin{cases} -1, \quad s<-1 \\ s, \quad -1 \leq s \leq 1 \\ 1, \quad s>1\end{cases}$
	![[Curs TIA 6 1.excalidraw.light.svg]]


## Probleme de aproximare liniara

Fie $P$ perechi de valori $(x^{k},d^{k})$
- $x^{k}$ - vectorul care contine valorile intrarilor din perechea de date de antrenare cu indicele $k$
- $d^{k}$ - vetorul valorilor impuse iesirilor daca la intrari avem $x^{k}$
- $k$ - indicele iteratiei curente

Problema aproximarii liniare se refera la determinarea unei functii liniare $f:P^{n}\to P^{m}, f(x)=wx$ care sa aproximeze cat mai bine relatia dintre $x^{k}$ si $d^{k}$ pentru toate cele $P$ perechi

![[Pasted image 20240120204244.png]]

O serie de valori este un set de valori $x_{k},k=\overline{1,L}$ asociat unei marimi ce evolueaza in timp, $x(t)$. Cunoscand ultimele $n$ valori ale seriei, inregistrate la momentele anterioare, se doreste estimarea valorii $x(t)$ in momentul curent $t$. Deci, exista o dependenta liniara intre valorile seriei, adica 
$$
x(t)=w_{1}x(t-1)+\dots+w_{n}x(t-n)+b
$$

Atunci, o retea liniara va permite estimarea coeficientilor $w_{i}$ si $b$, precum si valorile prezise a semnalului $x(t)$

![[Pasted image 20240120204532.png]]
## Arhitectura multistrat unidirectionala
Aplicatiile de retele neuronale se bazeaza pe structuri alcatuite din mai multe unitati functionale organizate in diverse configuratii. Una din aceste configuratii o reprezinta reteaua unidirectionala in care straturile de neuroni sunt clar definite pornind de la intrarile retelei. 

![[Pasted image 20240120211404.png]]

unde:
- $x_{1},x_{2},\dots,x_{N}$ - semnale de intrare
- $y_{1},y_{2},\dots,y_{M}$ - semnale de iesire

Delimitarea straturilor de neuroni este stricta, adica:
- Nu avem bucle in retea
- Nu exista conexiuni intre neuronii de pe acelasi strat 
- Nu avem conexiuni care sar peste straturi

Semnalele parcurg reteaua doar intr-un singur sens, de la intrari la iesiri.



## Metoda propagarii inapoi a erorii

![[Retele multistrat unidirectionale. Metoda propagarii inapoi a erorii 1.light.svg]]
Avand valori impuse pentru semnalele de iesire, se pot calcula erori de antrenare pentru neuronii stratului de iesire. Pentru neuronii celorlalte straturi (straturi ascunse – pentru o retea cu 2 straturi, nu avem) nu avem informatii despre valoarea semnalelor de iesire. 

Eroarea de antrenare a unui neuron de pe stratul ascuns trebuie sa depinda de erorile neuronilor de pe stratul de iesire si de ponderile dintre straturi. Pentru aceasta, se utilizeaza **eroarea dinamica de antrenare**, calculate in sensul invers de parcurgere a retelei.


## Sisteme neuro-fuzzy / ANFIS

![[Sisteme neuro-fuzzy. Sistemul ANFIS 1.light.svg]]

**ANFIS** = Adaptive Neural Fuzzy Inference System (SisteSisteme neuro-fuzzy / ANFISm de Inferenta Neuro-Fuzzy Adaptiv)

Un sistem *ANFIS* reprezinta un algoritm de inferenta fuzzy de tip [[Sisteme neuro-fuzzy. Sistemul ANFIS#^0b49bf|Sugeno-Takagi]] pentru care parametrii functiilor de apartenenta se ajusteaza printr-un algoritm de antrenare asemnanator celor de la retelele neuronale.  Antrenarea *ANFIS* este supervizata, asadar avem date de intrare si valori impuse semnalelor de iesire. 

- $e,d$ - variabile de intrare
- $u$ - variabile de iesire
- $\cap$ - intersectie
- $N$ - normalizare
- $w_{1}$ - intensitatea de activare
- $\overline{w_{1}}$ - intensitatea de activare normalizata
- $\mu_{A_{1,2},B_{1,2}}$ - valorile functiilor de apartenenta
- $f_{1}(e,d), f_{2}(e,d)$ - functii de apartenenta


Arhitectura cuprinde 5 straturi corespunzatoare celor 5 straturi de calcul, implicit 5 pasi:
1. Fuzzyficarea datelor de intrare
2. Multiplicarea semnalelor de intrare
3. Impartirea fiecarui semnal de intrare la suma totală a intrărilor.
4. Defuzzyficarea
5. Producerea iesirii sistemului prin intermediul neuronului sumator