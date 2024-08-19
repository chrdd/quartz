---
tags:
  - SistemeAutomateCuEsantionare
---

Analiza spectrala a semnalelor se face cu [[Transformata Fourier#Transformata Fourier|Transformata Fourier]]. 

Spectrul de amplitudine al unui semnal continuu $f(t)$ se obtine prin aplicarea *Transformatei Fourier*.
$$F(j \omega)= \int^{\infty}_{-\infty}f(t)e^{-j \omega t}dt$$
>[!info] Observatie
>$F(j \omega)$ este un numar complex, astfel se prefera utilizarea modulului sau.

In figura de mai jos se prezinta forma de variatie a spectrului de amplitudine al semnalului continuu $f(t)$

![[Attachments/image-removebg-preview(1).png]]

# Spectrul unui semnal esantionat
Spectrul unui semnal esantionat este format dintr-o infinitate de spectre similare cu cel al semnalului continuu, ponderate cu $\frac{1}{Te}$ si centrate cu valori multiplu intreg al pulsatiei de esantionare.
**Formula matematica:**
$$\frac{1}{Te}\sum^{\infty}_{k=-\infty}F(\omega-k \omega_e)$$
**Demonstratie matematica:**
$$F^*(j \omega)= \int^{\infty}_{- \infty} f^*(t)e^{-j \omega t} dt= \int^{\infty}_{-\infty}[\frac{1}{Te}f(t)\sum^{\infty}_{k=-\infty}e^{j k \omega_e}]e^{-j \omega t} dt= \frac{1}{Te}\sum^{\infty}_{k=-\infty} \int^{\infty}_{-\infty}f(t)e^{-jt(\omega-k \omega_e)}dt=\frac{1}{Te}\sum^{\infty}_{k=-\infty}F(\omega-k \omega_e)$$

In figura de mai jos se prezinta modulul spectrului de amplitudine al unui semnal esantionat ideal, considerandu-se 2 situatii diferite

![[image-removebg-preview(2) 1.png]]

![[image-removebg-preview(3) 1.png]]

In figura *a* se prezinta spectrul semnalului esantionat in care pulsatia de esantionare depaseste de 2 ori cea mai mare pulsatie continuta in spectrul semnalului continuu poate fi reconstrituit prin filtrarea (filtrul trece jos) din spectrul semnalul esantionare.

In figura *b* se prezinta spectrul semnalului esantionat in cazul in care pulsatia de esantionare este mai mica decat dublul celei mai mari pulsatii continute in spectrul semnalului continuu.

Se observa in acest caz ca exista o suprapunere a lobilor adiacenti, fenomen numit "Aliasing"
Se considera ca spectrul reconstituit este modificat fata de cel original in zona pulsatiilor $\omega_e$, $\omega_m$, $\omega_{\frac{e}{2}}$.
Spectrul lobului principal se suprapune cu spectrul lobului central pe pulsatia $\omega_m$

Erorile cauzate de fenomenul de aliasing pot sa devina foarte importante daca semnalul continuu original contine zgomote de amplitudine mare.

Solutia practica de eliminare sau minimizare a efectelor fenomenului de aliasing consta in filtrarea cu un **filtrul trece jos** a semnalului continuu inainte ca acesta sa fie aplicat convertorului inainte ca acesta sa fie aplicat convertorului analog numeric.

Acest filtru (numit anti-aliasing) va elimina toate componentele cu pulsatia mai mare de $\frac{\omega_m}{2}$

In figura urmatoare se prezinta spectrul semnalului esantionat dupa aplicarea filtrului anti-aliasing:

![[Attachments/image-removebg-preview(5).png]]

Pulsatia critica la care apare aliasing se numeste **pulsatie Nyquist** ($\omega_N=\frac{\omega_e}{2}$)

O concluzie a fenomenului de aliasing este **teorema Shannon-Nyquist**.
Conform ecuatiei teoremei, un semnal continuu poate fi reconstruit din esantioanele sale daca pulsatia este mai mare sau egala cu dublul celei mai mari pulsatii continute in semnalul continuu.
 
 ---
 [[Curs 2 SAE.excalidraw]]