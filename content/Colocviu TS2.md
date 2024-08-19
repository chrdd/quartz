---
tags:
  - TeoriaSistemelor2
---

#TeoriaSistemelor2 
## Reducerea diagramei block
![Block diagram reduction using Matlab - YouTube](https://www.youtube.com/watch?v=uGnRRt-dKvw)![[Pasted image 20230603180921.png]]
![[Pasted image 20230603180950.png]]

```matlab
nblocks=7;

iu=1;

iy=4;

q=[1 -5 -6 -7;2 1 0 0;3 2 0 0;4 3 0 0;5 2 0 0;6 3 0 0;7 4 0 0];

n1=1;

d1=2;

n2=4;

d2=[1 4];

n3=1;

d3=[1 2];

n4=1;

d4=[1 3];

n5=2;

d5=1;

n6=5;

d6=1;

n7=-1;

d7=1;

blkbuild

[A,B,C,D]=connect(a,b,c,d,q,iu,iy);
```

![[WhatsApp Image 2023-05-25 at 20.26.40.jpg]]
![[WhatsApp Image 2023-05-25 at 20.26.53.jpg]]

## Functia de transfer din Bode
![How to find transfer function from Bode Plot - YouTube](https://www.youtube.com/watch?v=QXgXaJKncGQ)
![Deriving the Transfer Function from Bode Plot | Example #1 - YouTube](https://www.youtube.com/watch?v=B55mFHw4GXY)
Daca panta se schimba in spre negativ rezulta **poli** (magnitudine).
Daca panta se schimba in spre pozitiv rezulta **zero** (magnitudine).

![[colocviu_bode_explicat1.pdf]]