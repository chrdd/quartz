---
title: Examen SAE
draft: false
tags:
  - SAE
---
 
## Bilete
### Bilet 2023
#### Exercitiul 1

Fie sistemul din figura ($T_{e}=0.1s$), unde $G(s)=\frac{1}{s(s+3)}$

![[Pasted image 20240618144616.png]]

1. Sa se determine functia de transfer a sistemului in circuit folosind [[Calculul analitic aproximativ al funcţiilor de transfer z#Calculul analitic aproximativ bazat pe substituţii algebrice de tipul $s=f(z)$|metoda de integrare a trapezului]]
2. Sa se determine pentru ce marime de intrare sistemul prezinta [[Analiza erorilor stationare la sisteme liniare discrete#Marimea de eroare|eroare stationara]] finita
3. Sa se determine si sa se reprezinte grafic [[Analiza raspunsului in timp al sistemelor discrete#Raspunsul la treapta unitara| raspunsul sistemului la marimea de intrare treapta unitara]]



#### Exercitiul 2

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de forma ($T_{e}=1s$):

$$G_{d}(z)=\frac{0.2z+0.07}{z^{2}-0.5z+0.05}$$

Sa se reprezinte caracteristicile amplitudine-pulsatie si faza-pulsatie

#### Exercitiul 3

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):

$$G_{d}(z)=\frac{k(0.13z+0.02)}{z^{2}-0.39z+0.007}$$

Determinati:

1. Numarul de ramuri ale [[Analiza sistemelor discrete cu metoda locului radacinilor|locului radacinilor]]; de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care il fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc. Trasati locul radacinilor

#### Exercitiul 4

Se considera functia de transfer a unui sistem in circuit inchis:

$$G_{0}(z)=\frac{z^{2}-1.39z+0.52}{z^{2}-1.43z+0.49}$$

1. Sa se determine modelul cu variabile de stare in forma [[Modele ale sistemelor discrete cu variabile de stare#Realizarea complet observabila|complet observabila]] (demonstratie)
2. Plecand de la modelul cu variabile de stare sa re realizeze schema bloc
### Bilet 1
#### Exercitiul 1

Se considera un sistem discret cu reactie negativa unitara in care partea continua are urmatoarea forma:

$$G_{PC}(s)=\frac{k}{s+5}$$

1. Pentru $k=0.1$, sa se determine functia de transfer a sistemului in circuit inchis plecand de la ecuatia cu diferente
2. Folosind graful de fluenta sa se determine functia de trensfer a sistemului in circuit inchis
3. Sa se determine pentru ce tip de intrare sistemul prezinta eroare stationara finita
4. Sa se determine raspunsul sistemului la marimea de intrare treapta unitara si sa se reprezinte grafic

---
**Rezolvare:**
1. 
$$\begin{align}& k=0.1 \implies G_{PC}(s)=\frac{0.1}{s+5}=\frac{Y(s)}{U(s)} \\&\implies U(s)= 10s\cdot Y(s) +50 Y(s) \bigg{|}\mathcal{L}^{-1} \\& \implies 10 \cdot \frac{dY(t)}{dt}+50 Y(t)=U(t) \\& \implies 10 \frac{ Y[k] - Y[k-1]}{T_{e}}+ 50 Y[k] = U[k] \\&\implies 10 (Y[k]-Y[k-1])+50 T_{e} \cdot Y[k]=T_{e} \cdot U[k] \\& \implies 10 Y[k](10+50T_{e}) - 10Y[k-1] = T_{e} \cdot U[k] \Big{|}Z \\&\implies 10 Y(z) (10+50T_{e})-10Z^{-1}Y(z)=T_{e}U(z) \\&\implies \frac{Y(z)}{U(z)}=\frac{T_{e}}{1+5T_{e}-z^{-1}}=\frac{zT_{e}}{z+5T_{e}z-1} \\& G_{0}(z)=\frac{G_{PC}(z)}{1+G_{PC}(z)}=\frac{\frac{zT_{e}}{z+5T_{e}z-1}}{1+\frac{zT_{e}}{z+5T_{e}z-1}}=\frac{zTe}{z(1+5T_{e})-1}\end{align}$$

	```mermaid

	graph LR

		R((R)) -->|1| E1((E=X1))

		E1 --> X1((/))

		X1 --> E2((E*=X2))

		E2 -->|ERO.Gpc| Y((Y=X3))

		Y -.->|−1| E1

	```

$$\begin{align}& \begin{cases} x_{1}=E=R-Y=R-x_{3} \\x_{2} = E^{*}= x_{1}^{*} \\  x_{3} = y = ERO \cdot G \cdot x_{2}=ERO \cdot G \cdot x_{1}^{*} \end{cases} \\ &\begin{cases} x_{1}=R-ERO \cdot G \cdot x_{1}^{*} \\ x_{2}=x_{1}^{*} \\ x_{3}=ERO \cdot G \cdot x_{1}^{*}\end{cases} \\ & \begin{cases} x_{1}^{*} =R^{*}-(ERO \cdot G)^{*} \cdot x_{1}^{*} \\ x_{2}^{*}=x_{1}^{*} \\ x_{3} = (ERO \cdot G)^{*} \cdot x_{1}^{*} \end{cases} \end{align}$$

 
	```mermaid
	graph LR
    R["R*"] -->|1| X1["X1*"]
    X1 -->|1| X2["X2*"]
    X2 -->|"(ERO G)"*| X3[" X3* = Y"]
    X1 -->|"-(ERO G)"*| X1
	```
2. 
$$\begin{align}& G_{d}(z)=\frac{0.2}{z-0.006} \\& e_{st}^{*} = \lim_{ z \to 1 }(1-z^{-1})\cdot E(z)=\lim_{ z \to 1 } \frac{z-1}{z} \cdot \frac{R(z)}{1+G_{0}(z)} \\& R(z)=\frac{z}{z-1}\implies e_{st}^{*'}=\lim_{ z \to 1 } \frac{\cancel{z-1}}{\cancel{z}} \cdot \frac{\cancel{z}}{\cancel{z-1}} \cdot \frac{1}{1+ \frac{0.2}{z-0.006}} \\&= \frac{1}{1+0.2} = \frac{1}{1.2}=0.83 = \text{eroarea stationara pentru intrarea treapta}   \end{align}$$
3. 
$$\begin{align}& y(kT_{e})=? \\& y(kT_{e})=Z^{-1} \{Y(z)\}=Z^{-1}\{R(z) \cdot G_{0}(z)\} \\& Y(z)=\frac{z}{z-1} \cdot \frac{0.2}{z+0.19}=\frac{0.2z}{z^{2}+0.19z-z-0.19} \\&= \frac{0.2z}{z^{2}-0.8z-0.19}|\cdot z^{-2}\implies Y(z^{-1})= \frac{0.2z^{-1}}{1-0.8z^{-1}-0.19z^{-2}}\end{align}$$

#### Exercitiul 2

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):

$$G_{d}(z)=\frac{0.56z+0.29}{z^{2}-1.13z+0.13}$$

Sa se determine :

1. Partea reala si partea imaginara
2. Punctul de unde pleaca [[Curba polara|curba polara]] si punctul unde se termina curba polara
3. Cum este sistemul in circuit deschis (argumentati)
4. Cum este sistemul in circuit inchis (argumentati)

---
**Rezolvare:**
1. 
$$\begin{align} & z= \frac{1+ \frac{T_{e}}{2}\omega}{1- \frac{T_{e}}{2}\omega}=\frac{1+0.5\omega}{1-0.5\omega} \\ & \implies G_{d}(z)= \frac{0.56\left( \frac{1+0.5\omega}{1-0.5\omega} \right)+0.29}{\left( \frac{1+0.5\omega}{1-0.5\omega} \right)^{2}-1.13\left( \frac{1+0.5\omega}{1-0.5\omega} \right)+0.13} \\ & = \frac{0.56(1+0.5\omega)+0.29(1-0.5\omega)}{(1+0.5\omega)^{2}-1.13 (1^{2}-0.5^{2}\omega^{2})+0.13(1-0.5\omega)^{2}}\cdot (1-0.5\omega) \\ & \frac{0.56+0.28\omega+0.29-0.14\omega}{\cancel{1}+\omega+0.25\omega^{2}\cancel{-1.13}+0.03\omega^{2}\cancel{+0.13}-0.13\omega+0.03\omega^{2}}\cdot (1-0.5\omega) \\ &= \frac{0.86+0.42\omega}{0.3\omega^{2}+0.8\omega}(1-0.5\omega ) = \frac{0.86-\cancel{0.42\omega}+ \cancel{0.42\omega}-0.2\omega^{2}}{0.3\omega^{2}+0.8\omega} \\ & = \frac{-0.2\omega^{2}+0.86}{0.3\omega^{2}+0.8\omega} = \frac{\cancel{0.86}(1-0.23\omega^{2})}{\cancel{0.8}\omega(1+0.37\omega)} \\ &\begin{cases} \alpha=1 \\ n=2 \\ m=2 \end{cases} \implies n-m=0 \\ &\omega \to j\omega \implies G_{d}(j\omega)=\frac{1+0.23\omega}{j \omega (1+0.37 j\omega)} \\ & G_{d}(j\omega) = \frac{(1+0.23\omega)(1-0.37 j \omega)}{\omega^{2}(1+0.37^{2}\omega^{2})}= \frac{1-0.37 j \omega + 0.23 j\omega + 0.08 \omega^{2}}{\omega^{2}(1+0.37^{2}\omega^{2})} \\ & \implies \begin{cases} Re\{G_{d}(j\omega)\}=\frac{0.08\omega^{2}+1}{\omega^{2}(1+0.37^{2}\omega^{2})} \\ Im\{G_{d}(j\omega) \}=\frac{-0.14\omega}{\omega^{2}(1+0.37^{2}\omega^{2})} \end{cases} \end{align}$$
2. 
$$\begin{align} &Im\{G(j\omega)\}=0 \implies 0.14\omega=0 \implies \omega=0 \\ & Re\{G(j\omega)\}=1 \\  \\ & \lim_{ \omega \to \infty } Re\{G(j\omega)\}=0 \text{ - curba polara se termina in 0} \\ & \lim_{ \omega \to \infty } Im\{G(j\omega)\} =0   \end{align}$$
	![[Pasted image 20240618194727.png]]
3. Sistemul in circuit deschis este stabil - curba polara nu inconjoara punctul $-1+j_{0}$
4. Sistemul in circuit inchis este stabil



#### Exercitiul 3

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):

$$G_{d}(z)= \frac{0.57z+0.29}{z^{2}-1.13z+0.13}$$

Determinati:

1. Numarul de ramuri ale [[Analiza sistemelor discrete cu metoda locului radacinilor|locului radacinilor]]; de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care il fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc

---
**Rezolvare:**
1. 
$$\begin{align} & n=2 \to \text{ramuri ale locului radacinilor} \\ & m=1 , n-m=1 \implies \text{ramura la infinit } \end{align}$$

2. $$\begin{align} & -z_{1} = -0.5 \\ & -p_{1}=1 \\& -p_{2} = 0.13 \\ & (-\infty, -z_{1}] \cup [-p_{2},-p_{1}] \\ & \implies (-\infty,0.5] \cup [0.13,1] \end{align}$$
	![[Pasted image 20240618195701.png]]
3. 
$$\begin{align}& n-m=1 \implies \text{o asimptota} \\& \varphi_{k}= \frac{\pm 180 \degree(2k+1)}{n-m};k=0.1 \\& k=0 \implies \varphi_{0}=\pm 180\degree \\& \implies \text{nu exista pentru unde se intalnesc}\end{align}$$
4. 
$$\begin{align} & 1+G(z)=0 \implies 1+ \frac{k(0.57z+0.29)}{z^{2}-1.13z+0.13}=0 \\ & \implies k= \frac{-(z^{2}-1.13z+0.13)}{0.57z+0.29} \\ &  \frac{dk}{dz}=0  \\ &\implies \frac{-(2z-1.13)(0.57z+0.29)-(z^{2}-1.13z+0.13)}{(z \cdot 0.57+0.29)^{2}} \\ & \implies -1.14z^{2}+0.6z+0.64z+0.32-z^{2}+1.13z-0.13=0 \\ & \implies -2.14z^{2} + 2.37z+0.2=0 \\ & \implies 2,14z^{2}-2.37z-0.2=0 \\ &\implies \begin{cases} z_{1}=-0.85 \\ z_{2}=0..35 \end{cases} \text{ intre} \implies \text{2 puncte de ramificare} \end{align}$$
5. 
$$\begin{align}&G(z)=\frac{0.57z+0.29}{z^{2}-1.13z+0.13} \\& \implies G(x+jy)=\frac{0.57(x+jy)+0.29}{(x+jy)^{2}-1.13(x+jy)+0.13} \\& \implies \frac{0.57x+0.29+0.57jy}{x^{2}-y^{2}+2xyj-1.13x-1.13jy+0.13}\bigg{|}\mathcal{L} \\&\angle G(x+jy) = (2k+1) 180 \degree \\&\angle G(x+jy) =\arctan \left(\frac{0.57y}{0.57x+0.29}\right)-\arctan\left( \frac{2xy-1.13y}{x^{2}-y^{2}-1.13x+0.13} \right)|\tan \\& \frac{a-b}{1+ab}=0 \implies a=b \implies \frac{0.57 \cancel{y}}{0.57x+0.29}= \frac{2x \cancel{y}-1.13 \cancel{y}}{x^{2}-y^{2}-1.13x+0.13} \\& \implies 0.57x^{2}-0.57y^{2}-\cancel{0.64x}+0.07=1.14x^{2}-\cancel{0.64x}+0.6x-0.32 \\& \implies 0.57x^{2}+0.57y^{2}+0.6x = 0.4 \\&\implies 0.57x^{2}+0.6x + 0.52^{2}+0.57y^{2}=0.4+0.52^{2} \\& \implies (x+0.52)^{2}+0.57y^{2}=0.7 \implies C(0.52;0) \\& 2ab=0.6 \implies b= \frac{0.6}{2\cdot0.57} =\frac{0.6}{1.14}=0.52 \\&R=0.83\end{align}$$


#### Exercitiul 4

Se considera functia de transfer a unui sistem in circuit inchis:

$$G_{0}(z)=\frac{0.02z}{z^{2}-1.49z+0.54}$$

1. Sa se determine modelul cu variabile de stare in forma complet controlabila
2. Plecand de la modelul cu variabile de stare (matricele sistemului) sa se determine daca sistemul este controlabil

---

**Rezolvare:**

1. 
$$\begin{align} & G_{0}(z)=\frac{0.02z}{z^{2}-1.49z+0.54}=\frac{Y(z)}{R(z)}=\frac{Y(z)}{X(z)} \cdot \frac{X(z)}{R(z)} \\ \\ & \frac{X(z)}{R(z)}=\frac{1}{z^{2}-1.49z+0.54} \\ & \implies \frac{Y(z)}{X(z)}=0.02z \\ &\implies z^{2}X(z) -1.49zX(z)+0.54X(z)=R(z) \Big{|} Z^{-1} \\ & \implies x[k+2]-1.49x[k+1]+0.54x[k]=r[k] \\ & \begin{cases} x[k]=x_{1}[k] \\ x[k+1]=x_{2}[k]=x_{1}[k+1] \\ x[k+2]=x_{3}[k]=-0.54 x_{1}[k]+1.49 x_{2}[k]+r[k] \end{cases} \\ &\implies \varnothing = \begin{bmatrix} 0 & 1  \\ -0.54 & 1.49 \end{bmatrix}, \tau=\begin{bmatrix} 0 \\ 1 \end{bmatrix} \\ & \frac{Y(z)}{X(z)}= 0.02z \implies 0.02z X(z)=Y(z)\Big{|} Z^{-1} \\ & \implies y[k]=0.02x[k+1] \\ & \implies y[k]=0.02x_{2}[k] \\ & \implies C= \begin{bmatrix} 0 & 0.02 \end{bmatrix},D=0  \end{align}$$
2.
$$\begin{align} & C(sJ- \varnothing)\cdot \tau \\ & sJ- \varnothing = \begin{bmatrix} s & 0 \\ 0 & s \end{bmatrix} - \begin{bmatrix} 0 & 1 \\ -0.54 & 1.49 \end{bmatrix} = \begin{bmatrix} s & -1 \\ 0.54 & s+1.49 \end{bmatrix} \\ & \implies \begin{bmatrix} 0 & 0.02 \end{bmatrix} \cdot \begin{bmatrix} s & -1 \\ 0.54 & s+1.49 \end{bmatrix} \cdot \begin{bmatrix} 0  \\ 1 \end{bmatrix} \\ & = \begin{bmatrix} 0.02 \cdot 0.54  &  0.02s+0.02 \cdot 0.49 \end{bmatrix} \cdot \begin{bmatrix} 0 \\ 1 \end{bmatrix} \\ & = \begin{bmatrix} 0  & 0.02s+0.02 \cdot 0.49 \end{bmatrix} \\ &= \begin{bmatrix}  0  & 0.02s+0.009 \end{bmatrix}  \end{align}$$

### Bilet 2
#### Exercitiul 1

Se considera un sistem discret cu reactie negativa unitara in care partea continua are urmatoarea forma:

$$G_{PC}(s)=\frac{k}{s+5}$$

1. Pentru $k=1$ si $T_{e}=0.1$ sa se determine functia de transfer a sistemului in circuit inchis plecand de la ecuatia cu diferente
2. Folosind graful de fluenta sa se determine functia de transfer a sistemului in circuit inchis (fara a se calcula numeric)
3. Sa se determine raspunsul sistemului la marimea de intrare treapta unitara si sa se reprezinte grafic (se va folosi functia de transfer determinata la punctul a)
4. Sa se determine valoarea de regim stationar $y_{st}[k]$


#### Exercitiul 2

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma:

$$G_{d}(z)=\frac{0.32}{z-0.05}$$

Determinati:

1. Functia de transfer (forma Bode) in domeniul frecventa
2. Factorul de amplificare si tipul sistemului
3. Pulsatiile de frangere
4. Ce panta/pante are caracteristica amplitudine-pulsatie intre $10^{-1}$ si $10^{1}$ (argumentati)


#### Exercitiul 3

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma:

$$G_{d}(z)=\frac{0.68zk}{z^{2}-1.05z+0.05}$$

Determinati:

1. Numarul de ramuri ale [[Analiza sistemelor discrete cu metoda locului radacinilor|locului radacinilor]]; de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care il fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc


#### Exercitiul 4

Se considera functia de transfer a unui sistem in circuit inchis:

$$G_{0}(z)=\frac{0.06z}{z^{2}-1.51z+0.54}$$

1. Sa se determine modelul cu variabile de stare in forma complet observabila (demonstratie)
2. Sa se determine [[Modele ale sistemelor discrete cu variabile de stare#Conversia modelului cu variabile de stare in functii de transfer $z$|matricea fundamentala]] a sistemului


### Bilet 3
#### Exercitiul 1

Se considera un sistem discret cu reactie negativa unitara in care partea continua are urmatoarea forma:

$$G_{PC}(s)=\frac{k}{s+6}$$

1. Pentru $k=1$, sa se determine functia de transfer a sistemului in circuit plecand de la ecuatia cu diferente
2. Folosind graful de fluenta sa se determine functia de transfer a sistemului in cricuti inchis
3. Sa se determine pentru ce tip de intrare sistemul prezinta eroare stationara finita
4. Sa se determine raspunsul sistemului la marimea de intrare treapta unitara si sa se reprezinte grafic

---
**Rezolvare:**
1. 
$$\begin{align} & G_{0}(z)=\frac{G_{d}(z)}{1+G_{d}(z)} \\ & G_{d}(z)=Z\left\{  \frac{1-e^{-sT_{e}}}{s} \cdot  \frac{k}{s+6} \right\} = (1-z^{-1})Z\left\{ \frac{k}{s(s+6)} \right\} \\ & = \frac{z-1}{k} Z \left\{ \frac{C_{1}}{s} + \frac{C_{2}}{s+6} \right\} \\ & \begin{cases} C_{1}=\frac{k}{s+6} \bigg{|}_{s=0}=\frac{k}{6} \\ C_{2} = \frac{k}{s} \bigg{|}_{s=-6} = -\frac{k}{6} \end{cases} \\ & \implies \frac{z-1}{z} \cdot Z \left\{ \frac{\frac{k}{6}}{s}  \cdot \frac{-\frac{k}{6}}{s+6}\right\}= \frac{k}{6} \cdot \frac{z-1}{z}\cdot  Z \left\{ \underbrace{\frac{1}{s}}_{\text{trepata}}-\underbrace{\frac{1}{s+6}}_{\text{exponentiala}} \right\} \\ & = \frac{k}{6} \cdot \frac{z-1}{\cancel{z}} \left\{ \frac{\cancel{z}}{z-1} - \frac{\cancel{z}}{z-e^{-6T_{e}}} \right\} = \frac{k}{6} \cancel{(z-1)} \left\{  \frac{\cancel{z}-e^{-6T_{e}}- \cancel{z}+1}{\cancel{(z-1)}(z-e^{-6T_{e}})} \right\}  \\ &= \frac{k}{6} \cdot \frac{1-e^{-6T_{e}}}{z-e^{-6T_{e}}} \\ & \begin{cases} k=1 \\ T_{e}=0.1s \end{cases} \implies G_{d}(z) = \frac{1}{6}\cdot \frac{1-e^{-0.6}}{z-e^{-0.6}}= 0.16 \cdot \frac{1-0.55}{z-0..55}= \frac{0.07}{z-0.55} \end{align}$$
	```mermaid

	graph LR

		R((R)) -->|1| E1((E=X1))

		E1 --> X1((/))

		X1 --> E2((E*=X2))

		E2 -->|G| Y((Y=X3))

		Y -.->|−1| E1

	```

$$\begin{align} &\begin{cases} x_{1}=R-Y=R-x_{3} \\ x_{2}=E^{*}=x_{1}^{*} \\ x_{3}=Y=G \cdot x_{2} = G \cdot x_{1}^{*} \end{cases} \\ & \begin{cases} x_{1}=R-G \cdot x_{1}^{*} \\ x_{2}=x_{1}^{*} \\ x_{3} = G \cdot x_{1}^{*} \end{cases} \\ & \begin{cases} x_{1}^{*} = R^{*} - G^{*} x_{1}^{*} \\ x_{2}^{*}=x_{1}^{*} \\ x_{3}^{*} = G^{*} \cdot x_{1}^{*} \end{cases} \end{align}$$

	```mermaid
	graph LR
    R["R*"] -->|1| X1["X1*"]
    X1 -->|1| X2["X2*"]
    X2 -->|"(ERO G)"*| X3[" X3* = Y"]
    X1 -->|"-(ERO G)"*| X1
	```

2. 
$$\begin{align} & e_{st}^{*} = \lim_{ z \to 1 } (1-z^{-1})G(z) = \lim_{  z \to 1 } (1-z^{-1}) \frac{R(z)}{1+G(z)} \\ & R(z) = \frac{z}{z-1} \implies e_{st}^{*'} = \lim_{ z \to 1 } \cancel{\frac{z-1}{z}} \cdot \cancel{\frac{z}{z-1}} \cdot \frac{1}{1+ \frac{0.07}{z-0.05}} \\ & = \lim_{ z \to 1 } \frac{1}{\frac{z-0.05+0.07}{z-0.05}}= \lim_{ z \to 1 } \frac{1}{\frac{z+0.02}{z-0.05}}= \lim_{ z \to 1 } \frac{z-0.05}{z+0.02} =\frac{0.95}{1.02}=0.93  \\ & \implies \text{sistemul are eroare stationara la treapta}     \end{align}$$
3. 
$$\begin{align} & G_{0}(z)=\frac{G_{d}(z)}{1+G_{d}(z)} =\frac{\frac{0.07}{z-0.55}}{1+ \frac{0.07}{z-0.55}} = \frac{\frac{0.07}{z-0.55}}{\frac{z-0.55+0.07}{z-0.55}} \\ & = \frac{0.07}{\cancel{z-0.55}} \cdot \frac{\cancel{z-0.55}}{z-0.62} = \frac{0.07}{z-0.62} \\ & Y(z) = G_{0}(z) \cdot R(z) = \frac{0.07}{z-0.62} \cdot \frac{z}{z-1} = \frac{0.07 z}{(z-0.62)(z-1)} \\ & = \frac{0.07z}{z^{2}-1.62z+0.62} \bigg{|}z^{-2} \\ & y[k]=z^{-1}\{y(z)\} \\ & \text{se efectueaza impartirea polinomilor si rezulta} \\ & y(kT_{e})=\{0;0.07;0.11;0.14;\dots\} \end{align}$$
	![[Pasted image 20240618163246.png]]


#### Exercitiul 2

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):

$$G_{d}(z)=\frac{0.2z+0.7}{z^{2}+0.5z+0.05}$$

1. Sa se determine partea reala si partea imaginara
2. Punctul de unde pleaca curba polara si punctul unde se termina curba polara
3. Cum este sistemul in circuit deschis
4. Cum este sistemul in circuit inchis

#### Exercitiul 3

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$)

$$G_{d}(z)=k \frac{0.2z+0.07}{z^{2}-0.5z+0.05}$$

Determinati:

1. Numarul de ramuri ale [[Analiza sistemelor discrete cu metoda locului radacinilor|locului radacinilor]], de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care-l fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc

---
**Rezolvare:**
1. 
$$\begin{align} &\text{Pasul 1:} \\ & \begin{cases} n=2 \\ m=1 \end{cases} \implies n-m=1 \to \infty \\ \\ &z^{2} -0.5z+0.05=0 \\ & -p_{1}=0.36 \\ &-p_{2}=0.13 \\  \\ & 0.2z+0.07=0 \\ &0.2z=-0.07  \\ &z=-0.35  \end{align}$$
	![[Pasted image 20240619115029.png]]
2. 
$$\begin{align} & \text{Pasul 2:} \\ & \text{Portiunea de pe axa reala: }(-\infty;-0.36) \end{align}$$
3. 
$$\begin{align} & \text{Pasul 3} \\ &n-m=1 \implies \text{o asimptota} \\ & p_{r}=  \frac{\pm 180(2x+1)}{n-m} = \pm 130 \\ \\ \end{align}$$
4. 
$$ \text{nu avem poli/zerouri complexe}$$
5. 
$$\begin{align} & \text{Pasul 5} \\ & \text{Intersectie pe axa Im, puncte de ramificatie} \\ & 1+G(z)=0 \implies 1+ \frac{k(0.2z+0.07)}{z^{2}-0.5z+0.}=0 \\ & \implies k= - \frac{z^{2}-0.5z+0.05}{0.2z+0.05} \\ & \frac{dk}{dz}=0 \implies \frac{dk}{dz}=  \\ & \frac{-(2z-0.5)(0.27+0.05)-0.2(z^{2}-0.5z+0.05)}{(0.2z+0.05)^{2}}=0 \\ & \implies -0.6z^{2}-0.1z+0.035=0 \\ &\implies \begin{cases} z_{1}=-0.33 \\ z_{2}=0.17 \end{cases} \implies \text{punct de ramificatie}  \end{align}$$
6. 
$$\begin{align}& \text{Pasul 6:} \\& G(z)= \frac{0.2z+0.07}{z^{2}-0.5z+0.05}; z=x+jy \\& G(x+jy) = \frac{0.2(x+jy)+0.07}{(x+jy)^{2}-0.5(x+jy)+0.05} \\& = \frac{0.2x+2jy+0.07}{x^{2}+y^{2}+ +0.05-0.5x+j(x+y-0.5y)} \\& \angle G(z)= \arctan \underbrace{\frac{2y}{0.2x+0.07}}_{a} - \arctan \underbrace{\frac{x^{2}-y^{2}+0.05-0.5x}{2xy-0.5y}}_{b} \\& = (2k-1) \cdot 180 |\cdot \tan \\& \frac{a-b}{1+ab} = 0 \implies a=b \\&\frac{2\cancel{y}}{0.2x+0.07}= \frac{x^{2}-y^{2}+0.05-0.5x}{2x\cancel{y}-0.5 \cancel{y}} \\& 4x-1=0.2x^{3}-0.2xy^{2}+0.01x-0.1x^{2}+0.07x^{2}-0.07y^{2}+ \\&-0.03x^{2}-0.035x+0.0035 \\& 0.2x^{3}-0.2xy^{2}-0.07y^{2}-0.03x^{2}-4.035x=0.965\end{align}$$

#### Exercitiul 4

Se considera functia de transfer a unui sistem in circuit inchis:

$$G_{0}(z)=\frac{0.01z+0.01}{z^{2}-1.52z+0.54}$$

1. Sa se determine modelul cu variabile de stare in forma complet controlabila
2. Plecand de la modelul cu variabille de stare (matricea sistemului) sa se determine daca sistemul este controlabil




### Bilet 4
#### Exercitiul 1

Sa se schiteze locul radacinilor pentru un sistem de reglare cu reactie negativa unitara. Functia de transfer $z$ a sistemului in circuit deschis este ($T_{e}=1$):
$$G(z)=\frac{0.368k(z+0.717)}{(z-1)(z-0.368)}$$
Determinati:

1. Numarul de ramuri ale [[Analiza sistemelor discrete cu metoda locului radacinilor|locului radacinilor]], de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care-l fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc


---

1. 
$$\begin{align}& n=2 \\&m=1 \\&n-m=1 \to \text{ o ramura la }\infty  \\\\& \text{Calculam polii si zerourile} \\& -p_{1}=1 \\&-p_{2}=0.368 \\&-z_{1}=-0.717\end{align}$$
2. 
$$(-\infty,-0.717] \cup [0.368,1]$$

3. 
$$\begin{align}& n-m=1 \to \text{ o asimptota} \\& \varphi_{k}= \frac{\pm180(2k+1)}{n-m}  \\&\implies \varphi_{0}=\pm 180 \degree \end{align}$$
4. 
$$\begin{align}& 1+G(z)=0 \\& 1+ \frac{0.368k(z+0.717)}{(z-1)(z-0.368)}=0 \\& \implies k= \frac{-(z-1)(z-0.368)}{0.368(z+0.717)} \\& \frac{dk}{dz}=0 \implies \begin{cases}z_{1}=0.65 \\z_{2}=-2.08\end{cases} \in \text{portiunii} \\& \implies \text{2 puncte de ramificatie}\end{align}$$
5. 
$$\begin{align}& \begin{cases}G_{d}(z)=\frac{0.368k(z+0.717)}{(z-1)(z-0.368)} \\z=x+jy\end{cases} \implies \\& G_{d}(x+jy)=\frac{0.368k(x+jy+0.717)}{(x+jy-1)(x+jy-0.368)} \\& = \frac{0.368(x+0.717+jy)}{x^{2}+xyj-0.368x+xyj-y^{2}-0.368jy-x-jy+0.368} \\& = \frac{0.368(x+0.717+jy)}{(x^{2}-y^{2}-1.368x+0.368)+j(2xy-1.368)} \bigg| \angle \\& \angle G(x+jy)=(2k+1)180 \degree (\text{conditia argumentului}) \\&=\arctan\underbrace{\frac{y}{x-0.717}}_{a}-\arctan\underbrace{\frac{2xy-1.368y}{x^{2}-y^{2}-1.368x+0.368}}_{b}  =(2k+1)180 \degree \bigg|\tan \\& \frac{a-b}{1+ab}=0 \implies a=b \implies \frac{y}{x-0.717}=\frac{2xy-1.368y}{x^{2}-y^{2}-1.368x+0.368} \\& \implies \frac{1}{x+0.717}=\frac{2x-1.368}{x^{2}-y^{2}-1.368x+0.368} \\& \implies x^{2}-y^{2}-1.368x+0.368=(2x-1.368)(x+0.717) \\& \implies x^{2}-y^{2}-1.368x+0.368=2x^{2}+1.434x-1.368x-0.98 \\& \implies x^{2}+y^{2}+1.434=1.348 \\& \implies(x+0.717)^{2} + y^{2}=1.348+\underbrace{0.514}_{(0.717)^{2}} \\& \implies (x+0.717)^{2}+y^{2}=1.862 \\& \text{ecuatia cercului: }x^{2}+y^{2}=r^{2} \\& \implies (x+0.717)^{2}+y^{2}=\sqrt{ 1.862 } \\& \implies (x+0.717)^{2}+y^{2}=1.36^{2} \\& \implies \text{Cerc cu } \begin{cases}C(-0.717;0) \\R=1.36\end{cases}\end{align}$$


```tikz
\begin{document}
	\begin{tikzpicture}
		\draw [->] (-6,0) -- (4,0) node[above] {$Re$};
		\draw [->] (0,-3) -- (0,3) node[above] {$Im$};
		\draw[thick] (-6,0) -- (-1.434,0);
		\draw (-1.434,0) circle (0.1) node [above] {$-z_1$};
		\node at (0.736,0) {$\times$}; 
		\node at (0.736,0.3) {$-p_2$};
		\node at (2,0) {$\times$}; 
		\node at (2,0.3) {$-p_1$};
		\draw [thick] (0.736,0) -- (2,0);
		\node at (-2,-0.3) {$-1$};
		\node at (2,-0.3) {$1$};
		\draw (-1.434,0) circle (2.72);
		\draw (0,0) circle (2);
		\node at (0.48,1.95) {$\textbf{x}$};
		\node at (0.48,-1.95) {$\textbf{x}$};
		\node at (-4.15,0) {$\textbf{x}$}; 
	\end{tikzpicture}
\end{document}
```
#### Exercitiul 2
Fie sistemul din figura ($T_{e}=0.3s$)
```tikz
\begin{document}
	\begin{tikzpicture}
		\draw[thick,->] (0,6) -- (2,6);
		\node at (1.25,6.2) {$R(s)$};
		\node at (1.25,5.8) {$R(z)$};
		\draw  (2.3,6) circle (0.3cm);
		\def\centerX{2.3} 
		\def\centerY{6} 
		\def\radius{0.2}
		\draw (\centerX - \radius, \centerY - \radius) -- (\centerX + \radius, \centerY + \radius);
		 \draw (\centerX - \radius, \centerY + \radius) -- (\centerX + \radius, \centerY - \radius);
		 \draw (2.6,6) -- (3.8,6);
		 \node at (3.2,6.2) {$E(s)$};
		 \draw (3.85,6) circle (0.05cm);
		 \draw (3.9,6) -- (4.4,6.2);
		 \draw (4.45,6) circle (0.05cm);
		 \draw[->] (4.1,6.3) .. controls (4.2,6.1) and (4.2,5.9)  .. (4.1, 5.7);
		 \node at (4.2,6.5) {$E_i$};
		 \node at (4.2,5.5) {$T_e$};
		 \draw[->] (4.5,6) -- (5.5,6);
		 \draw (5.5,6.5) -- (7.5,6.5) -- (7.5,5.5) -- (5.5,5.5) -- (5.5,6.5);
		 \node at (6.5,6) {$ERO$};
		 \draw [->] (7.5,6) -- (8.5,6);
		 \draw (8.5,6.5) -- (10.5,6.5) -- (10.5,5.5) -- (8.5,5.5) -- (8.5,6.5);
		 \node at (9.5,6) {$\frac{1}{s(s+1)}$};
		 \draw (10.5,6) -- (11.4,6);
		 \draw (11.5,6) circle (0.1);
		 \draw [->] (11.6,6) -- (12.8,6);
		 \node at (12.1,6.2) {$Y(s)$};
		 \node at (12.1,5.8) {$Y(z)$};
		 \draw [->] (11.5,5.9) .. controls (11.5,4) and (2.3,4) .. (2.3,5.7); 
		 \node at (2.6,5.6) {$-$};
	\end{tikzpicture}
\end{document}

```
1. Sa se determine functia de transfer discreta a sistemului inchis
2. Sa se determine raspunsul sistemului la marimea de intrare treapta unitara si sa se reprezinte grafic
3. Sa se determine pentru ce tip de intrare sistemul prezinta eroare stationara
4. Folosind curba polara sa se determine stabilitatea sistemului in bucla inchisa

---

1. 
$$\begin{align} G_{0}(z)&=\frac{G_{d}(z)}{1+G_{d}(z)} \\ G_{d}(z)&= Z\left\{ \frac{1-e^{-sT_{e}}}{s} \cdot \frac{1}{s(s+1)} \right\} \\& =(1-z^{-1})Z\left\{ \frac{1}{s^{2}(s+1)} \right\} \\& = \frac{z-1}{z} Z \left\{ \frac{c_{1}}{s^{2}}+\frac{c_{2}}{s}+\frac{c_{3}}{s+1} \right\}\ \\G_{d}(s)& =\frac{1}{s^{2}(s+1)}=  \frac{c_{1}}{s^{2}}+\frac{c_{2}}{s}+\frac{c_{3}}{s+1}\bigg|\cdot s^{2} \\s^{2} \cdot G_{d}(s)& = c_{1} \bigg|_{s=0} \implies c_{1}=s^{2} \frac{1}{s^{2}(s+1)} \bigg|_{s=0}=1 \\c_{2}&= \frac{d}{ds}[c_{1}]\bigg|_{s=0}=\frac{d}{ds}\left[ \frac{1}{s+1} \right]= \frac{1}{(s+1)^{2}}\bigg|_{s=0}=-1 \\(s+1)G_{d}(s) & = c_{3}\bigg|_{s=-1} \implies c_{3}=(s+1) \frac{1}{s^{2}(s+1)}=1 \\& \implies  \frac{z-1}{z} Z \left\{ \frac{1}{s^{2}}-\frac{1}{s}+\frac{1}{s+1} \right\}= \\ & = \frac{z-1}{z} \left\{ \frac{T_{e}z}{(z-1)^{2}}-\frac{z}{z-1}+\frac{z}{z-e^{-T_{e}}} \right\} \\&=  (z-1)\left[ \frac{T_{e}}{(z-1)^{2}}-\frac{1}{z-1}+\frac{1}{z-e^{-T_{e}}} \right] \\& = (z-1) \cdot \frac{T_{e}(z-e^{-T_{e}})-(z-1)(z-e^{-T_{e}})+(z-1)^{2}}{(z-1)^{2}(z-e^{-T_{e}})} \\& =\frac{T_{e}(e-e^{-T_{e}})-(z-1)[z-e^{-T_{e}}-z+1]}{(z-1)(z-e^{-0.3})} \\& = \frac{0.3(z-0.74)-(z-1)\cdot 0.26}{(z-1)(z-0.74)} \\& = \frac{0.3z-0.22-0.26z+0.26}{(z-1)(z-0.74)} \\& =\frac{0.04z+0.04}{(z-1)(z-0.74)} \\&= \frac{0.04(z+1)}{(z-1)(z-0.74)} \\G_{0}(z) & = \frac{G_{d}(z)}{1+G_{d}(z)} \\& = \frac{\frac{0.04(z+1)}{(z-1)(z-0.74)}}{1+\frac{0.04(z+1)}{(z-1)(z-0.74)}} \\& = \frac{0.04(z+1)}{(z-1)(z-0.74)+0.04(z+1)} \\& = \frac{0.04(z+1)}{z^{2}-1.74z+0.74+0.04z+0.04} \\& = \frac{0.04(z+1)}{z^{2}-1.72z+0.78}\end{align}$$
2. 
$$\begin{align}& y[k]=Z^{-1}\{Y(z)\} \\& \begin{cases}Y(z)=G_{0}(z)R(z) \\R(z)=\frac{z}{z-1} (\text{treapta})\end{cases} \implies \\& Y(z)= \frac{0.04(z+1)z}{(z^{2}-1.7z+0.78)(z-1)} \\& = \frac{0.04z^{2}+0.04z}{z^{3}-2.7z^{2}+2.48z-0.78} \bigg| \cdot z ^{-3} \\& \implies Y(z^{-1})= \frac{0.04z^{-1}+0.04z^{-2}}{z-2.7z^{-1}+2.48z^{-2}-0.78z^{-3}} \\& \text{Se efectueaza impartirea polinomiala si rezulta:} \\& y[k]= \{0;0.04;0.14;0.37;0.7;\dots\}\end{align}$$

```tikz
\begin{document}
	\begin{tikzpicture}
		\draw[thick,->] (0,0) -- (12,0) node [above] {$kT_e$};
		\draw[thick,->](0,0) -- (0,8) node[right] {$y[k],u[k]$};
		\draw[thick] (1,0) -- (1,1) -- (2,1) -- (2,0);
		\draw[thick] (2,0) -- (2,2) -- (3,2) -- (3,0);
	 	\draw[thick] (3,0) -- (3,3) -- (4,3) -- (4,0);
		\draw[thick] (4,0) -- (4,4) -- (5,4) -- (5,0);
		\draw[thick,dotted] (0,7) -- (12,7) node[xshift= -12.3 cm] {$1$};
		\node at (-0.2,-0.2) {$0$};
		\node at (1,-0.2) {$T_e$};
		\node at (2,-0.2) {$2T_e$};
		\node at (3,-0.2) {$3T_e$};
		\node at (4,-0.2) {$4T_e$};
		\node at (5,-0.2) {$5T_e$};
		\draw [thick, dotted] plot [smooth] coordinates {(0,0) (1,1) (2,2) (3,3) (4,4) (5,5) (6,6) (7,8) 
	(7.5,8.7)	(8,9) (9, 8.8) (9.5,7.8) (9.7,7) (10,6) (10.5,5.5) (11,5.5) (11.6,6) (11.8,7) (12,7)};
 	\end{tikzpicture}
\end{document}
```

3.
$$\begin{align}& G_{d}(z)= \frac{0.04(z+1)}{(z-1)(z-0.74)} \\& K_{p}^{*} = \lim_{ z \to 1 } G_{d}(z)=\frac{0.08}{0}=\infty\implies \\& \implies e_{st}^{*1}=\frac{1}{1+K_{p}^{*}}=\frac{1}{\infty}=0 \\& K_{v}^{*}= \lim_{ z \to 1 } \frac{z-1}{T_{e}}G_{d}(z)=\frac{z-1}{T_{e}} \frac{0.04(z+1)}{(z-1)(z-0.72)} \\& = \frac{0.08}{0.3 \cdot 0.26} = 1.02 \implies e_{st}^{*t} =\frac{1}{K_{v}}=\frac{1}{1.02}=0.98  \\& \implies \text{sistemul prezina eroare stationara finita} \\& \quad\quad\text{ pentru intrarea rampa unitara}\end{align}$$
4. 
$$\begin{align}& G_{d}(z) = \frac{0.04(z+1)}{(z-1)(z-0.74)} \\& \text{Pentru } \frac{1}{s(s+1)}: \begin{cases}\alpha=1 \\n-m=2\end{cases} \\& z=\frac{1+ \frac{T_{e}}{2}\omega}{1- \frac{T_{e}}{2}\omega} = \frac{1+0.5\omega}{1-0.5\omega} \implies \\& \implies G_{d}(\omega) = \frac{0.04\left(\frac{1+0.5\omega}{1-0.5\omega}+1\right)}{\left(\frac{1+0.5\omega}{1-0.5\omega}-1\right)\left(\frac{1+0.5\omega}{1-0.5\omega}-0.74\right)} \\& = \frac{0.04(1\cancel{+0.15\omega} +1 \cancel{-0.15\omega})}{(\cancel{1}+0.15\omega \cancel{-1} +0.15\omega)(1+0.5\omega-0.74+0.11\omega)} \\& =\frac{0.04 \cdot 2}{0.3\omega(0.26+0.26\omega)}=\frac{0.08}{0.08\omega(1+\omega)}=\frac{1}{\omega(1+\omega)} \\& \omega \to j\omega \\& G(j\omega)=\frac{1}{j\omega(1+j\omega)}= \frac{-j\omega(1-j\omega)}{\omega^{2}(1+\omega^{2})} = \frac{-j\omega - \omega^{2}}{\omega^{2}(1+\omega^{2})} \\& = \frac{\cancel{\omega}(-j-\omega)}{\omega^{\cancel{2}}(1+\omega^{2})}=\frac{-\omega-j}{\omega(1+\omega^{2})}= \frac{-\omega}{\omega(1+\omega^{2})}-j \frac{1}{\omega(1+\omega^{2})} \\& = \frac{-1}{1+\omega^{2}}-j \frac{1}{\omega(1+\omega^{2})} \\& Re\{G(j\omega)\}= -\frac{1}{1+\omega^{2}}; \quad Im\{G(j\omega)\}= -\frac{1}{\omega(1+\omega^{2})} \\& \lim_{ \omega \to \infty } Re\{G(j\omega)\}=0; \quad \lim_{ \omega \to \infty } Im\{G(j\omega)\}=0 \\& \text{Sistemul este stabil deoarece curba polara a circuitului} \\& \text{deschis nu inconjoara punctul }-1+j \cdot 0\end{align}$$
#### Exercitiul 3
Folosind transformata matched sa se  determine functia de transfer $Z$ pentru un proces continuu avand urmatoarea functie de transfer: 
$$G(s)=\frac{K_{e}(s+a)}{s(s+b)}, a=2,b=10,K_{c}=10$$
---
$$\begin{align}
& G(s)=\frac{10(s+2)}{s(s+10)}; G(z)=K_{d} \frac{(z-e^{-sT_{e}})(z+1)}{(z-1)(z-e^{-5T_{e}})} \\
& \implies \lim_{ z \to 1 } \left\{ \frac{\cancel{z-1}}{zT_{e}} \cdot K_{d} \frac{(z-e^{-sT_{e}})(z+1)}{\cancel{(z-1)}(z-e^{-5T_{e}})}  \right\} \\
& \alpha=1 \implies \lim_{ s \to 0 } \{s^{1} \cdot G(s)\}= \lim_{ z \to 1 } \left\{ \left( \frac{z-1}{zT_{e}} \right)^{1}  \cdot G(z)\right\}    
\end{align}$$

#### Exercitiul 4
Sa se determine modelul discret cu variabile de stare pentru ansamblul foirmat din CNA si un proces continuu reprezentat prin urmatoarea functie de transfer:
$$G(s)=\frac{1}{s^{2}+3s+2}$$
---

$$\begin{align}
& G(s)=\frac{Y(s)}{U(s)}= \frac{Y(s)}{X(s)} \cdot \frac{X(s)}{U(s)} = 1 \cdot \frac{1}{s^{2}+3s+2} \\
& \frac{X(s)}{U(s)}=\frac{1}{s^{2}+3s+2} \\
&\implies s^{2}X(s)+3sX(s)+2X(s)=U(s) \bigg|\mathcal{L}^{-1} \\
& \implies \frac{d^{2}X(t)}{dt^{2}}+3 \frac{dX(t)}{dt}+2X(t)=U(t) \\
& \begin{cases}
X_{1}(t)=X(t) \\
X_{2}(t)=\frac{dX(t)}{dt}= \dot{X_{1}}(t) \\
X_{3}(t)= \frac{d^{2}X(t)}{dt^{2}}=\dot{X_{2}}(t)=-2X_{1}(t)-3X_{2}(t)+U(t)
\end{cases} \\
&\dot{X_{1}}(t) =X_{2}(t) \\
& \dot{X_{2}}
(t) = -2X_{1}(t) -3X_{2}(t)+U(t) \\
& \frac{Y(s)}{X(s)}=1; Y(s)=X(s)\bigg|\mathcal{L}^{-1} \implies Y(t)= X(t)=X_{1}(t) \\
& A = \begin{bmatrix}
0 & 1 \\
-2 & -3
\end{bmatrix} \quad B = \begin{bmatrix}
0 \\
1
\end{bmatrix} \quad C= \begin{bmatrix}
1 & 0
\end{bmatrix} \quad D=0 \\
\phi&=I+A \cdot T_{e}+ \frac{A^{2}T_{e}^{2}}{2!} \\
& = \begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix} + \begin{bmatrix}
0 & 1 \\
-2 & -3
\end{bmatrix}+\frac{1}{2} \begin{bmatrix}
0 & 1 \\
-2 & -3
\end{bmatrix} \cdot \begin{bmatrix}
0 & 1 \\
-2  & -3
\end{bmatrix} \\
& = \begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}+ \begin{bmatrix}
0 & 1 \\
-2 & -3
\end{bmatrix}+\frac{1}{2} \begin{bmatrix}
-2 & -3 \\
6 & 9
\end{bmatrix} \\
&= \begin{bmatrix}
1 & 1 \\
-2 & -2
\end{bmatrix} + \begin{bmatrix}
-1 & -\frac{3}{2} \\
3 & \frac{9}{2}
\end{bmatrix} = \begin{bmatrix}
0 & -\frac{1}{2} \\
1 & \frac{5}{2}
\end{bmatrix} \\
\Gamma &= B \cdot T_{e} + \frac{A\cdot B T_{e}^{2}}{2!} \\
& = \begin{bmatrix}
0 \\
1
\end{bmatrix}+\frac{1}{2} \begin{bmatrix}
0 & 1 \\
-2 & -3
\end{bmatrix} \cdot \begin{bmatrix}
0 \\
1
\end{bmatrix} \\
&= \begin{bmatrix}
0 \\
1
\end{bmatrix} + \frac{1}{2} \begin{bmatrix}
 1 \\
-3
\end{bmatrix} \\
& = \begin{bmatrix}
0 \\
1
\end{bmatrix} + \begin{bmatrix}
\frac{1}{2} \\
-\frac{3}{2}
\end{bmatrix} = \begin{bmatrix}
 \frac{1}{2} \\
-\frac{1}{2}
\end{bmatrix} \\
& C = \begin{bmatrix}
1 & 0
\end{bmatrix} \quad D =0
\end{align}$$


### Bilet diana (bun)
#### Exercitiul 1

Se considera un sistem discret cu reactie negativa unitara in care partea continua are urmatoarea forma:

$$G_{PC}(s)=\frac{k}{s+6}$$

1. Pentru $k=1$, sa se determine functia de transfer a sistemului in circuit plecand de la ecuatia cu diferente
2. Folosind graful de fluenta sa se determine functia de transfer a sistemului in cricuti inchis
3. Sa se determine pentru ce tip de intrare sistemul prezinta eroare stationara finita
4. Sa se determine raspunsul sistemului la marimea de intrare treapta unitara si sa se reprezinte grafic

---

1. 
$$\begin{align}& G_{p}(s)= \frac{1}{s+6} = \frac{Y(s)}{U(s)} \\& \implies sY(s)+6Y(s)=U(s)\bigg|\mathcal{L}^{-1} \\& \implies \frac{dY(t)}{dt}+6Y(t)=U(t) \\&\begin{cases}U(t)\to U[k] \\Y(t)\to Y[k] \\\frac{dY(t)}{dt}\to \frac{Y[k]-Y[k-1]}{T_{e}}\end{cases} \implies \\& \implies \frac{Y[k]-Y[k-1]}{T_{e}}+6Y[k]=U[k] \\& \implies Y[k]-Y[k-1]+6T_{e}Y[k]=T_{e}U[k] \\& \implies Y[k](1+6T_{e})-Y[k-1]=T_{e}U[k] \bigg| z\\&\implies Y(z)(1+6T_{e})-z^{-1}Y(z)=T_{e}\cdot U(z) \\&\implies Y(z)(1+6T_{e}-z^{-1})=T_{e}U(z) \\& \implies G_{p}(z)=\frac{Y(z)}{U(z)}=\frac{T_{e}}{1+6T_{e}-z^{-1}}=\frac{T_{e}z}{z+6T_{e}z-1} \\& G_{0}(z)=\frac{G_{p}(z)}{1+G_{p}(z)}=\frac{\frac{T_{e}z}{z(1+7T_{e})-1}}{1+\frac{T_{e}z}{z(1+7T_{e})-1}}=\frac{T_{e}z}{z(1+6T_{e})-1+T_{e}z} \\& =\frac{T_{e}z}{z(1+7T_{e})-1}\end{align}$$
```tikz
\begin{document}
		\begin{tikzpicture}
			\draw[thick,->] (0,6) -- (2,6) node[above left] {$R(s)$};
			\draw [thick] (2.3,6) circle (0.3cm);
			\def\centerX{2.3} 
			\def\centerY{6} 
			\def\radius{0.2}
			\draw[thick] (\centerX - \radius, \centerY - \radius) -- (\centerX + \radius, \centerY + \radius);
			 \draw[thick] (\centerX - \radius, \centerY + \radius) -- (\centerX + \radius, \centerY - \radius);
			 \draw[thick] (2.6,6) -- (3.8,6);
			 \draw[thick] (3.85,6) circle (0.05cm);
			 \draw[thick] (3.9,6) -- (4.4,6.2);
			 \draw[thick] (4.45,6) circle (0.05cm);
			 \draw[thick,->] (4.1,6.3) .. controls (4.2,6.1) and (4.2,5.9)  .. (4.1, 5.7);
			 \draw[thick] (4.5,6) -- (6,6);
			 \draw[thick] (6,6.5) -- (8,6.5) -- (8,5.5) -- (6,5.5) -- (6,6.5);
			 \node at (7,6) {$G_{pc}$};
			 \draw [thick] (8,6) -- (10,6);
			 \draw [thick] (10.1,6) circle (0.1);
			 \draw [thick,->] (10.2,6) -- (12,6)node[above] {$Y$};
			 \draw [thick,->] (10.1,5.9) .. controls (10.1,4) and (2.3,4) .. (2.3,5.7);
			 \node at (2.7,5.7) {$-$};
		\end{tikzpicture}
	\end{document}
	```

```tikz
\begin{document}
	\begin{tikzpicture}
		\draw[->, thick] (0,0) -- (1,0) node [above left] {$R$};
		\draw[thick] (1,0) -- (2.9,0);
		\draw[thick] (3,0) circle (0.1) node [above] {$E=x_1$};
		\draw [thick, ->]  (3.1,0) -- (4.1,0);
		\draw [thick] (4.1,0) -- (5,0);
		\draw [thick] (5.05,0) circle (0.05);
		\draw [thick] (5.65,0) circle (0.05);
		\draw [thick , ->] (5.3,0.5) .. controls (5.4, 0.25) and (5.4, -0.25) .. (5.3,-0.5) node [below] {$T_e$};
		\draw [thick] (5.1,0) -- (5.7,0.4) node [above left] {$E_i$};
		\draw [thick] (5.7,0) -- (7.7,0);
		\draw [thick] (7.8,0) circle (0.1) node [above] {$E^{*}=x_2$};
		\draw [thick, ->] (7.9,0) -- (10,0) node[above] {$ERO \cdot G_p$};
		\draw [thick] (10,0) -- (11.9,0);
		\draw [thick] (12,0) circle (0.1) node [above] {$Y=x_3$};
		\draw [thick, ->] (12,-0.1) .. controls (10, -2) .. (7.5,-2) node [below right] {$-1$};
		\draw [thick] (7.5,-2) .. controls (5,-2) .. (3, -0.1) node [right] {$-$};  	
	\end{tikzpicture}
\end{document}
```

$$\begin{align}
& \begin{cases}
x_{1}=R- 1 \cdot Y=R-x_{3} \\ 
x_{2}=E^{*}=x_{1}^{*}  \\
x_{3}=G_{PC}\cdot x_{2} = G_{PC} \cdot x_{1}^{*}
\end{cases} \\
& \begin{cases}
x_{1}= R-G_{PC} \cdot x_{1}^{*} \\
x_{2} = x_{1}^{*} \\
x_{3} = G_{PC} \cdot x_{1}^{*}
\end{cases} \Bigg|^{*} \implies \\
& \begin{cases}
x_{1}^{*} = R^{*} - G_{PC}^{*} \cdot x_{1}^{*} \\
x_{2}^{*} = x_{1}^{*} \\
x_{3}^{*} = G_{PC}^{*} \cdot x_{1}^{*}
\end{cases}
\end{align}$$

```tikz
\begin{document}
	\begin{tikzpicture}
		\draw (0,0) circle (0.01) node[above] {$R^*$}; 	
		\draw[thick] (0,0) -- (2,0);
		\draw[thick] (2.1,0) circle (0.1) node [above right] {$x_1^*$};
		\draw [thick,->] (2.1,-0.1) ..controls (3,-1) and (1,-0.8) .. (2.1,-0.1) node [below right] {$-(ERO \cdot G)^*$};
		\draw [thick, ->](2.2, 0) -- (3.4,0) node [above] {$1$};
		\draw [thick] (3.4,0) -- (4.4,0);
		\draw[thick] (4.5,0) circle (0.1) node [above] {$x_2^*$};
		\draw [thick,->](4.6,0) -- (5.6,0) node[above] {$(ERO \cdot G)^*$};
		\draw [thick] (5.6,0) -- (6.6,0);
		\draw [thick](6.7,0) circle (0.1) node[ above right] {$x_3^*$};
	\end{tikzpicture}
\end{document}
```
 $$\begin{align}&\implies G_{0}(z)=\frac{(ERO \cdot G(s))^{*}}{1-(ERO \cdot G(s))^{*}} \Bigg|_{s=\frac{1}{T_{e}}\ln z} \\&= \frac{Z\{ERO \cdot G(s)\}}{1+Z\{ERO \cdot G(s)\}} \\& = Z\{ERO \cdot G(s)\}=Z\left\{ \frac{1-e^{-sT_{e}}}{s}  \cdot \frac{1}{s+6} \right\} \\& = (1-z^{-1}) Z \left\{ \frac{1}{s(s+6)} \right\}= (1-z^{-1}) \cdot Z \left\{ \frac{C_{1}}{s}+\frac{C_{2}}{s+6} \right\} \\& \implies C_{1}=\frac{1}{s+6} \bigg|_{s=0} \implies C_{1}=\frac{1}{6} \\& \implies C_{2}=\frac{1}{s} \bigg|_{s=-6} \implies C_{2}=-\frac{1}{6}\end{align}$$
3. 
$$\begin{align}
& G_{0}(z)=\frac{1}{G} \frac{1-e^{-6T_{e}}}{z-2 \cdot e^{-6T_{e}}+1}, \text{ pentru }T_{e}=0.1 \\
& \implies G_{0}(z)=\frac{0.16}{z-0.1}
\end{align}$$
#### Exercitiul 2

Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):
$$G_{d}(z)=\frac{0.13z+0.02}{z^{2}-0.39z+0.007}$$
1. Sa se determine partea reala si partea imaginara
2. Sa se determine punctul de unde pleaca curba polara si punctul de unde se termina curba polara
3. Sa se determine cum este sistemul in circuit deschis (argumentati)
4. Sa se determine cum este sistemul in circuit inchis (argumentati)

---

1. 
$$\begin{align} z&=\frac{1+\frac{T_{e}}{2}\omega}{1-\frac{T_{e}}{2}\omega}\implies z=\frac{1+0.5\omega}{1-0.5\omega} \\\implies G_{d}(\omega) & = \frac{0.13\frac{1+0.5\omega}{1-0.5\omega}+0.02}{\left(\frac{1+0.5\omega}{1-0.5\omega}\right)^{2}-0.39 \frac{1+0.5\omega}{1-0.5\omega} +0.007} \\&= \frac{0.13+0.07\omega+0.02-0.02\omega}{\cancel{1-0.5\omega}} \cdot \frac{(1-0.5\omega)^{\cancel{2}}}{1+\omega+0.25\omega^{2}-0.39+0.07\omega^{2}+0.07-0.07\omega^{2}+0.01\omega^{2}}  \\&= \frac{(0.15+0.05\omega)(1-0.5\omega)}{0.68+0.93\omega+0.33\omega^{2}}  \\\implies G_{d}(j\omega) & = G(\omega)\bigg|_{\omega=j\omega} = \frac{(0.15+0.05j\omega)(1-0.5j\omega)}{0.68+0.93j\omega-0.33\omega^{2}} \\& = \frac{0.15-0.07j\omega+0.05j\omega+0.02\omega^{2}}{0.68-0.3\omega^{2}+0.93j\omega} \\& = \frac{0.15-0.02j\omega+0.02\omega^{2}}{0.68-0.3\omega^{2}+0.93j\omega} \\& = \frac{(0.15-0.02j\omega+0.02\omega^{2})(0.68-0.3\omega^{2}-0.93j\omega)}{0.68- \\0.4\omega^{2}+0.09\omega^{4}+0.86\omega^{2}} \\& = \frac{0.1-0.04\omega^{2}-0.13j\omega-0.01j\omega+\cancel{0.006j\omega^{3}}- \cancel{0.01\omega^{2}}+\cancel{0.01\omega^{2}}-0.006\omega^{4}-\cancel{0.006j\omega^{3}}}{0.68+0.46\omega^{2}+0.09\omega^{4}} \\&=\frac{0.1-0.04\omega^{2}-0.06\omega^{4}+j(-0.14\omega)}{0.68+0.46\omega^{2}+0.09\omega^{4}} \\\implies& Re\{G(j\omega)\}=\frac{0.1-0.04\omega^{2}-0.06\omega^{4}}{0.68+0.46\omega^{2}+0.09\omega^{4}} \\& Im\{G(j\omega)\}=\frac{-0.14\omega}{0.68+0.46\omega^{2}+0.09\omega^{4}}\end{align}$$
2. 
$$\begin{align}& n-m=0 \\& \alpha=0  \\& Im\{G(j\omega)\}=0 \implies \omega=0 \implies Re\{G(j\omega)\}=\frac{0.1}{0.68}=0.147 \\ &\lim_{ \omega \to \infty }Im\{G(j\omega)\}=0;\lim_{ \omega \to \infty }Re\{G(j\omega)\}=\frac{-0.06}{0.9}=-0.067  \\&\implies \text{ pleaca de pe o axa reala din punctul }0.147 \\& \quad \quad \quad\text{ si se termina in } -0.067\end{align}$$
3. Sistemul in circuit deschis este stabil deoarece curba nu incercuieste $-1+j \cdot 0$
4. Sistemul in circuit inchis este stabil

	```tikz
	\begin{document}
		\begin{tikzpicture}
			\draw [thick,->] (-3,0) -- (3,0) node[above] {$Re$};
			\draw [thick,->] (0,-3) -- (0,3) node[above] {$Im$};
			\node at (-2,0) [yshift = 0.2cm] {$-1$};
			\node at (2,0) [yshift = 0.2cm] {$-1$};
			 \draw[dotted] (0,1) arc (90:180:1);
			 \draw (-1,0) arc (180:450:1); 
	 	\end{tikzpicture}
	\end{document}
	```

#### Exercitiul 3
Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):
$$G_{d}(z)=k \frac{0.16z+0.04}{z^{2}-0.4z+0.02}$$
Determinati:
1. Numarul de ramuri ale locului radacinilor, de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care-l fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc

---

1. 
$$\begin{align}& n=2 \text{ ramuri ale locului radacinilor} \\& m=1\implies n-m=1 \text{ o ramura la } \infty\end{align}$$
2. 
$$\begin{align}& -p_{1} = 0.34; -p_{2}=0.06; -z_{1}=0.25 \\& (-\infty;-0.25] \cup [0.06;0.34]\end{align}$$
3. 
$$\begin{align}&n-m=1 \implies \text{ o asimptota} \\& \varphi_{k}= \frac{\pm 180 \degree(2k+1)}{n-m};k=0.1 \\& \varphi = \pm180 \degree; \text{ nu avem punct de intersectie}\end{align}$$
4. 
$$\begin{align}& 1+ \frac{k(0.16z+0.04)}{z^{2}-0.4z+0.02}=0 \implies k= \frac{-(z^{2}-0.4z+0.02)}{0.16z+0.04} \\\implies & \frac{dk}{dz}=\frac{-(2z-0.4)(0.16z+0.04)+0.16(z^{2}-0.4z+0.02)}{(0.16z+0.4)^{2}}=0 \\\implies & -0.32z^{2}-0.08z+ \cancel{0.064z}+0.016+0.16z^{2}-\cancel{0.064z}+0.0032=0 \\\implies & -0.16z^{2}-0.08z+0.048=0 \\\implies & 0.16z^{2}+0.08z-0.048=0 \\\implies & \begin{cases}z_{1}=-0.85 \\z_{2}=0.35\end{cases} \end{align}$$
5. 
$$\begin{align}G(x+yj)&= \frac{0.16(x+jy)+0.04}{(x+jy)^{2}-0.4x+0.02+2xyj-0.4yj} \\&= \frac{0.16x+0.16yj+0.04}{x^{2}+2xyj-y^{2}-0.4x-0.4yj+0.02} \\&= \frac{0.16x+0.16yj+0.04}{x^{2}-y^{2}-0.4x+0.02+2xyj-0.4yj} \\\angle G(x+yj) &= 180 \degree(2k+1) \implies\\ \arctan &\underbrace{\frac{0.16y}{0.16x+0.04}}_{a} - \arctan \underbrace{\frac{2xy-0.4y}{x^{2}-y^{2}-0.4x+0.02}}_{b}= 180 \degree(2k+1)\tan \\& \implies \frac{ab}{1+ab} = 0 \implies a=b  \\&\implies \frac{0.16\cancel{y}}{0.16x+0.04}=\frac{\cancel{y}(2x-0.4)}{x^{2}-y^{2}-0.4x+0.02} \\& \implies 0.16x^{2}-0.16y^{2}-\cancel{0.064x}+0.032  = 0.32x-\cancel{0.064x}+0.08x-0.016 \\& \implies 0.16x^{2}-0.16y^{2}-0.4x=-0.048 \\& \implies 0.16x^{2}-0.4x+1.56-0.16y^{2}=-0.048+1.56 \\& \implies(x+1.25)^{2}-0.16y^{2}=1.51 \\& \implies C (-1.25;0) \text{ si } R=1.22\end{align}$$

	```tikz
	\begin{document}
			\begin{tikzpicture}
			\draw [->] (-4,0) -- (3,0) node [right] {$Re$};
			\draw [->] (0,-2) -- (0,2) node [above] {$Im$};
			\draw [thick] (-4,0) -- (-1,0);
			\draw [thick] (0.2,0) -- (1.44,0);
			\draw (-1,0) circle (0.05) node[above] {$-z_1$};
			\draw (0.2,0) circle (0.05) node [above] {$-p_2$};
			\draw (1.44,0) circle (0.05) node [above] {$-p_1$};
		 	\end{tikzpicture}
		\end{document}
	```

#### Exercitiul 4
Se considera functia de transfer a unui sistem in circuit inchis
$$G_{0}(z)=\frac{0.02z+0.02}{z^{2}-1.49z+0.54}$$
1. Sa se determine modelul cu variabile de stare in forma complet controlabila
2. Plecand de la modelul cu variabile de stare (matricele sistemului) sa se determine daca sistemul este controlabil

---

1. 
$$\begin{align}& G_{0}(z)=\frac{0.2z+0.02}{z^{2}-1.49z+0.54} = \frac{Y(z)}{R(z)} \\&\implies \frac{Y(z)}{X(z)}\cdot \frac{X(z)}{R(z)} \\& \frac{Y(z)}{R(z)} =0.02z+0.02 \\& \frac{X(z)}{R(z)}=\frac{1}{z^{2}-1.49z+0.54} \\& \implies z^{2}X(z)-1.49zX(z)+0.54X(z)=R(z) \bigg|z^{-1} \\&  \begin{cases}x[k+2]-1.49x[k+1]+0.54x[k]=R[k] \\ x[k]=x_{1}[k] \\x[k+1]=x_{2}[k]=x_{1}[k+1] \\x[k+2]=x_{2}[k+1]=-0.54x_{1}[k]+1.49x_{2}[k]+r[k]\end{cases} \implies \\& \implies \phi = \begin{bmatrix}0 & 1 \\-0.54 & 1.49\end{bmatrix};\Gamma=\begin{bmatrix}0 \\1\end{bmatrix} \\& \frac{Y(z)}{X(z)}=0.02z+0.02 \implies 0.02zX(z)+0.02X(z)=Y(z) \bigg|z^{-1} \\& \implies y[k]=0.02x[k+1]+0.02x[k] \\& \implies y[k]=0.02x_{2}[k]+0.02x_{1}[k] \\& \implies C= [0.02 \quad 0.02] \text{ si }D=0\end{align}$$
2. 
$$\begin{align}& P = \begin{bmatrix}\Gamma &  \phi \Gamma\end{bmatrix} = \begin{bmatrix}0 & 1  \\1 & 1.49\end{bmatrix} \implies \det P=-1 \neq 0 \implies \text{sistem controlabil} \\& \phi\Gamma= \begin{bmatrix}0 & 1 \\-0.54 & 1.49\end{bmatrix} \begin{bmatrix} 0 \\1\end{bmatrix} = \begin{bmatrix}1 \\1.49\end{bmatrix}\end{align}$$

### Bilet barbat
#### Exercitiul 1

Se considera un sistem discret cu reactie negativa unitara in care partea continua are urmatoarea forma:

$$G_{PC}(s)=\frac{k}{s+5}$$

1. Pentru $k=1$, sa se determine [[Seminar 3 SAE#Exercițiul 1|functia de transfer a sistemuluiu in circuit inchis plecand de la ecuatia cu diferente]]
2. Folosind graful de fluenta sa se determine functia de transfer a sistemului in circuit inchis
3. Sa se determine pentru ce tip de intrare sistemul prezinta eroare stationara finita
4. Sa se determine raspunsul sistemului la marimea de intrare treapta unitara si sa se reprezinte grafic

---

1. 
$$\begin{align} & k=1 \implies \begin{cases}G_{d}(s)=\frac{1}{s+5} \\G(s)=\frac{Y(s)}{U(s)}\end{cases} \\&\implies sY(s)+3Y(s)=U(s) \bigg| \mathcal{L}^{-1} \\& \implies\frac{dY(t)}{dt}+5Y(t)=U(t) \\&\implies \frac{Y[k]-Y[k-1]}{T_{e}}+5Y[k]=U[k] \\& \implies \frac{Y(z)-z^{-1}Y(z)}{T_{e}}+5Y(z)=U(z) \\& \implies Y(z) - z^{-1}Y(z)+5 T_{e }Y(z)= T_{e}U(z) \\&\implies Y(z)(1-z^{-1}+5T_{e}) = T_{e} U(z) \\& \implies G_{d}(z) = \frac{Y(z)}{U(z)}=\frac{T_{e}}{1+5T_{e}-z^{-1}} \\&\implies \frac{Y(z)}{U(z)}= \frac{T_{e}z}{(1+5T_{e})z-1} \\& G_{0}(z)=\frac{G_{d}(z)}{1+G_{d}(z)} = \frac{\frac{T_{e}z}{(1+5T_{e})z-1}}{1- \frac{T_{e}z}{(1+5T_{e})z-1}} \\& = \frac{T_{e}z}{(1+5T_{e})z-1+T_{e}z}=\frac{T_{e}z}{(1+6T_{e})z-1}\end{align}$$
```tikz
\begin{document}
		\begin{tikzpicture}
			\draw[thick,->] (0,6) -- (2,6) node[above left] {$R(s)$};
			\draw [thick] (2.3,6) circle (0.3cm);
			\def\centerX{2.3} 
			\def\centerY{6} 
			\def\radius{0.2}
			\draw[thick] (\centerX - \radius, \centerY - \radius) -- (\centerX + \radius, \centerY + \radius);
			 \draw[thick] (\centerX - \radius, \centerY + \radius) -- (\centerX + \radius, \centerY - \radius);
			 \draw[thick] (2.6,6) -- (3.8,6);
			 \draw[thick] (3.85,6) circle (0.05cm);
			 \draw[thick] (3.9,6) -- (4.4,6.2);
			 \draw[thick] (4.45,6) circle (0.05cm);
			 \draw[thick,->] (4.1,6.3) .. controls (4.2,6.1) and (4.2,5.9)  .. (4.1, 5.7);
			 \draw[thick] (4.5,6) -- (6,6);
			 \draw[thick] (6,6.5) -- (8,6.5) -- (8,5.5) -- (6,5.5) -- (6,6.5);
			 \node at (7,6) {$G_{pc}$};
			 \draw [thick] (8,6) -- (10,6);
			 \draw [thick] (10.1,6) circle (0.1);
			 \draw [thick,->] (10.2,6) -- (12,6)node[above] {$Y$};
			 \draw [thick,->] (10.1,5.9) .. controls (10.1,4) and (2.3,4) .. (2.3,5.7);
			 \node at (2.7,5.7) {$-$};
		\end{tikzpicture}
	\end{document}
	```

```tikz
\begin{document}
	\begin{tikzpicture}
		\draw[->, thick] (0,0) -- (1,0) node [above left] {$R$};
		\draw[thick] (1,0) -- (2.9,0);
		\draw[thick] (3,0) circle (0.1) node [above] {$E=x_1$};
		\draw [thick, ->]  (3.1,0) -- (4.1,0);
		\draw [thick] (4.1,0) -- (5,0);
		\draw [thick] (5.05,0) circle (0.05);
		\draw [thick] (5.65,0) circle (0.05);
		\draw [thick , ->] (5.3,0.5) .. controls (5.4, 0.25) and (5.4, -0.25) .. (5.3,-0.5) node [below] {$T_e$};
		\draw [thick] (5.1,0) -- (5.7,0.4) node [above left] {$E_i$};
		\draw [thick] (5.7,0) -- (7.7,0);
		\draw [thick] (7.8,0) circle (0.1) node [above] {$E^{*}=x_2$};
		\draw [thick, ->] (7.9,0) -- (10,0) node[above] {$G_{PC}(s)$};
		\draw [thick] (10,0) -- (11.9,0);
		\draw [thick] (12,0) circle (0.1) node [above] {$Y=x_3$};
		\draw [thick, ->] (12,-0.1) .. controls (10, -2) .. (7.5,-2) node [below right] {$-1$};
		\draw [thick] (7.5,-2) .. controls (5,-2) .. (3, -0.1) node [right] {$-$};  	
	\end{tikzpicture}
\end{document}
```

$$\begin{align}
& \begin{cases}
x_{1}=R- 1 \cdot Y=R-x_{3} \\ 
x_{2}=E^{*}=x_{1}^{*}  \\
x_{3}=G_{PC}\cdot x_{2} = G_{PC} \cdot x_{1}^{*}
\end{cases} \\
& \begin{cases}
x_{1}= R-G_{PC} \cdot x_{1}^{*} \\
x_{2} = x_{1}^{*} \\
x_{3} = G_{PC} \cdot x_{1}^{*}
\end{cases} \Bigg|^{*} \implies \\
& \begin{cases}
x_{1}^{*} = R^{*} - G_{PC}^{*} \cdot x_{1}^{*} \\
x_{2}^{*} = x_{1}^{*} \\
x_{3}^{*} = G_{PC}^{*} \cdot x_{1}^{*}
\end{cases}
\end{align}$$

```tikz
\begin{document}
	\begin{tikzpicture}
		\draw (0,0) circle (0.01) node[above] {$R^*$}; 	
		\draw[thick] (0,0) -- (2,0);
		\draw[thick] (2.1,0) circle (0.1) node [above right] {$x_1^*$};
		\draw [thick,->] (2.1,-0.1) ..controls (3,-1) and (1,-0.8) .. (2.1,-0.1) node [below right] {$-G_{PC}^*$};
		\draw [thick, ->](2.2, 0) -- (3.4,0) node [above] {$1$};
		\draw [thick] (3.4,0) -- (4.4,0);
		\draw[thick] (4.5,0) circle (0.1) node [above right] {$x_2^*$};
		\draw [thick,->](4.6,0) -- (5.6,0) node[above right] {$G_{PC}^*$};
		\draw [thick] (5.6,0) -- (6.6,0);
		\draw [thick](6.7,0) circle (0.1) node[ above right] {$x_3^*$};
	\end{tikzpicture}
\end{document}
```
 

3. 
$$\begin{align}& G_{e}(z)=\frac{G_{pc}(z)}{1+G_{pc}(z)} \\& G_{PC}(z)=Z\left\{ \frac{1-e^{-sT_{e}}}{s} \cdot \frac{1}{s+5}\right\} \\&= 1-z^{-1}z\left\{ \frac{1}{s(s+5)} \right\} \\&=\frac{z-1}{z}\cdot z \left\{ \frac{c_{1}}{s} + \frac{c_{2}}{s+5} \right\} \\&\implies \frac{c_{1}}{s}+\frac{c_{2}}{s+5}=\frac{1}{s(s+5)} \\& \implies sc_{1}+5c_{1}+sc_{2}=1 \\& \implies \begin{cases}c_{1}+c_{2}=0 \\5c_{1}=1\implies c_{1}=c_{2}=\frac{1}{5}\end{cases}  \\& \implies \frac{z-1}{z} \left\{ \frac{\frac{1}{5}}{s} - \frac{\frac{1}{5}}{s+5}\right\} \\&= \frac{z-1}{z}\left( \frac{1}{5}\cdot \frac{z}{z-1}-\frac{1}{5 \cdot z-e^{-5T_{e}}} \right) \\& =\frac{1}{5}(z-1)\left( \frac{1}{z-1}-\frac{1}{z-e^{-5T_{e}}} \right) \\& = \frac{1}{5}(z-1) \frac{\cancel{z}-e^{-5T_{e}}\cancel{-z}+1}{(\cancel{z}-1)(z-e^{-5T_{e}})} \\& = -\frac{e^{-5T_{e}}+1}{5(z-e^{-5T_{e}})}\end{align}$$
4. 
$$\begin{align}& T_{e}=1s \implies C_{p}(z)=\frac{1}{5z+0.03} \\& \implies G_{e}(z) =\frac{\frac{1}{5z+0.03}}{1+\frac{1}{5z+0.03}} = \frac{1}{5z+1.03} \\& Y(z)=\frac{z}{(5z+1.03)(z-1)}=\frac{z}{5z^{2}-3.97z-1.03}\bigg|\cdot z^{-2} \\& Y(z^{-1})= \frac{z^{-1}}{5-3.97z^{-1}-1.03z^{-2}}\end{align}$$ Se efectueaza impartirea polinomiala si se ajunge la rezultatul:$$Y(kT_{e})=(0;0.2;0.158;0.29;\dots)$$
```tikz
\begin{document}
	\begin{tikzpicture}
		\draw[thick,->] (0,0) -- (12,0) node [above] {$t$};
		\draw[thick,->](0,0) -- (0,8) node[left] {$Y(t)$};
		\draw[thick] (2,0) -- (2,1) -- (4,1) -- (4,0);
		\draw[thick] (4,0) -- (4,2) -- (6,2) -- (6,0);
	 	\draw[thick] (6,0) -- (6,4) -- (8,4) -- (8,0);
		\draw[thick] (8,0) -- (8,6) -- (10,6) -- (10,0);
		\draw[thick,dotted] (0,7) -- (12,7) node[xshift= -12.5 cm] {$-1$};
 	\end{tikzpicture}
\end{document}
```

#### Exercitiul 2
Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):
$$G_{d}(z)=\frac{0.13z+0.02}{z^{2}-0.39z+0.007}$$
1. Sa se determine partea reala si partea imaginara
2. Sa se determine punctul de unde pleaca curba polara si punctul de unde se termina curba polara
3. Sa se determine cum este sistemul in circuit deschis (argumentati)
4. Sa se determine cum este sistemul in circuit inchis (argumentati)

---

1. 
$$\begin{align}& T_{e}=1s \\& \begin{cases}G_{d}(s)= \frac{0.13z+0.02}{z^{2}-0.392z+0.007} \\z=\frac{1+ \frac{T_{e}}{2}\omega}{1- \frac{T_{e}}{2}\omega} = \frac{1+0.5\omega}{1-0.5\omega}\end{cases} \implies \\& \implies G_{d}(\omega)= \frac{\frac{0.13(1+0.5\omega)}{1-0.5\omega}+0.02}{\left( \frac{1+0.5\omega}{1-0.5\omega} \right)^{2}-0.39 \frac{1+0.5\omega}{1-0.5\omega}+0.007} \\& = \frac{\frac{0.13+0.065\omega+0.02-0.01\omega}{1-0.5\omega}}{\frac{1+\omega+o.25\omega^{2}-0.39+0.0975\omega^{2}+0.007-0.007\omega+0.0175\omega^{2}}{(1-0.5\omega)^{2}}} \\& = \frac{(0.055\omega+0.15)(1-0.5\omega)}{o.365\omega^{2}+0.993\omega+0.617} \\&= \frac{-0.0275\omega^{2}-0.02+0.15}{0.365\omega^{2}+0.993\omega+0.617} \\& \omega \to j \omega \implies  \\&\implies G(j\omega)= \frac{0.0275\omega^{2}-0.02j\omega+0.15}{  0.615-0.993j\omega-0.365\omega^{2}} \\& =\frac{(0.615-0.993j\omega+0.365\omega^{2})(0.0275\omega^{2}-0.02j\omega+0.15)}{(0.615-0.365\omega^{2})+ 0.993\omega^{2}}  \\& \frac{0.017\omega^{2}-0.0123j\omega+0.092-0.01\omega^{4}+0.075j\omega^{3}-0.054\omega^{2}-0.027j\omega^{3}-0.019\omega^{2}-0.15j\omega}{0.378 - 0.45\omega^{2}+0.13\omega^{4}+0.993\omega^{2}} \\& = \frac{-0.01\omega^{4}-0.056\omega^{2}+0.092}{0.13\omega^{4}+0.543\omega^{2}+0.378}+j \frac{0.046\omega^{3}-0.162\omega}{0.13\omega^{4}+0.543\omega^{2}+0.378} \\&\implies \begin{cases}\mathrm{Re}\{G(j\omega)\}=\frac{-0.01\omega^{4}-0.056\omega^{2}+0.092}{0.13\omega^{4}+0.543\omega^{2}+0.378} \\Im\{G(j\omega)\}=\frac{0.046\omega^{3}-0.162\omega}{0.13\omega^{4}+0.543\omega^{2}+0.378}\end{cases}\end{align}$$
2. 
$$\begin{align}& Im=0 \implies Re=\frac{0.092}{0.378}=0.243 \\& \lim_{ \omega \to \infty } Re\{G(j\omega)\} = -0.076 \\& \lim_{ \omega \to \infty } Im\{G(j\omega)\} = 0 \end{align}$$
	```tikz
	\begin{document}
		\begin{tikzpicture}
			\draw [thick,->] (-2.25,0) -- (2.25,0) node[above] {$Re$};
			\draw [thick,->] (0,-2.25) -- (0,2.25) node[above] {$Im$};
			\draw (-0.34125,0) circle (0.70875);
			\draw (-1.05,0) circle (0.05) node [yshift= -0.3cm, xshift= -0.5cm] {$-0.7$};
			\draw (0.3675,0) circle (0.05) node [yshift= -0.3cm, xshift= 0.5cm] {$0.245$};
	 	\end{tikzpicture}
	\end{document}
	```

3. 
$$\begin{align}& \begin{cases}z_{0}=-0.1538 \\p_{1}=0.37 \\p_{2}=0.019\end{cases}\end{align}$$ $\implies$ Sistemul in circuit deschis este stabil deoarece modulul polilor si zerourilor este $<1$
 4. Sistemul in circuit deschis este stabil deoarece caracteristica polara nu inconjoara punctul $(-1,0)$

#### Exercitiul 3
Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):
$$G_{d}(s)=k \frac{0.16z+0.04}{z^{2}-0.42z+0.02}$$
Determinati:
1. Numarul de ramuri ale locului radacinilor, de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care il fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc

---
1. 
$$\begin{align}& G_{d}(z)=\frac{k(0.16z+0.04)}{z^{2}-0.42z+0.02} \\& n=2 - \text{ 2 ramuri} \\& m=1 \\& n-m=1 \implies \begin{cases}\text{o ramura }\to \infty \\\text{o ramura se duce in zero}\end{cases}\end{align}$$
2. 
$$\begin{align}& z=-0.25 \\& p_{1}=0.36 \\& p_{2} = 0.05\end{align}$$
	```tikz
	\begin{document}
			\begin{tikzpicture}
			\draw [->] (-4,0) -- (3,0);
			\draw [->] (0,-2) -- (0,2);
			\draw [thick] (-4,0) -- (-1,0);
			\draw [thick] (0.2,0) -- (1.44,0);
			\draw (-1,0) circle (0.05) node[above] {$-0.25$};
			\draw (0.2,0) circle (0.05) node [above] {$0.05$};
			\draw (1.44,0) circle (0.05) node [above] {$0.36$};
		 	\end{tikzpicture}
		\end{document}
	```
	$$\implies (-\infty,0.25] \cup [0.05;0.36]$$
3. 
$$\begin{align}& n-m=1 \implies \text{o asimptota} \\&y_{0}=\frac{180\degree}{1}=180\degree \\& T_{a}=\frac{0.41+0.25}{1}=0.66\end{align}$$
4. 
$$\begin{align}& G(z)=k \frac{0.16z+0.04}{z^{2}-0.42z+0.02} \\& 1+G(z)=0 \\& \implies k=-\frac{z^{2}-0.42z+0.02}{0.16z+0.04} \\&\frac{dk}{dz}=0 \implies \\& \frac{-(2z-0.42)(0.16z+0.04)+0.16(z^{2}-0.42z+0.02)}{(0.16z+0.04)^{2}}=0 \\&\implies \frac{-0.32z^{2}- 0.012z + 0.017+ 0.16z^{2}-0.067+0.003}{(0.16z+0.04)^{2}} \\& \implies \frac{-0.16z^{2}-0.08z+0.014}{(0.16z+0.04)^{2}}=0\implies \begin{cases}z_{1}=-0.63 \\z_{2}=0.13\end{cases} \\&\implies p_{e}: \begin{cases}(-0.63,0) \\(0.13,0)\end{cases}\end{align}$$
5. 
$$\begin{align}& \begin{cases}G_{d}(z)= \frac{0.16z+0.04}{z^{2}-0.42z+0.02} \\z=x+jy\end{cases}\implies \\& \implies G_{d}(z+jy)= \frac{0.16(x+jy)+0.04}{(x+jy)^{2}-0.42(x+jy)+0.02} \\& \implies \frac{0.16x+0.16jy+0.04}{x^{2}+2xjy-y^{2}-0.42x-0.42jy+0.02} \\& \angle G(s)=(2k+1) 180\degree \implies \\&\angle G(s)=\arctan \frac{\cancel{0.16}y}{\cancel{0.16}(x+0.25)}-\arctan \frac{2xy-0.42y}{x^{2}-y^{2}-0.42x+0.02} \\ & = (2k+1) \cdot 180\degree \bigg|\tan \implies  \\& \implies \frac{\frac{y}{x+0.25}- \frac{2xy-0.42y}{x^{2}-y^{2}-0.42x+0.02}}{1+\frac{y}{x+0.25} \cdot \frac{2xy-0.42y}{x^{2}-y^{2}-0.42x+0.02}}=0 \\&\implies \frac{y}{x+0.25}= \frac{2xy-0.42y}{x^{2}-y^{2}-0.42x+0.02} \\& \implies x^{2}-y^{2}-0.42x +0.02=2x^{2}+0.08x-0.105 \\ & x^{2}+0.5x+0.625+y^{2}=0.125+0.0625 \\& (x+0.25)^{2}+y^{2}=(\sqrt{ 0.433 })^{2} \implies \\& \implies C=(-0.25;0); R=0.433\implies \text{descrie un arc}\end{align}$$
#### Exercitiul 4
Se considera functia de transfer a sistemului in circuit inchis:
$$G_{0}(z)= \frac{0.01z+0.01}{z^{2}-1.52z+0.54}$$
1. Sa se determine modelul cu variabile de stare in forma complet controlabila (demonstratie)
2. Plecand de la modelul cu variabile de stare (matricele sistemului) sa se determine daca sistemul este controlabil

---
1. 
$$\begin{align}& G_{0}(z)= \frac{(0.01z+0.01)^{2}}{z^{2}-1.5z+0.54} \\& \implies G_{0}(z)=\frac{Y(z)}{U(z)}= \frac{Y(z)}{X(z)} \cdot \frac{X(z)}{U(z)} \\& \frac{Y(z)}{X(z)}= 0.01z+0.01 \\& \frac{X(z)}{U(z)} = \frac{1}{z^{2}-1.5z+0.54} \\&\implies z^{2}X(z)-1.5z X(z)+0.54X(z)=U(z) \bigg|z^{-1} \\& \implies X[k+2]-1.52X[k+1]+0.54X[k]=U[k] \\&\implies \begin{cases}X_{1}[k]=X[k] \\X_{2}[k]=X[k+1]=X_{1}[k+1] \\X_{2}[k+1]=1.52X_{2}[k]-0.54X_{1}[k]+U[k]\end{cases} \\& \phi= \begin{bmatrix}0 & 1 \\-0.54 & 1.52 \\\end{bmatrix} ; \Gamma= \begin{bmatrix}0 \\1\end{bmatrix} \\& \frac{Y(z)}{X(z)}=0.01z+0.01\implies \\& \implies Y(z)=0.01zX(z)+0.01X(z)\bigg|z^{-1} \\& \implies Y[k]=0.01X[k+1]+0.01X[k] \\& C = \begin{bmatrix}0.01 & 0.01\end{bmatrix} \\& D=0\end{align}$$
2. Controlabilitatea: $$\begin{align}&P= [\Gamma \cdot \phi \Gamma] \\& \phi \cdot \Gamma = \begin{bmatrix}0 & 1 \\-0.54 & 1.52\end{bmatrix} \begin{bmatrix}0 \\1\end{bmatrix} = \begin{bmatrix}1 \\1.52\end{bmatrix} \\& \implies P=\begin{bmatrix}0 & 1 \\1 & 1.52\end{bmatrix}  \\&\implies \det P= \begin{vmatrix}0 & 1 \\1 & 1.52\end{vmatrix}=-1 \neq 0 \\& \implies \text{Controlabila}\end{align}$$
### Bilet bejenaru
#### Exercitiul 1
Se considera un sistem discret cu reactie negativa unitara in care partea continua are urmatoarea forma:
$$G_{PC}(s)=\frac{k}{s+4}$$
1. Pentru $k=1$, sa se determine functia de transfer a sistemului in circuit inchis plecand de la ecuatia cu diferente
2. Folosind graful de fluenta sa se determine functia de transfer a sistemului in circuit inchis
3. Sa se determine pentru ce tip de intrare sistemul prezinta eroare stationara finita
4. Sa se determine raspunsul sistemului la marimea de intrare treapta unitara si sa se reprezinte grafic
---
1. 
$$\begin{align}& Y(s)=GU(s)\implies Y(s)=\frac{1}{s+4} \cdot U(s) \\&\implies 3Y(s)+4Y(s)=U(s) \bigg|\mathcal{L}^{-1} \\& \implies \frac{dY(t)}{dt}+4Y(t)=U(t) \\& \implies \frac{Y[k]-Y[k-1]}{T_{e}}+4Y[k]=U[k] \\&(T_{e}=1)\implies Y[k]-Y[k-1]+Y[k-1]=U[k] \bigg|z^{-1} \\&\implies 5Y(z)- \frac{1}{Y(z)}=U(z) \\& \implies G_{0}(z)=\frac{Y(z)}{U(z)}=\frac{z}{z-5} \end{align}$$
2. 
```tikz
\begin{document}
	\begin{tikzpicture}
		\draw[->, thick] (0,0) -- (1,0) node [above left] {$R$};
		\draw[thick] (1,0) -- (2.9,0);
		\draw[thick] (3,0) circle (0.1) node [above] {$E=x_1$};
		\draw [thick, ->]  (3.1,0) -- (4.1,0);
		\draw [thick] (4.1,0) -- (5,0);
		\draw [thick] (5.05,0) circle (0.05);
		\draw [thick] (5.65,0) circle (0.05);
		\draw [thick , ->] (5.3,0.5) .. controls (5.4, 0.25) and (5.4, -0.25) .. (5.3,-0.5) node [below] {$T_e$};
		\draw [thick] (5.1,0) -- (5.7,0.4) node [above left] {$E_i$};
		\draw [thick] (5.7,0) -- (7.7,0);
		\draw [thick] (7.8,0) circle (0.1) node [above] {$E^{*}=x_2$};
		\draw [thick, ->] (7.9,0) -- (10,0) node[above] {$G$};
		\draw [thick] (10,0) -- (11.9,0);
		\draw [thick] (12,0) circle (0.1) node [above] {$Y=x_3$};
		\draw [thick, ->] (12,-0.1) .. controls (10, -2) .. (7.5,-2) node [below right] {$-1$};
		\draw [thick] (7.5,-2) .. controls (5,-2) .. (3, -0.1) node [right] {$-$};  	
	\end{tikzpicture}
\end{document}
```
$$\begin{align}
&\begin{cases}
x_{1}=R-Y \\
x_{2}=E^{*}=x_{1}^{*} \\
x_{3}=Y=G \cdot x_{2}= G \cdot x_{1}^{*} \\
\end{cases} \\
&\begin{cases}
x_{1}=R-G^{*}x_{1}^{*} \\
x_{2}=x_{1}^{*} \\
x_{3}=Gx_{1}^{*}
\end{cases} \Bigg|^{*} \implies \\
& \begin{cases}
x_{1}^{*}=R^{*}-G^{*}x_{1}^{*} \\
x_{2}^{*}= x_{1}^{*} \\
x_{3}^{*}= G^{*} x_{1}^{*}
\end{cases}
\end{align}$$
```tikz
\begin{document}
	\begin{tikzpicture}
		\draw (0,0) circle (0.01) node[above] {$R^*$}; 	
		\draw[thick] (0,0) -- (2,0);
		\draw[thick] (2.1,0) circle (0.1) node [above right] {$x_1^*$};
		\draw [thick,->] (2.1,-0.1) ..controls (3,-1) and (1,-0.8) .. (2.1,-0.1) node [below right] {$-G^*$};
		\draw [thick, ->](2.2, 0) -- (3.4,0) node [above] {$1$};
		\draw [thick] (3.4,0) -- (4.4,0);
		\draw[thick] (4.5,0) circle (0.1) node [above right] {$x_2^*$};
		\draw [thick,->](4.6,0) -- (5.6,0) node[above right] {$G^*$};
		\draw [thick] (5.6,0) -- (6.6,0);
		\draw [thick](6.7,0) circle (0.1) node[ above right] {$x_3^*=Y^*$};
	\end{tikzpicture}
\end{document}
```
$$G_{e}(z)=\frac{Y^{*}(s)}{R^{*}(s)}=\frac{G^{*}}{1+G^{*}}$$
3. 
$$\begin{align}& G_{d}(z)= \frac{z}{z-e^{-4}}=\frac{z}{z-0.01} \\& e^{*'}_{st}= \frac{1}{1+K_{p}^{*}}=\frac{1}{2}=0.5 \\& K_{p}^{*}=\lim_{ z \to 1 }=\frac{1}{0.99}=1.01 \approx 1 \\ \end{align}$$ Sistemul prezinta eroare stationara la intrare treapta
4. 
$$\begin{align}
& Y(z)=G_{0}(z) \cdot R(z) = \frac{z}{z-5} \cdot \frac{z}{z-1}=\frac{z^{2}}{z^{2}-6z+5} \bigg|\cdot z^{-2} \\
& Y(z^{-1})=\frac{1}{1-6z^{-1}+5z^{-2}}
\end{align}$$
 Se efectueaza impartirea polinomiala si se ajunge la rezultatul
```tikz
\begin{document}
	\begin{tikzpicture}
		\draw[thick,->] (0,0) -- (12,0) node [above] {$t$};
		\draw[thick,->](0,0) -- (0,8) node[left] {$Y(t)$};
		\draw[thick] (2,0) -- (2,1) -- (4,1) -- (4,0);
		\draw[thick] (4,0) -- (4,2) -- (6,2) -- (6,0);
	 	\draw[thick] (6,0) -- (6,4) -- (8,4) -- (8,0);
		\draw[thick] (8,0) -- (8,6) -- (10,6) -- (10,0);
		\draw[thick,dotted] (0,7) -- (12,7) node[xshift= -12.5 cm] {$-1$};
 	\end{tikzpicture}
\end{document}
```

#### Exercitiul 2
Se considera un sistem cu reactie negativa unitara, in care functia de transfer in circuit deschis este de urmatoarea forma ($T_{e}=1s$):
$$G_{d}(z)=\frac{0.2z+0.7}{z^{2}-0.5z+0.05}$$
1. Sa se determine partea reala si partea imaginara
2. Punctul de unde pleaca curba polara si punctul unde se termina curba polara
3. Cum este sistemul in circuit deschis (argumentati)
4. Cum este sistemul in circuit inchis (argumentati)

---

$$\begin{align}
& G_{d}(z)=\frac{0.2z+0.7}{z^{2}-0.5z+0.05} \\
& z= \frac{1+\frac{T_{e}}{2}\omega}{1-\frac{T_{e}}{2}\omega}=\frac{1+0.5\omega}{1-0.5\omega} \\
& G_{d}(\omega)= \frac{0.2\frac{1+0.5\omega}{1-0.5\omega}+0.7}{\left( \frac{1+0.5\omega}{1-0.5\omega} \right)^{2}-0.5\frac{1+0.5\omega}{1-0.5\omega}+0.05} \\
& = \frac{\frac{0.2(1+0.5\omega)+0.7(1-0.5\omega)}{1-0.5\omega}}{\frac{(1+0.5\omega)^{2}+0.5(1+0.5\omega)(1-0.5\omega)+0.05(1-0.5\omega)^{2}}{(1-0.5\omega)^{2}}} \\
& = \frac{(1-0.5\omega)(0.2+0.1\omega+0.7-0.35\omega)}{1-\omega+0.25\omega^{2}+0.5(1-\cancel{0.5\omega}+ \cancel{0.5\omega}-0.25\omega^{2})+0.05(1-\omega+0.25\omega^{2})} \\
&= \frac{(1-0.5\omega)(0.9-0.25\omega)}{1-\omega+0.24\omega^{2}+0.5-0.25\omega^{2}+0.05-0.05\omega+0.0125\omega^{2}}  \\
& = \frac{0.9-0.25\omega-0.45\omega+0.125\omega^{2}}{0.1375\omega^{2}-1.05\omega+1.05} \\
& = \frac{0.125\omega^{2}-0.7\omega+0.9}{0.1375\omega^{2}-1.05\omega+1.05} \\
& \omega\to j\omega \\
& G(j\omega)=\frac{-0.125\omega^{2}-0.7j\omega+0.9}{-0.1375\omega^{2}-1.05j\omega+1.05} \\
& = \frac{-0.7j\omega+(0.9-0.125\omega^{2})}{-1.05j\omega+(1.05-0.1375\omega^{2})}  \\
& = \dots
\end{align}$$



#### Exercitiul 3
Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):
$$G_{d}(z)=k \frac{0.13z+0.02}{z^{2}-0.39z+0.007}$$
Determinati:
1. Numarul de ramuri ale locului radacinilor, de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care il fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc

---

#### Exercitiul 4
Se considera functia de transfer a unui sistem in circuit inchis:
$$G_{0}(z)=\frac{0.02z+0.01}{z^{2}-1.51z+0.54}$$
1. Sa se determine modelul cu variabile de stare in forma complet controlabila (demonstratie)
2. Plecand de la modelul cu variabile de stare (matricea sistemului) sa se determine daca sistemul este controlabil

---

1. 
$$\begin{align}& \frac{Y(z)}{X(z)}= 0.02z+0.01 \\& \frac{X(z)}{U(z)}= \frac{1}{z^{2}-1.51z+0.54} \\&  z^{2}\cdot X(z)-1.51zX(z)+0.54X(z)=U(z) \bigg|z^{-1} \\& \implies X[k+2]-1.51X[k+1]+0.54X[k]=U[k] \\&\implies \begin{cases}X_{1}[k]=X[k] \\X_{2}[k]=X[k+1]=X_{1}[k+1] \\X_{2}[k+1]=X[k+2]=1.41X[k+1]-0.54X[k]+U[k] \\X[k+2]= 1.51X_{2}[k]-0.54X_{1}[k]+U[k]\end{cases}  \\& \phi = \begin{bmatrix}0 & 1 \\-0.54 & 1.51\end{bmatrix}; \Gamma=\begin{bmatrix}0 \\1\end{bmatrix} \\& Y(z)=0.02zX(z)+0.01X(z)\bigg|z^{-1} \\& Y[k]=0.02X[k+1]+0.01X[k] \\& =0.2 X_{2}[k]+0.01X_{1}[k] \\& \implies C=[0.01 \quad 0.02] \\& D=0\end{align}$$
2. 
$$\begin{align}& P= \begin{bmatrix}\Gamma & \phi\Gamma
\end{bmatrix} \\&\phi\Gamma= \begin{bmatrix}0 & 1 \\1 & 1.51\end{bmatrix} \begin{bmatrix}0  \\1\end{bmatrix}=\begin{bmatrix}1 \\1.51
\end{bmatrix} \\& P= \begin{bmatrix}0 & 1 \\1 & 1.51\end{bmatrix}, \det P=-1 \neq 0 \\ &\implies \text{ sistemul este controlabil}\end{align}$$
 
### Bilet maier
#### Exercitiul 1
Se considera un sistem discret cu reactie negativa unitara in care partea continua are urmatoarea forma:
$$G_{PC}(s)=\frac{k}{s+5}$$
1. Pentru $k=0.1$, sa se determine functia de transfer a sistemului in circuit inchhis plecand de la ecuatia cu diferente
2. Folosind graful de fluenta sa se determine functia de transfer a sistemului in circuit inchis
3. Sa se determine pentru ce tip de intrare sistemul prezinta eroare stationara finita
4. Sa se determine raspunsul sistemului la marimea de intrare treapta unitara si sa se reprezinte grafic

---

1. 
$$\begin{align}& k=0.1 \implies G_{PC}(s)=\frac{0.1}{s+5}=\frac{Y(s)}{U(s)} \\& \implies U(s)=10sY(s)+50Y(s)\bigg|\mathcal{L}^{-1} \\& \implies 10 \frac{dY(t)}{dt}+50Y(t)=U(t) \\&\implies 10 \frac{Y(k)-T[k-1]}{T_{e}}+ 50Y[k]=U[k] \\&\implies 10(Y[k]-Y[k-1])+50T_{e}Y[k]=T_{e}U[k] \\& \implies  10 Y[k](10+50T_{e})-10Y[k-1]=T_{e}U[k]\bigg|Z \\& \implies 10Y(z)(10+50T_{e})-10z^{-1}Y(z)=T_{e}U(z) \\& \implies 10Y(z)(10+50T_{e}-10z^{-1})=T_{e}U(z) \\& \implies \frac{Y(z)}{U(z)}=\frac{T_{e}}{1+5T_{e}-z^{-1}}=\frac{zT_{e}}{z+5T_{e}z-1} \\& G_{0}(z) = \frac{G_{PC}(z)}{1+G_{PC}(z)}=\frac{\frac{zT_{e}}{z+5T_{e}z-1}}{1+\frac{zT_{e}}{z+5T_{e}z-1}}=\frac{T_{e }z}{z(1+5T_{e})-1}\end{align}$$
2.  
	```tikz
	\begin{document}
		\begin{tikzpicture}
			\draw[->, thick] (0,0) -- (1,0) node [above left] {$R$};
			\draw[thick] (1,0) -- (2.9,0);
			\draw[thick] (3,0) circle (0.1) node [above] {$E=x_1$};
			\draw [thick, ->]  (3.1,0) -- (4.1,0);
			\draw [thick] (4.1,0) -- (5,0);
			\draw [thick] (5.05,0) circle (0.05);
			\draw [thick] (5.65,0) circle (0.05);
			\draw [thick , ->] (5.3,0.5) .. controls (5.4, 0.25) and (5.4, -0.25) .. (5.3,-0.5) node [below] {$T_e$};
			\draw [thick] (5.1,0) -- (5.7,0.4) node [above left] {$E_i$};
			\draw [thick] (5.7,0) -- (7.7,0);
			\draw [thick] (7.8,0) circle (0.1) node [above] {$E^{*}=x_2$};
			\draw [thick, ->] (7.9,0) -- (10,0) node[above] {$ERO \cdot G_{PC}$};
			\draw [thick] (10,0) -- (11.9,0);
			\draw [thick] (12,0) circle (0.1) node [above] {$Y=x_3$};
			\draw [thick, ->] (12,-0.1) .. controls (10, -2) .. (7.5,-2) node [below right] {$-1$};
			\draw [thick] (7.5,-2) .. controls (5,-2) .. (3, -0.1) node [right] {$-$};  	
		\end{tikzpicture}
	\end{document}
	```

$$\begin{align}
&\begin{cases}
x_{1}=E=R-Y=R-x_{3} \\
x_{2}=E^{*}=x_{1}^{*} \\
x_{3}=Y=G \cdot x_{2}= G \cdot x_{1}^{*} \\
\end{cases} \\
&\begin{cases}
x_{1}=R-ERO \cdot G \cdot x_{1}^{*} \\
x_{2}=x_{1}^{*} \\
x_{3}=ERO \cdot Gx_{1}^{*}
\end{cases} \Bigg|^{*} \implies \\
& \begin{cases}
x_{1}^{*}=R^{*}-(ERO \cdot G)^{*}x_{1}^{*} \\
x_{2}^{*}= x_{1}^{*} \\
x_{3}^{*}= (ERO \cdot G)^{*} x_{1}^{*}
\end{cases}
\end{align}$$

```tikz
\begin{document}
	\begin{tikzpicture}
		\draw (0,0) circle (0.01) node[above] {$R^*$}; 	
		\draw[thick] (0,0) -- (2,0);
		\draw[thick] (2.1,0) circle (0.1) node [above right] {$x_1^*$};
		\draw [thick,->] (2.1,-0.1) ..controls (3,-1) and (1,-0.8) .. (2.1,-0.1) node [below right] {$-(ERO \cdot G)^*$};
		\draw [thick, ->](2.2, 0) -- (3.4,0) node [above] {$1$};
		\draw [thick] (3.4,0) -- (4.4,0);
		\draw[thick] (4.5,0) circle (0.1) node [above] {$x_2^*$};
		\draw [thick,->](4.6,0) -- (5.6,0) node[above] {$(ERO \cdot G)^*$};
		\draw [thick] (5.6,0) -- (6.6,0);
		\draw [thick](6.7,0) circle (0.1) node[ above right] {$x_3^*$};
	\end{tikzpicture}
\end{document}
```
$$\begin{align}
& G_{0}(z)= \frac{(ERO \cdot G)^{*}}{1- [-(ERO \cdot G)^{*}]}\Bigg|_{s=\frac{1}{T_{e}}\ln z} = \frac{Z\{ERO \cdot G(s)\}}{1+Z\{ERO \cdot G(s)} \\
& Z\{ERO \cdot G(s)\}=Z \left\{ \frac{1-e^{-sT_{e}}}{s} \cdot \frac{1}{s+5} \right\}= (1-z^{-1}) Z\left\{ \frac{1}{s(s+5)} \right\}  \\
& = (1-z^{-1})Z \left\{ \frac{C_{1}}{s}+\frac{C_{2}}{s+5} \right\} \\ \\
& C_{1}=\frac{1}{s+5}\bigg|_{s=0}=\frac{1}{5} \\
& C_{2}=\frac{1}{s }\bigg|_{s=-5} =-\frac{1}{5} \\
 \\
&\implies G_{p}(z)=\frac{z}{z-1} \cdot Z\left\{ \frac{1}{5} \cdot \frac{1}{s} - \frac{1}{5} \cdot \frac{1}{s+5} \right\} \\
& = \frac{z-1}{z} \cdot Z \left\{ \frac{1}{5} \cdot \frac{z}{z-1} - \frac{1}{5} \cdot \frac{z}{z-e^{-5T_{e}}} \right\} \\
&= \frac{z-1}{5} \cdot \frac{(z-e^{-5T_{e}}-z+1)}{(z-1)(z-e^{-5T_{e}})}, T_{e}=1 \\
& \implies G_{p}=\frac{0.2(-e^{-5}+1)}{z-e^{-5}}=\frac{0.2(1-0.006)}{z-0.006}=\frac{0.2}{z-0.006} \\
& \implies G_{0}(z)= \frac{\frac{0.2}{z-0.006}}{1+\frac{0.2}{z-0.006}}=\frac{0.2}{z-0.006+0.2}=\frac{0.2}{z+0.19}
\end{align}$$
3. 
$$\begin{align}& G_{d}(z)=\frac{0.2}{z-0.006} \\& e_{st}^{*}=\lim_{ z \to 1 }(1-z^{-1})\cdot E(z)=\lim_{ z \to 1 } \frac{z-1}{z} \cdot \frac{R(z)}{1+G(z)} \\& R(z)=\frac{z}{z-1} \implies e_{st}^{*'}=\lim_{ z \to 1 } \frac{z-1}{z} \cdot \frac{z}{z-1} \cdot \frac{1}{1+ \frac{0.2}{z-0.006}} \\& = \frac{1}{1+0.2}=\frac{1}{1.2}=0.83  \\&\implies \text{ eroare stationara pentru intrarea treapta unitara} \end{align}$$
4. 
$$\begin{align}& Y(kT_{e})=Z^{-1}\{Y(z)\}=Z^{-1}\{R(z) \cdot G_{0}(z)\} \\& Y(z)=\frac{z}{z-1} \cdot \frac{0.2}{z+0.19} = \frac{0.2z}{z^{2}+0.19z-z-0.19} \\&=\frac{0.2z}{z^{2}-0.8z-0.19}\ \bigg| \cdot z^{-2} \\& \implies Y(z^{-1})= \frac{0.2z^{-1}}{1-0.8z^{-1}-0.19z^{-2}}\\&\dots\end{align}$$
#### Exercitiul 2
Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):
$$G_{d}(z)=\frac{0.56z+0.29}{z^{2}-1.13z+0.13}$$
Determinati:
1. Partea reala si partea imaginara
2. Punctul unde se termina curba polara
3. Cum este sistemul in circuit deschis (argumentati)
4. Cum este sistemul in circuit inchis (argumentati)

---


#### Exercitiul 3
Se considera un sistem cu reactie negativa unitara, in care functia de transfer a sistemului in circuit deschis este de urmatoarea forma ($T_{e}=1s$):
$$G_{d}(z)=k \frac{0.57z+0.29}{z^{2}-1.13z+0.13}$$
Determinati:
1. Numarul de ramuri ale locului radacinilor; de unde incep ramurile si unde se termina
2. Portiunea de pe axa reala care apartine locului radacinilor
3. Numarul de asimptote, unghiul pe care il fac cu axa reala si punctul unde se intalnesc pe axa reala
4. Punctele de ramificatie
5. Verificati daca locul radacinilor descrie un cerc

---


#### Exercitiul 4
Se considera functia de transfer a unui sistem in circuit inchis:
$$G_{0}(z)=\frac{0.02z}{z^{2}-1.49z+0.54}$$
1. Sa se determine modelul cu variabile de stare in forma complet controlabila (demonstratie)
2. Sa se determine matricea fundamentala a sistemului

---


