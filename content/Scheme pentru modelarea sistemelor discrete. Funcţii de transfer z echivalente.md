---
tags:
  - SistemeAutomateCuEsantionare
aliases:
  - Curs 6 SAE
---

Ca şi la sistemele continue, analiza sistemelor de reglare compuse din mai multe subsisteme se face cu ajutorul unor scheme grafice care pun în evidenţă conexiunile existente între aceste elemente şi sensul de transmitere a semnalelor. Faţă de sistemele continue, în cazul sistemelor discrete apare suplimentar unul sau mai multe elemente de eşantionare ideală.

Abordările obţinute, utilizate în reprezentarea grafică a sistemelor discrete cu mai multe elemente sunt:

- schemele bloc-funcţionale;

- grafurile de semnal sau de fluenţă.

## Funcţii de transfer $z$ echivalente

Trebuie remarcat, de la început, că nu există reguli general valabile, ca la sistemele continue, care să permită reducerea rapidă a schemelor-bloc complexe cu funcţii de transfer $z$.

În mod obişnuit pentru reducerea schemelor-bloc complexe se apelează la algebra specifică acestor scheme, scriind relaţii care există între semnalele de ieşire şi intrare precum şi între diverse semnale intermediare. Se poate sublinia faptul că acest mod de abordare se aplică schemelor-bloc cu funcţii de transfer s, obţinându-se astfel relaţii în care apar simultan semnale continue şi eşantionate, fiind posibil ca acelaşi semnal să apară simultan în formele continuă şi eşantionată.

Modul concret de lucru folosit pentru deducerea unor funcţii de transfer $z$ echivalente va fi ilustrat pentru conexiunile serie (cascadă) şi cu reacţie.

## Conexiune în serie (cascadă)

Există două situaţii posibile de conectare a elementelor continue, cazuri evidenţiate de schemele - bloc din figurile $4.37 \mathrm{a}$ şi $4.37 \mathrm{~b}$.

### Elementele continue conectate în serie cu eşantionor intercalat

Se menţionează că toate eşantionoarele au aceeaşi frecvenţă de comutare, $f_{e}=1 / T_{e}$. 

![](https://cdn.mathpix.com/cropped/2023_07_17_2597cb5c34eb9285e14fg-2.jpg?height=771&width=1380&top_left_y=266&top_left_x=338)

Relaţiile algebrice dintre semnale sunt într-o primă etapă:

$Y(s)=G_{2}(s) Y_{1}^{*}(s)$ şi $Y_{1}(s)=G_{1}(s) U^{*}(s)$

Aplicând operatorul de eşantionare acestor relaţii se obţine în continuare:

$Y^{*}(s)=G_{2}^{*}(s) Y_{1}^{*}(s)$ şi $Y_{1}^{*}(s)=G_{1}^{*}(s) U^{*}(s)$,

respectiv:

$Y^{*}(s)=G_{2}^{*}(s) G_{1}^{*}(s) U^{*}(s)$,

de unde, având în vedere definiţia [[Transformata Z|transformatei Z]], rezultă:

$G_{e s}(z)=\left.\frac{Y^{*}(s)}{U^{*}(s)}\right|_{s=\frac{1}{T_{e}} \ln z}=\left.G_{1}^{*}(s) G_{2}^{*}(s)\right|_{s=\frac{1}{T_{e}} \ln z}=G_{1}(z) G_{2}(z)$.

În concluzie funcţia de transfer $z$ echivalentă a două elemente continue conectate în serie cu eşantionor ideal între ele este:

$G_{e s}(z)=G_{1}(z) G_{2}(z)$,

unde:

$G_{1}(z)=Z\left\{G_{1}(s)\right\}$ şi $G_{2}(z)=Z\left\{G_{2}(s)\right\}$

### Elemente continue conectate direct în serie

Din schema bloc prezentată în figura 4.37b se poate scrie mai întâi relaţia:

$Y(s)=G_{1}(s) G_{2}(s) U^{*}(s)$,

care, după aplicarea operatorului de eşantionare, devine:

$Y^{*}(s)=\left[G_{1}(s) G_{2}(s)\right]^{*} U^{*}(s)$. În final, având în vedere definiţia transformatei $Z$, rezultă:

$$
G_{e s}(z)=G_{1} G_{2}(z)
$$

unde:

$$
G_{1} G_{2}(z)=Z\left\{G_{1}(s) G_{2}(s)\right\}
$$

Se poate face următoarea remarcă importantă:

$$
G_{1}(z) G_{2}(z) \neq G_{1} G_{2}(z) \text {, }
$$

respectiv:

$$
Z\left\{G_{1}(s)\right] Z\left[G_{2}(s)\right\} \neq Z\left\{G_{1}(s) G_{2}(s)\right\}
$$

## Proprietăţile de bază ale operatorului de eşantionare

$$
\begin{aligned}
& \text { 1) }\left[U_{1}(s)+U_{2}(s)\right]^{\star}=U_{1}^{*}(s)+U_{2}^{*}(s), \\
& \text { 2) }\left(U^{*}(s)\right)^{*}=U^{*}(s), \\
& \text { 3) }\left[G(s) U^{*}(s)\right]^{*}=G^{*}(s) U^{*}(s), \\
& \text { 4) }[G(s) H(s)]^{*} \neq G^{*}(s) H^{*}(s) .
\end{aligned}
$$

### Exemplul 35

Se consideră funcţiile de transfer $s G_{1}(s)=\frac{1}{s}$ şi $G_{2}(s)=\frac{1}{s+1}$. Să cere să se calculeze $G_{1}(z) G_{2}(z)$ şi $G_{1} G_{2}(z)$.

Avem:

$$
\begin{aligned}
& G_{1}(z)=Z\{1 / s\}=\frac{z}{z-1}, \\
& G_{2}(z)=Z\left\{\frac{1}{s+1}\right\}=\frac{z}{z-e^{-T_{e}}},
\end{aligned}
$$

deci:

$$
G_{1}(z) G_{2}(z)=\frac{z^{2}}{(z-1)\left(z-e^{-T_{e}}\right)} .
$$

Pentru a se calcula funcţia de transfer $G_{1} G_{2}(z)$, se determină mai întâi dezvoltarea în fracţii simple:

$$
G_{1}(s) G_{2}(s)=\frac{1}{s(s+1)}=\frac{1}{s}-\frac{1}{s+1}
$$

de unde se obţine:

$$
Z\left[G_{1}(s) G_{2}(s)\right]=\frac{z}{z-1}-\frac{z}{z-e^{-T_{e}}}=\frac{z\left(1-e^{-T_{e}}\right)}{(z-1)\left(z-e^{-T_{e}}\right)} .
$$

Rezultă că:

$$
G_{1}(z) G_{2}(z)=\frac{z^{2}}{(z-1)\left(z-e^{-T_{e}}\right)} \neq \boldsymbol{Z}\left\{G_{1}(s) G_{2}(s)\right\}=\frac{z\left(1-e^{-T_{e}}\right)}{(z-1)\left(z-e^{-T_{e}}\right)} .
$$

## Conexiunea cu reacţie

Se consideră sistemul discret în circuit închis cu eşantionarea erorii, prezentat în figura a. Remarcăm faptul că schema cu eşantionare a erorii din figura 4.38a este echivalentă funcţional în zona sumatorului cu schema cu două eşantionoare ideale plasate ca în figura b.

![](https://cdn.mathpix.com/cropped/2023_07_17_2597cb5c34eb9285e14fg-4.jpg?height=674&width=1282&top_left_y=785&top_left_x=387)

Pentru deducerea funcţiei de transfer echivalente a conexiunii cu reacţie se scriu mai întâi relaţiile algebrice care corelează semnalele din schema bloc. Astfel avem:

$Y(s)=G(s) E^{*}(s)$,

$E(s)=R(s)-H(s) Y(s)$.

Substituind $Y(s)$ din relaţia (4.276) în expresia (4.277) se obţine relaţia:

$E(s)=R(s)-G(s) H(s) E^{*}(s)$.

care după aplicarea operatorului de eşantionare devine:

$E^{*}(s)=R^{*}(s)-\left[G(s) H(s) E^{*}(s)\right]^{*}$,

respectiv:

$E^{\star}(s)=R^{\star}(s)-[G(s) H(s)]^{\star} E^{*}(s)=R^{*}(s)-G H^{*}(s) E^{*}(s)$,

de unde se obţine [[Transformata Laplace|transformata Laplace]] eşantionată a erorii:

$E^{*}(s)=\frac{R^{*}(s)}{1+G H^{*}(s)}$.

Substituţia expresiei (4.281) în relaţia (4.276) furnizează [[Transformata Laplace|transformata Laplace]] a semnalului de ieşire în raport cu semnalul eşantionat de intrare: $Y(s)=\frac{G(s)}{1+G H^{*}(s)} R^{*}(s)$,

din care, după aplicarea operatorului de eşantionare, rezultă:

$Y^{*}(s)=\frac{G^{*}(s)}{1+G H^{*}(s)} R^{*}(s)$,

de unde, cu schimbarea de variabilă $s=\frac{1}{T_{e}} \ln z$, se obţine:

$Y(z)=\frac{G(z)}{1+G H(z)} R(z)$

În final rezultă funcţia de transfer $z$ a sistemului cu reacţie negativă neunitară, cu eşantionarea erorii, exprimată conform relaţiei:

$G_{e r}(z)=\frac{Y(z)}{U(z)}=\frac{G(z)}{1+G H(z)}$.
