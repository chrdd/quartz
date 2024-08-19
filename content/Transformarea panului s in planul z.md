---
tags:
  - SistemeAutomateCuEsantionare
aliases:
  - Curs 4 SAE
---

Deoarece anumite proprietăţi ale sistemelor continue au fost analizate folosinduse configuraţia în planul complex s a polilor şi zerourilor, prezintă interes studiul transformării planului s (a unor porţiuni din acesta sau a unor drepte cu anumite caracteristici) în planul $z$.

Schimbarea de variabilă $z=e^{s T_{e}}$ constituie o transformare conformă a planului $\mathbf{s}$ în planul z. Din punctul de vedere al transformării $z=e^{s T_{e}}$, planul s este împărţit într-un număr infinit de fâşii de periodicitate, limita acestor fâşii fiind dreptele orizontale, paralele cu axa abscisei, aşa cum se arată în figura 4.20,a.

Prima fâşie (numită primară) este cuprinsă între $\omega=-\frac{\omega_{e}}{2}$ şi $\frac{\omega_{e}}{2}$, iar celelalte fâşii sunt cuprinse între $-\frac{\omega_{e}}{2}$ şi $-3 \frac{\omega_{e}}{2},-3 \frac{\omega_{e}}{2}$ şi $-5 \frac{\omega_{e}}{2}, \ldots$ pentru pulsaţiile negative, respectiv între $\frac{\omega_{e}}{2}$ şi $3 \frac{\omega_{e}}{2},3 \frac{\omega_{e}}{2}$ şi $5 \frac{\omega_{e}}{2} \ldots$ pentru pulsaţiile pozitive. Împărţirea planului $s$ în fâşii este o consecinţă a proprietăţii de periodicitate a funcţiei exponenţiale de exponent complex care corespunde schimbării de variabilă:

$e^{s T_{e}}=e^{(\sigma+j \omega) T_{e}}=e^{\sigma T_{e}} e^{j 2 \pi \omega / \omega_{e}}$.

Se poate verifica uşor că pentru $\omega \in\left(-\frac{\omega_{e}}{2}, \frac{\omega_{e}}{2}\right)$ rezultă $e^{s T_{e}} \in \mathrm{e}^{\sigma T_{e}}\left(\mathrm{e}^{-\mathrm{j} \pi} \div \mathrm{e}^{\mathrm{j} \pi}\right)$; un rezultat similar rezultă, de exemplu, pentru $\omega \in\left(\omega_{e} / 2,3 \omega_{e} / 2\right)$, când avem $$\mathrm{e}^{s T_{e}} \in \mathrm{e}^{\sigma T_{e}}\left(\mathrm{e}^{\mathrm{j} \pi} \div \mathrm{e}^{\mathrm{j} 3 \pi}\right) \equiv \mathrm{e}^{\sigma T_{e}}\left(\mathrm{e}^{\mathrm{j} \pi} \div \mathrm{e}^{-\mathrm{j} \pi}\right)$$

![[Pasted image 20230715154605.png]]

## Transformarea semiplanului complex stang in planul z

Avand in vedere periodicitatea se considera portiunea din semiplanul stang al fasiei primare definita in planul $s$ prin conturui $1-2-3-4-5$ *(fig a)*. Se va analiza, pentru fiecare interval din conturul poligonal inchis, curba care rezulta in planul $z$ prin transformarea conforma $z=e^{sT_e}$.

**Intervalul $1-2$ :**

$s=0+\left.\mathrm{j} \omega\right|_{\omega \in\left(0, \omega_{e} / 2\right)} \rightarrow Z=\left.\mathrm{e}^{(0+\mathrm{j} \omega) T_{e}}\right|_{\omega \in\left(0, \omega_{e} / 2\right)}$,

$|z|=\left|e^{\mathrm{j} \omega T_{e}}\right|_{\omega \in\left(0, \omega_{e} / 2\right)}=1$ cu $z_{1}=e^{\mathrm{j} 0 T_{e}}=1$ şi $z_{2}=\mathrm{e}^{\mathrm{j} \omega_{e} T_{e} / 2}=-1$.

Prin urmare, dreapta verticala cuprinsa intre punctele 1 si 2 se transforma in planul $z$ intr-un arc de cerc de raza unitara intre punctele $z_1=1$ si $z_2=-1.

**Intervalul $2-3$ :** 

$$
s=\sigma+\left.\mathrm{j} \frac{\omega_{e}}{2}\right|_{\sigma \in(0,-\infty)} \rightarrow z=\mathrm{e}^{\sigma T_{e}} \mathrm{e}^{\mathrm{j} \omega_{e} T_{e} / 2}=-\left.\mathrm{e}^{\sigma T_{e}}\right|_{\sigma \in(0,-\infty)} .
$$

Când $\sigma$ se modifică de la 0 la $-\infty, z$ va fi un număr real cu valori cuprinse între -1 şi 0 . Deci schimbarea de variabilă transformă dreapta orizontală la $\omega=\omega_{e} / 2$, cu $\sigma$ cuprins în intervalul $(0,-\infty)$, într-o dreaptă, de asemenea orizontală, suprapusă semiaxei reale negative a planului $z$, cuprinsă între $z_{2}=-1$ şi $z_{3}=0$.

**Intervalul 3-4:**

Deoarece $s=\sigma+\left.j \omega\right|_{\sigma=-\infty, \omega \in\left(\omega_{e} / 2,-\omega_{e} / 2\right)}$, în planul $z$ avem

$$
z=\left.\mathrm{e}^{-\mathrm{j} \infty T_{e}} \mathrm{e}^{\mathrm{j} \omega T_{e}}\right|_{\omega \in\left(\omega_{e} / 2,-\omega_{e} / 2\right)}=\left.0 \cdot e^{\mathrm{j} \omega T_{e}}\right|_{\omega \in\left(\omega_{e} / 2,-\omega_{e} / 2\right)}=0 .
$$

Dacă $\omega$ ia valori în gama $\left(\omega_{e} / 2,-\omega_{e} / 2\right)$ punctul $z$ se deplasează în jurul originii pe un arc de cerc cu rază infinit mică.

**Intervalul 4-5:**

$$
s=\sigma-\left.\mathrm{j} \frac{\omega_{e}}{2}\right|_{\sigma \in(-\infty, 0)} \rightarrow z=\mathrm{e}^{\sigma T_{e}} \mathrm{e}^{-\mathrm{j} \omega T_{e} / 2}=-\left.\mathrm{e}^{\sigma T_{e}}\right|_{\sigma \in(-\infty, 0)} .
$$

Transformarea este asemănătoare cu cea realizată între punctele 2 şi 3. De această dată variabila $z$ ia valori pe semiaxa reală negativă între punctele $z_{4}=0$ şi $z_{5}=-1$.

**Intervalul 5-1:**

$$
s=0+\left.\mathrm{j} \omega\right|_{\omega \in\left(-\omega_{e} / 2,0\right)} \rightarrow z=\left.\mathrm{e}^{(0+\mathrm{j} \omega) T_{e}}\right|_{\omega \in\left(-\omega_{e} / 2,0\right)},|z|=\left|e^{j \omega T_{e}}\right|_{\omega \in\left(-\omega_{e} / 2,0\right)}=1,
$$

cu $z_{5}=\mathrm{e}^{-\mathrm{j} \omega_{\mathrm{e}} T_{e} / 2}=\mathrm{e}^{-\mathrm{j} \pi}=-1$ şi $z_{6}=z_{1}=\mathrm{e}^{\mathrm{j} 0 T_{e}}=1$.

Asemănător cu transformarea conformă a dreptei $1-2$, rezultă, şi în acest caz, un semicerc de rază unitară care începe în punctul $z_{5}=-1$ şi se termină în punctul $z_{6}=z_{1}=1$.

Rezumând, fâşia primară din semiplanul complex stâng (respectiv prin periodicitate întreg semiplanul stâng al variabilei complexe $s$) se transformă, prin schimbarea de variabilă $z=e^{s T_{e}}$, în planul $z$, în interiorul cercului de rază unitară. Rezultatul este ilustrat grafic în figura b. În concluzie, toate punctele din care acţionează conform definiţiei din relaţiile (4.204)semiplanul stâng $s$ sunt transformate în interiorul cercului de rază unitară din planul $z$. Punctele din semiplanul $s$ drept sunt transformate în exteriorul cercului de rază unitară din planul $z$.

## Modelele dinamice ale sistemelor discrete

Modelul dinamic al unui sistem (continuu sau discret) ilustrează modul în care se obţine semnalul de ieşire din semnalul de intrare. În cazul sistemelor liniare şi continue modelul dinamic de bază este ecuaţia diferenţială cu coeficienţi constanţi cu forma generală: 

$$
\begin{aligned}
\frac{\mathrm{d}^{n} y(t)}{\mathrm{d} t^{n}}+\alpha_{1} & \frac{\mathrm{d}^{n-1} y(t)}{\mathrm{d} t^{n-1}}+\ldots+\alpha_{n-1} \frac{\mathrm{d} y(t)}{\mathrm{d} t}+\alpha_{n} y(t)= \\
& =\beta_{0} \frac{\mathrm{d}^{m} u(t)}{\mathrm{d} t^{m}}+\beta_{1} \frac{\mathrm{d}^{m-1} u(t)}{\mathrm{d} t^{m-1}}+\ldots+\beta_{m-1} \frac{\mathrm{d} u(t)}{\mathrm{d} t}+\beta_{m} u(t),
\end{aligned}
$$

unde $u(t)$ şi $y(t)$ sunt funcţiile continue de timp asociate mărimilor de intrare respectiv de ieşire, iar coeficienţii $\alpha_{i}(i=0, \ldots, n-1)$ şi $\beta_{j}(j=0, \ldots, m)$ sunt constante cu valori reale. Echivalentul discret al ecuaţiilor diferenţiale este ecuaţia cu diferenţe.

### Ecuaţii liniare cu diferenţe

Se reaminteşte că semnalele discrete sunt descrise, folosind notaţiile specifice, ca secvenţe temporale de numere de forma $u\left(k T_{e}\right)$ sau $u[k]$ pentru mărimea de intrare, respectiv $y\left(k T_{e}\right)$ sau $y[k]$ pentru mărimea de ieşire.

Având în vedere evoluţia în timp a acestor semnale, valorile $u[k]$ şi $y[k]$ se vor numi eşantioane curente ale mărimilor respective iar valorile $y[k-i]$ şi $u[k-j]$, cu $i=1, \ldots, n$ şi $j=1, \ldots, m$, vor fi eşantioane anterioare ale mărimilor considerate.

Ecuaţiile liniare cu diferenţe, scrise în forma recurentă (care se va prezenta ulterior) determină eşantionul curent al mărimii de ieşire în funcţie de eşantioanele anterioare ale mărimilor de intrare şi ieşire.

Ecuaţiile cu diferenţe se pot introduce în mai multe moduri. Se va ilustra deducerea ecuaţ̧iilor cu diferenţe pornind de la ecuaţia diferenţială, prin aproximarea succesivă a derivatelor cu diferenţa de ordinul unu. Aproximarea se face conform schemei care se prezintă în continuare, pentru mărimea de ieşire:

$$
\begin{aligned}
& \frac{\mathrm{d} y(t)}{\mathrm{d} t} \cong \frac{\Delta y_{k}}{T_{e}}=\frac{y[k]-y[k-1]}{T_{e}}, \\
& \frac{\mathrm{d}^{2} y(t)}{\mathrm{d} t^{2}}=\frac{\mathrm{d}}{\mathrm{d} t}\left(\frac{\mathrm{d} y(t)}{\mathrm{d} t}\right) \cong \frac{\frac{\Delta y_{k}}{T_{e}}-\frac{\Delta y_{k}-1}{T_{e}}}{T_{e}}=\frac{y[k]-2 y[k-1]+y[k-2]}{T_{e}^{2}}, \\
& \frac{\mathrm{d}^{3} y(t)}{\mathrm{d} t^{3}} \cong \frac{y[k]-3 y[k-1]+3 y[k-2]-y[k-3]}{T_{e}^{3}},
\end{aligned}
$$

Forma exactă pentru derivata de ordinul $n$ nu este relevantă, deoarece, de obicei, ecuaţia cu diferenţe se calculează în alt mod. Se remarcă faptul că în relaţiile scrise mai înainte pentru aproximarea derivatelor $s-a$ folosit notaţia $y[k] \equiv y\left(k T_{e}\right)$. De asemenea, la deducerea ecuaţiilor cu diferenţe funcţiile de timp $y(t)$ şi $u(t)$ au fost înlocuite cu eşantioanele $y[k]$ şi $u[k]$, deci:

$y(t) \cong y[k]$ şi $u(t) \cong u[k]$.

Aplicând, în ecuaţia diferenţială de mai sus, schema de aproximare a derivatelor se obţine forma generală a unei ecuaţii cu diferenţe: 

$$
y[k]+a_{1} y[k-1]+\ldots+a_{n} y[k-n]=b_{0} u[k]+b_{1} u[k-1]+\ldots+b_{m} u[k-m]
$$

unde $k \in \boldsymbol{Z}$ sau $\boldsymbol{N}, n, m \in \boldsymbol{N}$ şi $a_{i}, b_{j} \in \boldsymbol{R}$.

Ordinul maxim al eşantionului anterior care apare în ecuaţia cu diferenţe este determinat de ordinul sistemului $n$, fiind $k-n$.

Dacă sistemul liniar conţine un timp mort pur, multiplu întreg al perioadei de eşantionare, de forma $\tau=\ell T_{e}$, cu $\ell \in N$, ecuaţia cu diferenţe se va scrie conform relaţiei:

$$
y[k]+a_{1} y[k-1]+\ldots+a_{n} y[k-n]=b_{0} u[k-\ell]+b_{1} u[k-\ell-1]+\ldots+b_{m} u[k-\ell-m] . \text { (4.192) }
$$

O formă particulară a ecuaţiei cu diferenţe (4.192) care permite calculul recurent al eşantionului curent al mărimii de ieşire, în funcţie de eşantioanele anterioare ale intrării şi ieşirii, este exprimată conform relaţiei:

$$
y[k]=-a_{1} y[k-1]+\ldots-a_{n} y[k-n]+b_{0} u[k]+b_{1} u[k-1]+\ldots+b_{m} u[k-m], \ell=0,
$$

Sistemele discrete care au toţi coeficienţii $a_{i}, i=1, \ldots, n$ egali cu zero se numesc sisteme cu răspuns finit la impuls (Finite Impulse Response - FIR).

Dacă cel puţin un coeficient $a_{i}$ este diferit de zero sistemul discret se numeşte autoregresiv sau, în mod alternativ, sistem cu răspuns infinit la impuls (Infinite Impulse Response - IIR).

În legătură cu modul în care s-a dedus mai înainte ecuaţia cu diferenţe se poate remarca faptul că rezultatul obţinut este aproximativ, fapt reflectat în valorile coeficienţilor care vor fi diferite de valorile exacte care se obţin când se foloseşte [[Transformata Z|transformata Z]]. Aspectele de principiu sunt însă valabile şi în acest caz.

### Operatorul de întârziere cu un pas. funcţii de transfer operaţionale

Un alt tip de model pentru sistemele discrete se poate introduce, pornind de la ecuaţia cu diferenţe, pe baza operatorului de întârziere cu un pas $q^{-1}$, care este definit cu relaţii de forma:

$$q^{-1} y[k]=y[k-1]\text{, respectiv }q^{-1} u[k]=u[k-1]$$

Aplicând în mod repetat operatorul de întârziere cu un pas se obţin expresiile formale următoare:

$$y[k-i]=q^{-i} y[t]\text{, respectiv }u[k-j]=q^{-j} u[t]$$

Înlocuind aceste expresii în ecuaţia cu diferenţe (4.191) se obţine relaţia algebrică:

$$
\left(1+a_{1} q^{-1}+\ldots+a_{n} q^{-n}\right) y[k]=q^{-\ell}\left(b_{0}+b_{1} q^{-1}+\ldots+b_{m} q^{-m}\right) u[k]
$$

de unde, cu notaţiile:

$$
\begin{aligned}
& A(q) \equiv A\left(q^{-1}\right)=1+a_{1} q^{-1}+\ldots+a_{n} q^{-n}, \\
& B(q) \equiv B\left(q^{-1}\right)=q^{-\ell}\left(b_{0}+b_{1} q^{-1}+\ldots+b_{m} q^{-m}\right),
\end{aligned}
$$

se obţine modelul operaţional:

$$y[k]=\frac{B(q)}{A(q)} u[k]=G(q) u[k]$$

Funcţia raţională de argument $q$ :

$$G(q)=\frac{B(q)}{A(q)}=\frac{q^{-\ell}\left(b_{0}+b_{1} q^{-1}+\ldots+b_{m} q^{-m}\right)}{1+a_{1} q^{-1}+\ldots+a_{n} q^{-n}}$$

se numeşte funcţie de transfer operaţională. Se remarcă faptul că argumentul q care apare în această funcţie de transfer nu are caracterul unei variabile complexe fiind doar o notaţie formală.

Pe baza ecuaţiilor cu diferenţe a metodelor numerice de integrare, Euler şi trapezului, se determină funcţiile de transfer $z$ pentru elementul integrator.

Ecuaţiile recurente cu diferenţe care modelează elementul integrator, respectiv operaţia de integrare numerică sunt:

- pentru metoda Euler a dreptunghiului (înapoi) cu latura din spate pe curbă MDS (BRR-Backward Rectangular Rule):

$$
y[k]=y[k-1]+T_{e} u[k]
$$

- pentru metoda Euler a dreptunghiului (înainte) cu latura din faţă pe curbă MDF (FRRForward Rectangular rule):

$$
y[k]=y[k-1]+T_{e} u[k-1]
$$

- pentru metoda trapezului MT (TR-trapezoid rule):

$$
y[k]=y[k-1]+\frac{T_{e}}{2}(u[k]+u[k-1])
$$

Aplicând în continuare definiţia transformatei $Z$ şi teorema de deplasare în timp, relaţiilor $(4.233) \div(4.235)$ se obţin următoarele expresii:

$$
\left(1-z^{-1}\right) Y(z)=T_{e} U(z)
$$

$\left(1-z^{-1}\right) Y(z)=T_{e} z^{-1} U(z)$

$\left(1-z^{-1}\right) Y(z)=\frac{T_{e}}{z}\left(1+z^{-1}\right) U(z)$

de unde rezultă funcţiile de transfer $z$ :

$G(z)=\frac{Y(z)}{U(z)}=\frac{T_{e}}{1-z^{-1}}=\frac{z T_{e}}{z-1}, \operatorname{MDS}$ (BRR-Backward Rectangular Rule)

$G(z)=\frac{Y(z)}{U(z)}=\frac{T_{e} z^{-1}}{1-z^{-1}}=\frac{T_{e}}{z-1}$, MDF (FRR-Forward Rectangular rule)

$G(z)=\frac{Y(z)}{U(z)}=\frac{T_{e}}{2} \frac{1+z^{-1}}{1-z^{-1}}=\frac{T_{e}}{2} \frac{z+1}{z-1}$, MT (TR-trapezoid rule).
