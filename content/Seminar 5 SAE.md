---
tags:
  - SistemeAutomateCuEsantionare
---
## Exercițiul 1

Să se verifice că modelul la stare cu matricele:

$$\Phi=\left[\begin{array}{ccc}0 & 1 & 0 \\ 0 & 0 & 1 \\ -a_{0} & -a_{1} & -a_{2}\end{array}\right], \Gamma=\left[\begin{array}{l}0 \\ 0 \\ 1\end{array}\right], \boldsymbol{C}=\left[\begin{array}{lll}b_{0} & b_{1} & b_{2}\end{array}\right]$$

are funcţia de transfer:

$$\frac{Y(s)}{U(s)}=\frac{b_{2} z^{2}+b_{1} z+b_{0}}{z^{3}+a_{2} z^{2}+a_{1} z+a_{0}}$$

---

Funcţia de transfer se deduce conform relaţiei de definiţie $G(z)=\boldsymbol{C}(z \mathbf{I}-\Phi)^{-1} \Gamma$.

În prima etapă se determină matricea :

$$(s \mathbf{I}-\Phi)=\left[\begin{array}{ccc}s & -1 & 0 \\ 0 & s & -1 \\ a_{0} & a_{1} & s+a_{2}\end{array}\right]$$

şi apoi se scrie matricea transpusă:

$$(s \mathbf{I}-\boldsymbol{\Phi})^{\top}=\left[\begin{array}{ccc}s & 0 & a_{0} \\ -1 & s & a_{1} \\ 0 & -1 & s+a_{2}\end{array}\right]$$

Se calculează :

$$
\begin{align}
& \operatorname{det}(z \mathbf{I}-\Phi)=z\left[\begin{array}{cc}z & -1 \\ a_{1} & z+a_{2}\end{array}\right]+1 \cdot\left[\begin{array}{cc}0 & -1 \\ a_{0} & z+a_{2}\end{array}\right]=z\left[z\left(z+a_{2}\right)+a_{1}\right]+a_{0} \\
& \operatorname{det}(z \mathbf{I}-\Phi)=z^{3}+z^{2} a_{2}+z a_{1}+a_{0}=A(z)
\end{align}
$$

Se determină cofactorii matricei transpuse:

$$
\begin{align}
& c_{11}=(-1)^{2}\left[\begin{array}{cc}z & a_{1} \\ -1 & z+a_{2}\end{array}\right]=z^{2}+a_{2} z+a_{1}, c_{12}=(-1)^{3}\left[\begin{array}{cc}-1 & a_{1} \\ 0 & z+a_{2}\end{array}\right]=z+a_{2} \\
& c_{13}=(-1)^{4}\left[\begin{array}{cc}-1 & z \\ 0 & -1\end{array}\right]=1, c_{21}=(-1)^{3}\left[\begin{array}{cc}0 & a_{0} \\ -1 & z+a_{2}\end{array}\right]=-a_{0} \\
& c_{22}=(-1)^{4}\left[\begin{array}{cc}z & a_{0} \\ 0 & z+a_{2}\end{array}\right]=z^{2}+a_{2} z, c_{23}=(-1)^{5}\left[\begin{array}{cc}z & 0 \\ 0 & -1\end{array}\right]=z \\
& c_{31}=(-1)^{4}\left[\begin{array}{ll}0 & a_{0} \\ z & a_{1}\end{array}\right]=-a_{0} z, c_{32}=(-1)^{5}\left[\begin{array}{cc}z & a_{0} \\ -1 & a_{1}\end{array}\right]=-a_{1} z+a_{0} \\
& c_{33}=(-1)^{6}\left[\begin{array}{cc}z & 0 \\ -1 & z\end{array}\right]=z^{2}
\end{align}
$$

Având în vedere că :

$$
(z \mathbf{I}-\Phi)^{-1}=\frac{\operatorname{adj}(z \mathbf{I}-\Phi)}{\operatorname{det}(z \mathbf{I}-\Phi)}=\frac{1}{A(z)}\left[\begin{array}{lll}
c_{11} & c_{12} & c_{13} \\
c_{21} & c_{22} & c_{23} \\
c_{31} & c_{32} & c_{33}
\end{array}\right]
$$

se calculează produsul matriceal:

$$
(z \mathbf{I}-\Phi)^{-1} \Gamma=\frac{\operatorname{adj}(z \mathbf{I}-\Phi)}{\operatorname{det}(z \mathbf{I}-\Phi)}=\frac{1}{A(z)}\left[\begin{array}{lll}
c_{11} & c_{12} & c_{13} \\
c_{21} & c_{22} & c_{23} \\
c_{31} & c_{32} & c_{33}
\end{array}\right]\left[\begin{array}{l}
0 \\
0 \\
1
\end{array}\right]=\frac{1}{A(z)}\left[\begin{array}{l}
c_{13} \\
c_{23} \\
c_{33}
\end{array}\right] 
$$

Se înmulţeşte rezultatul, la stânga, cu matricea $\boldsymbol{C}$ şi astfel se obţine:

$$
G(z)=\left[\begin{array}{lll}
b_{0} & b_{1} & b_{2}
\end{array}\right] \frac{1}{A(z)}\left[\begin{array}{c}
1 \\
z \\
z^{2}
\end{array}\right]=\frac{b_{0}+b_{1} z+b_{2} z^{2}}{z^{3}+a_{2} z^{2}+a_{1} z+a_{0}}
$$

adică tocmai funcţia de transfer dată.

## Exercițiul 2

Fie sistemul cu modelul descris de ecuaţia matriceală de stare:

$$
x[k+1]=\left[\begin{array}{ccc}
0 & 1 & 0 \\
0 & 0 & 1 \\
-a_{0} & -a_{1} & -a_{2}
\end{array}\right] \boldsymbol{x}[k]+\left[\begin{array}{l}
0 \\
0 \\
1
\end{array}\right] u[k], y[k]=x_{1}[k]
$$

Să se arate că acest sistem este controlabil.

---

Matricele sistemului sunt

$$
\Phi=\left[\begin{array}{ccc}
0 & 1 & 0 \\
0 & 0 & 1 \\
-a_{0} & -a_{1} & -a_{2}
\end{array}\right] \text {, şi } \Gamma=\left[\begin{array}{l}
0 \\
0 \\
1
\end{array}\right]
$$

deci

$$
\Gamma=\left[\begin{array}{l}
0 \\
0 \\
1
\end{array}\right], \Phi \Gamma=\left[\begin{array}{c}
0 \\
1 \\
-a_{2}
\end{array}\right]
$$

$$
\Phi^{2}=\left[\begin{array}{ccc}0 & 1 & 0 \\ 0 & 0 & 1 \\ -a_{0} & -a_{1} & -a_{2}\end{array}\right]\left[\begin{array}{ccc}0 & 1 & 0 \\ 0 & 0 & 1 \\ -a_{0} & -a_{1} & -a_{2}\end{array}\right]=\left[\begin{array}{ccc}0 & 0 & 1 \\ a_{0} & -a_{1} & -a_{2} \\ a_{0} a_{2} & a_{1} a_{2}-a_{0} & a_{2}^{2}-a_{1}\end{array}\right]
$$

$$
\Phi^{2} \Gamma=\left[\begin{array}{c}1 \\ -a_{2} \\ \left(a_{2}^{2}-a_{1}\right)\end{array}\right]
$$

de unde se obţine matricea de controlabilitate

$$
\boldsymbol{P}=\left[\begin{array}{ccc}0 & 0 & 1 \\ 0 & 1 & -a_{2} \\ 1 & -a_{2} & \left(a_{2}^{2}-a_{1}\right)\end{array}\right]
$$

Deoarece $\operatorname{det} \boldsymbol{P}=1$, rezultă că sistemul este controlabil.

**Soluţie alternativă**

Modelul cu graf de semnal pentru sistemul studiat este prezentat în figura 4.61.

![](https://cdn.mathpix.com/cropped/2024_03_04_1fd287cad61561871fbdg-3.jpg?height=334&width=1090&top_left_y=775&top_left_x=563)

Figura 4.61.

De aici se poate observa că avem căi de la semnalul de intrare $u[k]$ sau $U(z)$ la toate variabilele de stare ale sistemului, deci sistemul este controlabil.

## Exercițiul 3

Considerăm din nou sistemul de la exercițiul anterior, cu modelul descris de ecuaţiile matriceală de stare şi de ieşire:

$$
\boldsymbol{x}[k+1]=\left[\begin{array}{ccc}0 & 1 & 0 \\ 0 & 0 & 1 \\ -a_{0} & -a_{1} & -a_{2}\end{array}\right] \boldsymbol{x}[k]+\left[\begin{array}{l}0 \\ 0 \\ 1\end{array}\right] u[k]
$$


$$
y[k]=x_{1}[k]
$$

Arătaţi că acest sistem este observabil.

---

Matricele sistemului sunt

$$
\Phi=\left[\begin{array}{ccc}
0 & 1 & 0 \\
0 & 0 & 1 \\
-a_{0} & -a_{1} & -a_{2}
\end{array}\right] \text {, si } \boldsymbol{C}=\left[\begin{array}{lll}
1 & 0 & 0
\end{array}\right]
$$

deci avem

$$
C \Phi=\left[\begin{array}{lll}1 & 0 & 0\end{array}\right]\left[\begin{array}{ccc}0 & 1 & 0 \\ 0 & 0 & 1 \\ -a_{0} & -a_{1} & -a_{2}\end{array}\right]=\left[\begin{array}{lll}0 & 1 & 0\end{array}\right]
$$

$$
C \Phi^{2}=\left[\begin{array}{lll}
1 & 0 & 0
\end{array}\right]\left[\begin{array}{ccc}
0 & 0 & 1 \\
a_{0} & -a_{1} & -a_{2} \\
a_{0} a_{2} & a_{1} a_{2}-a_{0} & a_{2}^{2}-a_{1}
\end{array}\right]=\left[\begin{array}{lll}
0 & 0 & 1
\end{array}\right]
$$

Prin urmare matricea de observabilitate va $\mathrm{fi}$

$$
Q=\left[\begin{array}{c}
C \\
C \Phi \\
C \Phi^{2}
\end{array}\right]=\left[\begin{array}{lll}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{array}\right]
$$

Deoarece, $\operatorname{det} \boldsymbol{Q}=1$
