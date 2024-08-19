---
tags:
  - CircuiteLogiceProgramabile
---


## Teorie
### Fundamentele circuitelor logice programabile

1. **Circuitele integrate digitale se împart în 3 categorii:**
    1. Cu funcție fixă
    2. Dedicat unei aplicații specifice
    3. Programabile
2. **Circuitele cu funcție fixă:**
    1. Sunt create pentru a putea fi folosite într-o mare varietate de aplicații
    2. Sunt ieftine, simple de utilizat
3. **Circuitele dedicate unei aplicații specifice:**
    1. Sunt dispozitive proiectate de către utilizator
    2. Sunt produse pe baza specificațiilor utilizatorului
    3. Se numesc și ASIC (application specific integrated circuit)
4. **Circuitele programabile:**
    1. Au structura fixă, configurată de către utilizator pentru a implementa o anumită funcție logică
    2. Îmbină avantajele circuitelor cu funcție fixă cu avantajele circuitelor ASIC
5. **Utilizarea dispozitivelor logice programabile (DLP)**
    1. Înlocuirea unui sistem digital vechi
    2. Implementarea unor sisteme cu volum mai mic
    3. Implementarea de sisteme ce necesită schimbarea ulterioară a funcționalității
    4. Implementarea de prototipuri de validare
6. **Avantajele dispozitivelor logice programabile (DLP)**
    1. Îmbunătățirea performanțelor de viteză
        1. Semnalele de interconectare devin interne, astfel nu mai trebuie condiționate
        2. Viteză net superioară aplicațiilor cu circuite cu funcție fixă dar sub viteză ASIC (din cauza programabilității punctelor de interconexiune care cresc capacitățile parazite)
    2. Reducerea dimensiunii și a puterii disipate
        1. Sistemul implementat cu dispozitive programabile este de dimensiuni fizice mai mici
        2. Conține mai puține chipuri, poate doar unul singur
    3. Timpi de proiectare mai scurți (de ordinul minutelor)
        1. Proiectarea constă în descrierea comportamentală
        2. Modelul se poate valida direct pe placă de dezvoltare
    4. Rata de defectare mai mică (număr de componente redus)
    5. Dificil de copiat (logica este în interiorul circuitului)
    6. Ușurința depanării sistemelor defecte
    7. Actualizarea / Îmbunătățirea funcției implementate (prin reprogramare, fără schimbări hardware)
7. **Tehnologia cu legături fuzibile**
    1. Este printre primele tehnologii de programabilitate apărute
    2. Dispozitivele sunt realizate având toate legăturile
    3. Fuzibilele în circuitele logice programabile sunt realizate folosind aceleași tehnologii cu care sunt realizați tranzistorii din interiorul circuitului.
    4. Înaintea programării toate fuzibilele sunt intacte
    5. ![[Pasted image 20240613145448.png]]
    6. Pentru programare, unele dintre fuzibile vor fi distruse prin aplicarea de pulsuri cu tensiune și curent relativ mare
    7. Dispozitivele ce folosesc tehnologii cu legături fuzibile se numesc și one time programmable (OTP)
    8. Procesul de distrugere este numit programare și este final
    9. FPGA nu folosesc fuzibile
8. **Tehnologia cu legături antifuzibile**
    1. O legătură "antifuse" se prezintă inițial ca o coloană de siliciu microscopic și amorfa (noncristalină) între 2 benzi de metalizare
    2. În stare neprogramată, siliciul amorf acționează ca un izolator cu o rezistență foarte mare ($>10^{9} \Omega$)
    3. Programarea se face prin aplicarea de pulsuri cu tensiune și curent relativ mare la intrările circuitului
    4. Prin programarea legăturii se creează o legătură activă prin transformarea siliciului amorf izolator într-un siliciu conductiv
    5. Dispozitivele ce folosesc tehnologia cu legături antifuzibile se numesc și one time programmable (OTP)
    6. Procesul este ireversibil
    7. ![[Pasted image 20240613145655.png]]

### Memorii programabile

1. **Sistemele electronice utilizează 2 tipuri de memorii:**
    1. Memorii doar cu citire (ROM)
    2. Memorii cu acces aleatoriu (RAM)
2. **Memoriile ROM (nonvolatile)**
    1. Datele pe care le conțin rămân în memorie și la oprirea tensiunii de alimentare
    2. Componentele sistemului pot citi date din memoria ROM, dar nu pot scrie date în acestea
    3. Acestea sunt denumite mask-programmable deoarece datele sunt blocate la momentul creării
    4. Prin procesul de "foto-mascare" sunt creați tranzistori în structura circuitului din memorie și interconectați prin legături metalice
    5. Acest tip de memorie constă într-o matrice de linii și coloane
    6. Coloanele au rezistență "pull-up" pentru a ține coloana la weak 1
    7. Intersecția linie-coloană are un tranzistor și o legătură programabilă prin mascare
    8. Configurarea necesită o singură masca-foto pentru a defini celulele ce trebuie programate și celulele ce rămân neconectate
    9. ![[Pasted image 20240613150408.png]]
3. **Memorii EPROM (Erasable Programmable Read Only Memory)**
    1. Datorită faptului că legăturile fuzibile nu pot fi modificate, necesitatea ștergerii datelor a condus la memoria EPROM
    2. Tranzistorul EPROM are structura de tranzistor MOS, dar cu o poartă flotantă (floating gate) adițională, izolată prin straturi de oxid de siliciu ($S_{i}O_{2}$)
    3. În starea neprogramată, poarta flotantă este descărcată și nu afectează funcționarea porții de control (control gate)
    4. Programarea tranzistorului se face la o tensiune de $\approx12V$ între partea de control și drena
    5. La aplicarea tensiunii, tranzistorul este puternic activat și are loc procesul de "high energy electron injection"
    6. După oprirea semnalului pe poarta flotantă rămâne o sarcină negativă
    7. Activarea unei linii va activa toți tranzistorii conectați la acea linie, generând starea logică 0 pentru toate coloanele respective (tranzistorii sunt în conductie).
    8. Programarea EPROM se face la intrările primare pentru a încărca porțile flotante
    9. Celulele programate au tranzistori dezactivați (au permanent valoarea 1 logic)
    10. Spre deosebire de memoria cu legături fuzibile, EPROM sunt mai mici
    11. Pot fi șterse, deci reprogramate, iar timpul de ștergere este $\approx 20 \text{ min}$
4. **Memorii EEPROM (Electrically Erasable Programmable Read Only Memory)**
    1. Celula EEPROM este de aproximativ 2,5 ori mai mare decât EPROM (are 2 tranzistori + spațiul dintre ei)
    2. Tranzistorul EEPROM este asemănător cu cel folosit în celula EPROM, dar are izolantul ce înconjoară partea flotantă mult mai subțire
    3. Al 2-lea tranzistor (MOS) poate fi utilizat pentru ștergerea electrică a celulei
5. **Memorii flash**
    1. Numele "flash" reflectă rapiditatea de ștergere
    2. Există 2 tipuri de memorie flash:
        1. **Flash cu o singură celulă cu tranzistor**: are aceeași are ca o celulă EEPROM, dar au strat izolator de oxid de siliciu mult mai subțire
        2. **Flash cu celule cu 2 tranzistori**: Similar cu EEPROM, însă permit ștergerea și reprogramarea lor la nivel de word (o linie întreagă)
6. **Memorii RAM**
    1. Sunt memorii volatile (Datele pe care le conțin se șterg din memorie la oprirea tensiunii de alimentare)
    2. Componentele sistemului pot citi și scrie date din/in memoria RAM
    3. Din punct de vedere constructiv, există 2 tipuri de memorii RAM:
        1. **Memorie DRAM (Dynamic Random Access Memory):**
            1. Celula de memorie este formată dintr-un tranzistor și un condensator
            2. Dynamic vine de la faptul că în timp, condensatoarele se descarcă, astfel celulele trebuie să fie reîncărcate periodic
        2. **Memorie SRAM (Static Random Access Memory):**
            1. Sunt denumite statice deoarece își păstrează valoarea
            2. Valoarea scrisă rămâne neschimbată până când este suprascrisă sau până la întreruperea alimentării
            3. La întreruperea alimentării, informația stocată se pierde
            4. Reprogramarea se face rapid și în număr nelimitat de scrieri
            5. Tehnologia SRAM poate fi folosită ca înlocuitor al tehnologiilor cu legături fuzibile/antifuzibile
### Clasificare dispoziivelor programabile
1. Primele circuite programabile au fost denumite PLD (Programmable Logic Device)
	1. Principalele componente utilizate erau memoriile PROM
	2. Clasificare:
		1. **SPLD (Simple Programmable Logic Device)**
			1. **PROM**
			2. **PLA**
			3. **PAL**
		2. **CPLD (Complex Programmable Logic Device)**
			1. **FPGA**
			2. **CPLD**
2. **Circuite programabile PROM**
	1. Primele PLD au fost bazate pe memoriile PROM
	2. Sunt compuse din:
		1. Un nivel AND neprogramabil
		2. Un nivel OR care poate implementa functii programabile
	3. Memorii PROM pot fi folosite la implementarea oricarei functii logice
	4. Structurile PROM sunt implementate ca sume de produse
	5. Sunt folositoare pentru ecuatii ce contin un numar mare de termeni produs, dar suporta un numar relativ mic de intrari
	6. Dispozitivele PROM sunt realizate cu:
		1. legaturi fuzibile
		2. celule de memorie EPROM
		3. celule de memorie EEPROM
3. **Circuit PLA (Programmable Logic Array)**
	1. Au aparut ca o inbunatatire a limitarilor circuitelor PROM
	2. Au ambele niveluri programabile (AND si OR)
	3. Confera o programabilitate totala
	4. Numarul de porti AND in matricea de produse este independent de numarul de porti OR din matricea de sume
	5. Sunt folosite pentru functii mari
	6. Dezavantaje: 
		1. Celulele cu cai lung de parcurs prin legaturile programabile
		2. Sunt mai lente decat circuitele PROM
4. **Circuite PAL (Programmable Array Logic)**
	1. Au inbunatati problema vitezei din circuitele PLA
	2. Sunt opusul circuitelor PROM:
		1. Au un nivel programabil AND
		2. Au un nivel predefinit OR
	3. Acestea sunt mai rapide decat PLA, dar are un numar limitat de termeni suma. Diverse subterfugii ? intre etapele de proiectare ajuta la minimalizarea acestui inconvenient.
5. **Circuite CPLD (Complex Programmable Logic Devices)**
	1. S-au cautat metode pentru definirea structurilor pentru a ingloba functionalitatile cu structura fizica mai mica, care functioneaza la viteze mai mari si sunt mai eficiente.
	2. Tehnologia CMOS a permis cresterea de dispozitive cu o densitate si complexitate foarte mare, la un cost redus de putere
	3. Conceptul initial a fost inbunatatit prin:
		1. Folosirea unui numar mai redus de conexiuni disponibile
		2. Utilizarea de unele softuri complexe pentru proiectare
	4. Structura generala consta in:
		1. Blocuri SPLD
		2. matricea comuna de interconectare
	5. Atat blocurile cat si conexiunile intre blocuri sunt programabile
6. **Tipuri de circuite ASIC (Application Specific Integrated Circuit)**
	1. **Gate Arrays ASIC** - au celula de baza ce contine tranzistori sau rezistente si fara conexiuni ?
	2. **Structured ASIC** - Au o matrice de celule de baza ($4 \times 4,8 \times 8,16 \times 16$)
	3. **Structured Cell ASIC** - Au biblioteci cu celule standard
	4. **Full Custom ASIC** - Au control total asupra fiecarei matrici

### Circuite logice fpga
1. **Circuitele ASIC** 
	1. Pot implementa functii complexe dar costurile de proiectare si implementare sunt foarte mari
	2. Nu pot fi reprogramate/ modificate (functionalitatile sunt fixe in siliciu)
	3. In 1981 compania Xilinx a creat primele circuite FPGA, bazate pe tehnologia CMOS si utilizand celule SRAM pentru configurare.
2. **Blocurile logice in circuitele FPGA**
	1. Inca de la inceput s-a folosit conceptul de **Lookup Table (LUT)**
	2. Intr-un LUT cu 3 intrari se implementau functii de 3 variabile din LUT sau o alta intrare
	3. Primele FPGA aveau un singur domeniu (frecventa) de ceas distribuit in tot circuitul
3. **Arhitectura circuitelor FPGA**
	1. Circuitele FPGA constau dintr-o matrice de blocuri logice, inconjurate de multe conexiuni
	2. Blocurile logice sunt interconectate printr-o schema de interconectare programabila
	3. Circuitele FPGA contin pini de intrare/iesire si pad-uri aferente acestora
	4. Matricea de interconectare are propriile celule de SRAM care permit programarea conexiunilor
	5. Aceste circuite au reusit sa umple golul existent intre PLD si ASIC deoarece
		1. Ofera programabilitate
		2. Pot implementa functii mari si complexe
		3. Ofera performante mult mai bine decat circuitul PLD
4. **Structuri hibride**
	1. Din punct de vedere al combinarilor celor 2 tipuri de implementari (FPGA si ASIC), distingem:
		1. Circuitele FPGA ce inglobeaza un circuit ASIC (functionalitate fixa si imposibil de actualizat)
		2. Circuitele ASIC ce inglobeaza blocuri FPGA : se includ blocuri FPGA intr-un circuit ASIC cu tehnologia Standard Cell
	2. Includerea cu blocuri FPGA in ASIC se incadreaza in Platform Design. Aceasta solute este folosita pentru extinderea compatibilitatii circuitelor ASIC
	3. Cele mai bune rezultate pentru implementarea ASIC-FPGA sunt oferite de procesele utilizate in circuitele Structured ASIC
5. **Modul de folosire al FPGA**
	1. Producatorii de circuite implementeaza circuitele utilizand
		1. Tehnologia Full Custom - tranzistorii sunt proiectati manual pentru optimizarea maxima a dimensiunilor si a vitezei
		2. Tehnologia Standard Cell - proiectarea se face pe celulele logice predefinite 
6. **Tipuri de tehnologii de realizare a FPGA**
	1. **Circuite FPGA bazate pe celule SRAM**
		1. Acest tip de circuite pot fi programate si reprogramate continuu
		2. Avantaje:
			1. Se pot redefinii functionalitatile implementate
			2. Se pot adauga noi functionalitati
			3. Se pot altera functionalitati
			4. Celulele SRAM folosesc aceeasi tehnologie CMOS ca si celulele elementare ale chip-ului
		3. Dezavantaje:
			1. Trebuies reconfigurate la fiecare pornire (punere sub tensiune)
			2. Informatia de programare trebuie reutilizata de fiecare data la pornire, motiv pentru care sunt necesare memorii auxiliare pentru stocarea acestei informatii
		4. Unele circuite FPGA au mecanisme de "bitstream encryption", adica informatia de configurare este criptata si decriptarea se face cu ajutorul celulelor stocate in interiorul FPGA intr-un registru special
		5. Dupa decriptarea informatiei, procesul de citire este blocat
	2. **Circuite FPGA bazate pe tehnologie cu legaturi antifuzibile**
		1. Programarea se face offline cu ajutorul unui programator special
		2. Avantaje:
			1. Sunt nonvolatile (nu se pierde informatia de configurare la oprire)
			2. Nu necesita memorie auxiliara
			3. Structura de interconectare este imuna la perturbatiile provocate de radiatia electromagnetica
			4. Informatia de configurare este stocata in adancul circuitului (astfel fiind protejata)
		3. Dezavantaje:
			1. Nu sunt reprogramabile (sunt OTP)
	3. **Circuitele FPGA bazate pe memorii EPROM, EEPROM si FLASH**
		1. Nu exista circuite FPGA bazate pe memorii EPROM, exista variante comerciale ce folosesc memorii EEPROM si FLASH 
		2. Aceste dispozitive sunt programate offline cu ajutorul unor dispozitive de programare
		3. Avantaje:
			1. Non-volatibilitatea
			2. Dimensiuni mai mici
			3. Intarzieri mai mici in logica de interconectare 
		4. Dezavantaje
			1. Fabricarea necesita 5 pasi suplimentari fata de CMOS
			2. Consumul de putere statica este mare (datorita numarului mare de rezistente "pull-up")
### Caracteristicile circuitelor logice fpga
1. **Tipuri de arhitecturi in circuitele programabile FLASH**
	1. Clasificarea se face in functie de granularitatea blocurilor logice:
		1. Arhitecturi FPGA cu granularitate mare (fine grained) - au numar de conexiuni mai mare
		2. Arhitecturi FPGA cu granularitate mica (coarse grained) - au numar de conexiuni mai mic si pot implementa functii complexe printr-o structura de noduri
2. **Modalitati de implementare a blocurilor logice**
	1. Implementarea blocurilor logice cu multiplexoare
		1. Exista arhitecturi logice FPGA ce utilizeaza blocuri logice programabile bazate pe multiplexoare (MUX)
		2. Implementarea functiilor in blocurile logice se face prin maparea pe structuri cu MUX
	2. Blocuri logice ce utiliuzeaza Lookup Table
		1. LUT-urile sunt mici blocuri de memorie SRAM ce stocheaza valorile functiei care trebuie implementata
		2. Prin intermediul intrarilor LUT se selecteaza adresa din blocul SRAM, iar continutul memoriei de la adresa respectiva este valoarea functiei,
		3. Maparea functiilor logice pe LUT-urile dispozitivului sufera de anumite inconveniente
			1. Pe un LUT cu 3 intrari se implica o functie logica cu 3 variabile (ideal)
			2. Daca se implementeaza o functie cu 2 intrari, unele celule SRAM din LUT raman neutilizate
			3. Functia globala nu poate fi fragmentata
		4. Unele implementari ale blocurilor logice selecteaza celulele SRAM prin intermediul portilor de transmisiune
		5. Portile de transmisiune controleaza propagarea informatiei la iesire
		6. Pe fiecare intrare sunt implementate porti de transmisiune activate pe logica pozitiva, cat si porti active pe logica negatiiva
		7. Cea mai mare parte a circuitelor FPGA moderne au blocuri logice bazate pe LUT
		8. Variabilele ce utilizeaza LUT au lanturi de transport rapid a informatiei
3. **Blocurile logice specifice circuitelor AMD-Xiliux**
	1. Logic cell (termen creat de compania Xiliux) reprezinta o structura LUT, un registru de tip D si un multiplexor care poate directiona la iesirea LogicCell datele din LUT trecute prin registru sau direct
	2. Registrul poate fi selectat sa functioneze ca bistabil D sau ca latch
	3. In functie de numarul de intrari, LUT poate implementa functii cu n variabile
4. **Modalitati de optimizare a implementarii functiilor logice**
	1. **Lanturi de transport a depasirii**
		1. Pentru implementarea functiilor de adunare/scadere, la nivelul CLB-urilor (CLB = Configurable Logic Block) s-au implentat lanturi rapide de transport a depasiii (carry chains)
		2. Ele pot functiona independent sau pot fi inlantuite pentru a realiza functii aritmetice de mari dimensiuni 
		3. Prin interconectarea lanturilor de transport se pot implementa operatii aritmetice foarte rapide cu operanzi de dimensiuni mari
	2. **Blocuri aritmetice predefinite**
		1. Folosite pentru implementarea functionalitatilor ce implica diverse calcule matematice
		2. Pentru cresterea performantelor s-au fabricat blocuri criterice predefinite: multiplicatoare si sumatoare
		3. Pentru implementarea algoritmilor de procesarea digitala a semnalelor s-au creat structuri predefinite MAC (Multiply and Accumulate)
5. **Nuclee de microprocesor in circuite logice programabile**
	1. **Ratiuni de utilizare a nuceelor de microprocesor**
		1. In proiectarea circuitelor digitale se foloseste conceptul de "HW-SW partitoning" => alegerea functionalitatii cevor fi executate de aplicatii software si functionalitatile implementate hardware
		2. FPGA moderne inglobeaza pe chip unul sau mai multe modele de microprocesor
		3. Exista unele implementari in siliciu ca blocuri predefinite si pot fi pozitionate separat de logica programata, dar nu pot fi modificate
	2. **Utilizarea de modele de tip soft core**
		1. Acestea sunt mai lente decat "hard macros microprocesor" si intreaga functionalitate va fi interpretata cu aceleasi procese de proiectare ca si restul logicii
		2. Avantajul este ca pot fi replicate si plasate in orice parte a chipului
		3. Exista si versiuni intermediare care au biblioteci de functii predefinite => firm microprocesor cores
6. **Semnale de ceas in FPGA**
	1. Pentru sincronizarea elementelor secventiale din circuitele FPGA se folosesc semnale de ceas distribuit in sistem
	2. Semnalul de ceas de referinta este furnizat din exteriorul circuitului FPGA si e legat la unul din pinii specializati ai FPGA-ului
	3. Clock-ul este confitionat in interiorul FPGA-ului si e distribuit intern catre elemente din logica programabila
	4. Pentru distribuirea uniforma si sincronizata se folosesc arbori de ceas (clock trees)
	5. Acesti arbori de ceas asigura distributia uniforma a clock-ului catre toate elementele de tip registru evitand decalajele (clock skews)
	6. Clock skews = situatii in care un registru primeste semnalul cu o anumita intarziere fata de alte celule registru
	7. In circuite moderne se folosesc mai multe domenii de ceas (de cele mai multe ori) => alte frecvente, defazaje, etc
	8. Pentru fiecare domeniu e implementat un arbore de ceas separat 
	9. In FPGA arborii de ceas sunt implementati utilizand trasee dedicate
7. **Control semnalelor de ceas**
	1. Controlul de ceas (clock manager) preia semnalul de ceas din exterior si pe baza lui creaza diferite semnale de ceas interne (acestia sunt propagati in logica prin intermediul arborelor de ceas)
	2. Logica de management al ceasului asigura conditionarea semnalului de ceas receptionat:
		1. Elimina jitter-ul (deviatiile de perioada ale clockului)
		2. Creaza semnale de ceas defazate
		3. Genereaza semnale de ceas cu diferite frecvente
		4. Elimina clock sckew
	3. FPGA-urile folosesc 2 tipuri de circuite pentru implementarea controlului de ceas
		1. PLL - Phase-Locked Loop
		2. DLL - Digital Delay-Locked Loop
8. **Functionalitatile predefinite Soft IP**
	1. Sunt functionalitati preimplementate, sunt optimizate pentru viteza si arie ocupata; numarul functionalitatilor depinde de familia de circuite aleasa
	2. IP-urile soft (Soft IP) sunt functionalitati furnizate utilizatorilor sub forma de cod RTL (descriere intr-un limbaj proiectare hardware)
	3. Utilizarea Soft IP au avantajul ca lasa la latitudinea proiectantilor folosirea lor sau nu (fata de "hard macros")
	4. Varianta Soft IP's este aleasa pentru functionalitati ce adreseaza o gama larga sau restransa de aplicatii
	5. Functionalitatile Soft IPs sunt parametrizabile, furnizatorul IP-ului oferind un cod ce poate fi configurat in functie de necesitatile utilizatorului
	6. Parametrizarea este facuta de regula cu ajutorul unor parametrii generici (utilizati in codul RTL)
9. **Pinii si bank-urile I/O**
	1. In functie de producator, FPGA-urile dispun de un numar de pini I/O
	2. Dispozitivele actuale ofera sute pana la peste o mie de porturi I/O
	3. Primii sunt grupati in bank-uri de I/O, iar numarul de bannk-urilor depinde de familia de circuite, de dimensiunea circuitelor si de numarul de pini I/O al capului circuitului
10. **Blocurile de I/O**
	1. Fiecare bank de I/O are in componenta de blocuri de I/O care leaga pinii de logica interna
	2. Blocurile contin buffere care permit folosirea pinilor ca port de intrare, iesire sau bidirectional (si intrare si iesire)
11. **Standarde de I/O suportate**
	1. Blocurile de intrare/iesire suporta diferite standarde de transmisie a datelor si diferite niveluri de tensiune
	2. Pentru FPGA, tensiunea de alimentare 1-0.9V la circuitele actuale
	3. Tensiunea de alimentare a pinilor este diferita de "core voltage"
	4. La circuitele actuale tensiunea de alimentare a pinilor de I/O este 1.2-3.3V
12. **Rezistente programabile**
	1. Blocurile de I/O permit utilizarea de rezistente pull-up si pull-down programabile
	2. Aceste rezistente implementeaza rezistivitati mari (50-100 $k\Omega$)
	3. Implementarea acestor rezistente se face cu ajutorul unor tranzistori de tip p legati la VCC (pt pull-up) si de tip n legati la masa (pentru pull-down)
13. **Transmisia diferentiala LVDS**
	1. LVDS este un standard de transmisie al datelor care foloseste 2 linii fizice
	2. Transmisia functioneaza la putere scazuta si permite transmisia datelor la viteze mari
	3. LVDS utilizeaza valoarea diferentei de tensiune intre cele 2 linii
14. **Interconectarea in circuite FPGA**
	1. In FPGA-urile bazate pe SRAM conexiunile intre blocuri logice si porturile de I/O sunt realizate prin intermediul liniilor de interconectare
	2. Liniile de interconectare folosesc noduri de interconectare programabile
	3. Structura liniilor de interconectare este matriceala si ierarhica
	4. Structura liniilor de interconectare ofera utilizatorului o rutare cat mai eficienta (rutarea se face automat, transparent)
15. **Matricea de interconectare programabila**
	1. Modurile de interconectare intre diferitele linii ale structurii de interconectare sunt implementate cu ajutorul unor tranzistori controlati prin intermediul unor celule SRAM
	2. Cu cat lungimea unei linii este mai mica, cu atat viteza de transmisie este mai mare
	3. Matricile de interconectare introduc la randul lor intarzieri in propagarea semnalelor
16. **Metrici de masurare a FPGA**
	1. Se foloseste notiuniea de "poarta echivalenta" pentru a putea compara implementarea functionalitatilor in FPGA in implementarile ASIC
	2. O poarta AND cu 2 intrari pe considera o poarta echivalenta ?
	3. Pentru masurarea implementarilor este indicat sa se masoare:
		1. Numarul de Logic Cells (pentru LUT cu 4 intrari)
		2. Numarul si dimensiunea blocurilor de Embedded RAM
		3. Numarul si dimensiunea elementelor aritmetice predefinite
		4. Numarul unitatilor de procesare predefinite
17. **Procesul de configurare a circuitelor FPGA**
	1. Pentru programarea FPGA-urilor, utilizatorii creaza fisiere de configurare in format binar, care sunt folosite in logica de programare => bitstream-uri
	2. Configurarea reprezinta procesul prin care in FPGA se incarca datele de programare specifice proiectului, datele ce definesc functionalitatea blocurilor logice interne ale circuitului precum si interconexiunile intre ele
18. **Configurarea FPGA bazate pe antifuzibile**
	1. Este nevoie de un dispozitiv de programare dedicat ce aplica implementarile la pinii de programare
	2. Pentru a ajunge la locatia antifuzibilului ce trebuie programat, pinii de programare implementeaza o schema de codificare a coordonatelor
19. **Configurarea FPGA bazate pe SRAM**
	1. Configurarea se face prin programarea tuturor celulelor SRAM folosite la implementarea functiilor logice precum si a celulelor care stabilesc interconexiunile
	2. Fiecare bit din bitstream defineste starea logica a unei celule de memorie SRAM din interiorul unui LUT
	3. Transmisia seriala este una lenta, iar configurarea sistemului poate dura foarte mult, daca circuitul are un numar mare de resurse
	4. Producatorii de FPGA au creat mecanisme de paralelizare pentru imbunatatirea vitezei de configurare
	5. Au creat registrii de deplasare de dimensiune redusa
	6. Au creat si frame-uri de celule SRAM, care sunt conectate in paralel la frame-ul cu bistabile D
20. **Modul de configurare Serial-Master**
	1. Este cel mai simplu mod de configurare
	2. Transferul datelor de configurare se face serial, prin intermediul unei singure linii de date legata la portul de configurare de intrare al FPGA-ului
	3. FPGA-ul activeaza ca master => controleaza transportul de date de configurare de la memoria externa
	4. FPGA-ul furnizeaza memoriei semnale de clock si reset
	5. Cand se incepe configurarea, FPGA-urile trebuie sa genereze un puls de reset, iar memoria va incepe sa transmita datele de configurare serial, pe fiecare tact de ceas
	6. FPGA-ul nu trebuie sa transmita informatie la adresa memoriei
	7. Memoria incepe sa transmita datele succesiv la primul bit pana la ultimul bit de configurare
	8. FPGA-ul dispuine de 2 pini de configurare, unul de 1 si unul de 0
	9. Pinul de intrare este folosit pentru receptionarea informatiei de configurare de la memoria externa
	10. Cel de iesire pentru citirea seriala al datelor de configurare ce au fost deja incarcate in circuit si transmisia informatiei de configurare
21. **Modul de config Serial-Slave**
	1. In acest mod de configurare circuitul FPGA nu are controlul configurarii
	2. Datele de configurare sunt furnizate serial de catre un Master, care poate fi un procesor, un alt dispozitiv ce implementeaza logica de transfer a configurarii sau de alt circuit FPGA (cand sunt inlantuite in Daisy Chain)
	3. Circuitul Master este responsabil de controlul configurarii si furnizeaza ceasul si datele de configurare
	4. Circuitul Master va prelua datele de configurare de la memorie sau prin intermediul unui alt periferic si le va transmite catre circuitul FPGA
	5. ![[Pasted image 20240614135808.png]]
22. **Modul de configurare Paralel-Master**
	1. Este similar cu Serial-Master, se foloseste o memorie externa pentru stocarea datelor de configurare, insa acestea sunt citite de catre circuitul FPGA printr-o interfata paralela
	2. FPGA-ul trebuie sa furnizeze adresa de memorie la care este stocata fiecare data de configurare
	3. Adresa furnizata memoriei e generata de logica de control a configurarii din FPGA
	4. Aceasta e generata pe baza unui numarator cu adrese
	5. Pentru receptia paralela a datelor de configurare, FPGA au implementat modalitati de transfer paralel a datelor receptionate de catre lanturile de bistabile
23. **Modul de configurare Paralel-Slave**
	1. E similar cu mediul de configurare serial cu FPGA cu slave, astfel necesita un dispozitiv extern ce actioneaza ca master si controleaza configurarea
	2. Masterul citeste datele de configurare de la o memorie externa sau de la un dispozitiv periferic, dupa care le transmit FPGA-ului
	3. Acest mod de configurare reprezinta o solutie frecventa pentru ca multe sisteme contin pe langa FPGA, unul sau mai multe microprocesoare
	4. Microprocesoarele au acces la memorie de pe cablajul imprimat si dupa ce s-a finalizat configurarea FPGA-ului se pot utiliza pentru restul activitatilor pentru care au fost incluse in sistem
### Factori ce influenteaza comportamentul circuitelor digitale
1. **Circuitele CMOS**
	1. Acestea sunt circuite electronice digitale ce folosesc semnale electrice care reprezinta valori discrete de tensiune
	2. Valorile discrete se reprezinta valori logice si numerice ale informatiei
	3. Spre deosebire de circuitele analogice se utilizeaza semnale ce variaza continuu, circuitele digitale folosesc valori discrete ale tensiunii pentru a reprezenta cele 2 niveluri logice, astfel aceste valori sunt folosite de circuite digitale pentru implementarea operatiilor de logica booleeana
	4. Avantaje:
		1. Consum scazut de putere statica 
	5. Tranzistorii de tip n conduc sarcina, iar cei de tip p golurile, astfel functionalitatea lor este complementara
	6. Tranzistorul de tip n intra in conductie la aplicarea unei tensiuni la terminalul portii, iar tranzistorul de tip p intra in conductie cand terminalul portii (gate) este tras la masa (sau la o tensiune mica, care corespunde cu nivelul 0)
	7. Din punct de vedere functional, tranzistorul MOS functioneaza ca niste comutatoare 
	8. Tranzistorii de tip n si p sunt folositi pentru implementarea protilor logice in circuite digitale
2. **Fan-In/Fan-Out**
	1. In terminologia ASIC (dar la fel sunt folosite si in cazul circuitelor FPGA) capacitatile porturilor de intrare si iesire sunt denumite fan-in si fan-out 
	2. Pentru o poarta logica, fan-in reprezinta capacitatea unui pin de intrare 
	3. Fan-out reprezinta capacitatea maxima pe care un pin de iesire o poate controla (daca bine-nteles poarta logica este alimentata la nivelul de tensiune corespunzator unuia din nivelulrile logice LOW si HIGH)
	4. ![[Pasted image 20240614135602.png]]
	5. Nota : intotdeauna fan-out este de mai multe ordine de marime mai mare decat fan-in (fan-out >> fan-in) 
	6. fan-out si fan-in masoara numarul de conexiuni ce pot fi realizate intre portile logice:
		1. fan-in caracterizeaza numarul de intrari
		2. fan-out caracterizeaza numarul maxim de porti logice ce pot fi conectate la o iesire 
	7. La FPGA-uri fan-in depaseste numarul de utilizari ale unui bloc logic si fan-out depaseste numarul de porti ce pot fi conectate la iesirea blocului
	8. Fan-out max reprezinta numarul maxim de conexiune care se pot realiza la iesirea unui bloc logic
	9. In implementarile FPGA iesirea unui bloc va fi conectata la un traseu de interconectare care va fi conectat la alte blocuri
	10. Se foloseste traseul fan-out-net pentru calcularea numarului total de intrari ale traseului respectiv
	11. Traseele ce transporta semnale de ceas, reset sau actionare (enable) sunt trasee cu intoarcere mare (high fan-out-nets)
	12. Exista metode de optimizare alea high fan-out nets
		1. Duplicarea registrilor
		2. Replicarea driverelor
		3. Buffer-area semnalelor de ceas
3. **Puterea de conductie**
	1. Defineste puterea furnizata de o poarta logica
	2. Cu cat aceasta putere este mai mare, cu atat creste numarul portilor pe care le poate conecta la portul /porturile sale de iesire 
	3. Puterea de conductie este legata de capabilitatea portii de a incarca/descarca capacitatea vazuta la iesirea sa
	4. Timpul de propagare e dat de constanta RC
	5. Portile de putere de conductie mai mare au timp de propagare mai mic
	6. In FPGA puterea de conductie a blocurilor logice nu este controlata de catre utilizator
	7. Acesta poate controla doar puterea de conductie a bufferelor de iesire
	8. Acest lucru asigura interfatarea corecta a circuitelor externe de pe cablajul imprimat, astfel ating parametrii corespunzatori de transmisie a datelor
4. **Rezistentele de pull-up si pull-down**
	1. Acestea sunt folosite pentru fortarea unui port I/O la o anumita stare logica (0=low;1=high)
	2. Aceste rezistente sunt folosite pentru a preveni oscilatia unui port atunci cand acesta nu este conectat
	3. Pull-up "trage" valoarea interna la "weak high"
	4. Pull-down "trage" valoarea interna la "weak low"
	5. Aceste rezistente pot fi realizate in interiorul circuitului integrat sau extern
5. **Programarea semnalelor in FPGA**
	1. **Timpii de tranzitie**
		1. Tranzitia intre low si high sa invers se face prin trecerea tensiunii de la valoarea asociata starii low la valoarea asociata starii high si invers
		2. Exista anumite paje de tensiune ce corespund nivelului high si nivelului low (in functie de nivelul de tensiune la carre e alimentat circuitul)
		3. Plaja cuprina intre bana corespunzatoare nivelului low si tensiunea corespunzatoare nivelului high este numita plaja invalida
		4. Timpul de crestere (rise time) este timpul in care trece de la starea low la cea de high
		5. Timpul de descrestere (fall time) este timpul in care trece de la starea high la cea de low
	2. **Viteza de tranzitie (slew rate)**
		1. Reprezinta viteza de schimbare a unei tensiuni in unitatea de timp si se calculeaza ca $\frac{dv}{dt}$
		2. In circuite digitale aceasta reprezinta viteza de transmisie de la low la high sau invers
		3. In cazul pinilor configurati ca fast slew rate pins, acestia pot transmite la exterior semnale tranzitorii nedorite (glitch-uri)
	3. **Tipuri de propagare**
		1. Tipul de propagare al unui semnal printr-o poarta logica depinde de intarzierea interna cat si de intarzierile externe
		2. Intrazierile interne reprezinta impul de propagare in interiorul portii
		3. Intarzierile externe sunt legate de numarul si natura conponentelor logice pe care poarta le poate comanda
		4. Timpii de propagare sunt dependenti de temperatura si valoarea tensiunii de alimentare
		5. Acestia au o caracteristica logaritmica raportat la tensiunea de alimentare
6. **Bufffere 3-state asociate porturilor**
	1. Aceste buffere sunt utilizate pentru decuplarea porturilor de iesire atunci cand sunt conectate la o magistrala de date
	2. Prin interiorul acestor buffere se permite trecerea unui port de 0 in stare de HiZ (inalta impedanta) (nu se influenteaza starea logica a magistralei )
	3. La magistrala de date (unde se utilizeaza circuite ce folosesc 3-state), cand toate circuitele conectate la magistrala au iesirile inactive, liniile de date vor ramane flotante, pentru a preveni aceasta, liniile magistrale vor fi legate prin rezistente de pull-up sau pull-down
	4. Circuitele de tip bus holder sunt utilizate pentru a mentine ultima valoare scrisa pe magistrala de date prin utilizarea unor structuri de tip latch realizat cu inversoare.
7. **Glitch-uri si hazard logic**
	1. Glitch-urile sunt stari nedorite ale semnalelor aparute in urma tranzitiei dintre 2 stari dorite
	2. Sunt semnale de tip puls de scurta durata
	3. De obicei se produc datorita conditiilor de concurenta a semnalelor ce se propaga pe cai diferite
	4. In circuite combinationale, glitch-urile se pot acumula odata cu cresterea numarului de niveluri logice
	5. Hazardul logic este un efect nedorit, in care comutarea intrarilor unui circuit produce stari temporare incorecte la iesire
	6. Acesta poate produce glitch-uri
	7. Este de 3 tipuri:
		1. Static
		2. Dinamic
		3. Functional
	8. Hazardul static reprezinta schimbarea starii logice la iesire de q ori la rand (iesirea ar fi trebuit sa ramana constanta)
	9. Hazardul dinamic reprezinta schimbarea temporara a starii logice la iesire de mai multe ori la rand (ar fi trebuit sa se schimbe doar odata)
	10. Hazardul functional este hazardul implicat la schimbarea simultana a mai multor intrari (dificil de eliminat)
	11. Hazardul poate fi eliminat prin introducerea de elemente auxiliare
	12. Hazardul nu afecteaza circuitele sincrone
	13. Memoriile ssunt sensibile la glitch-uri
8. **Asigurarea sincronicitatii in circuitele digitale**
	1. Circuitele digitale sunt formate din elemente de logica combinationala (porti logice si mux-uri) si elemente de logica secventiala (bistabile si latch-uri)
	2. Sincronicitatea circuitelor este asigurata prin folosirea semnalelor de ceas
	3. Semnalele de ceas sunt semnale periodice care definesc momentele de timp la care valorile de iesire ale functiilor booleene sunt incarcate in celule de memorie
	4. Functionalitatea circuitului este compusa din logica combinationala si elemente de memorie
	5. In circuite ASIC sunt folosite cel mai des elemente de memorie ce utilizeaza bistabile de tip D si latch-uri
	6. Latch-urile esantioneaza data de instrare pe palierul semnalului de ceas (pe durata palierului de 1 sau de 0 depinde de implementare)
	7. Bistabilul de tip D esantioneaza data de la intrare pe frontul semnalului de ceas; pe semnalul de ceas, acesta copiaza valoarea intrarii (D) la iesire (Q); din punct de vedere constructiv/structural e alcatuit din 2 latch-uri
	8. FPGA-urile sunt circuite digitale sincrone si folosesc celule de memorie ce pot fi configurate ca latch sau ca bistabil de tip D
	9. Toate elementele de logica secventiala conectate la acelasi semnal de ceas se spune ca fac parte din acelasi domeniu de ceas; Acestea vor esantiona intrarile in acelasi moment, deci au aceeasi frecventa
9. **Parametrii temporali ai bistabilului D**
	1. Exista 3 parametrii:
		1. Timpul de set-up
		2. Timpul de hold
		3. Timpul de propagare
	2. Datele de intrare trebuie sa fie stabile inainte si dupa aparitia unui front de ceas
	3. Timpii de set-up si hold sunt specifici tehnologiei cu care se implementeaza bistabilele
	4. Valorile de set-up si hold pot varia de la cateva picosecunde la cateva nanosecunde
10. **Semnale de ceas si reset**
	1. **Distributia semnalului de ceas**
		1. Arborele de distributie a ceasului asigura distribuirea balansata a semnalului de ceas catre registrii ce il utilizeaza
		2. Pentru o functionare corecta a unui sistem, arborele de ceas trebuie sa fie corect implementat si balansat corespunzator
		3. Arborele de ceas foloseste buffere pentru a implementa o structura arborescenta de distributie a semnalului de ceas catre toate elementele de logica secventiala
	2. **Defazajul semnalului de ceas (clock skew)**
		1. Reprezinta defazajul ceasului intr-un anumit punct de pe circuit raportat la ceasul sursa
		2. Apare datorita dezechilibrelor din arborii de ceas
		3. Exista 2 tipuri de clock skew:
			1. Clock skew pozitiv: cand registrul ce transmite date primeste ceasul cu intarziere fata de registrul ce receptioneaza
			2. Clock skew negativ: cand registrul ce transmite primeste ceasul inaintea registrului ce receptioneaza datele
		4. Deoarece frecventa circuitului nu poate fi scazuta pentru a elimina incalcarea timpului de hold, clock skew negativ este considerat mai periculos decat clock skew pozitiv
	3. **Jitter-ul semnalului de ceas**
		1. Este un fenomen care apare in circuite digitale care reprezinta o instabilitate temporala a fronturilor de ceas
		2. Principalele surse ale jitter-ului sunt:
			1. Generatoarele de semnal de ceas de pe circuit
			2. Bufferele in arborele de distributie a ceasului
			3. Conditiile de operare
		3. Deviatia cea mai mare fata de ceasul sursa se numeste absolute jitter
11. **Metastabilitatea**
	1. Reprezinta o disfunctionalitate a circuitelor digitale
	2. Daca nu sunt respectati timpii de set-up si hold (data de intrare isi modifica valoarea in acest interval) bistabilul D poate intra in metastabilitate
	3. La finalul perioadei de instabilitate, bistabilul se va stabiliza la una din starile logice 0 sau 1 (nu se stie la care)
	4. Durata perioadei de metastabilitate e aleatorie si depinde de cum este implementat bistabilul in siliciu
	5. Metastabilitatea apare cand:
		1. Nu sunt respectate conditiile de set-up si hold
		2. Semnalele de intrare sunt asincrone sau cand datele de intrare sunt receptionate din alt domeniu de ceas
		3. Cand apare clock skew sau cand panta de crestere sau descrestere a ceasului este mai mare
		4. Intarzierile prin logica combinationala
	6. Pentru calcularea probabilitatii de operatie a metastabilitatii la bistabile D, se foloseste metrica MTBD (Mean-Time Between Faliure)
	7. Formula de calcul tine cont de:
		1. Frecventa de combinare a datelor de intrare
		2. Frecventa de lucru a bistabilului
		3. Timpul de recuperare
		4. Constante se tin de implementare si de conditiile de operare
	8. MTBD scade cu cat timpul de recuperare este mai mare si cu cat frecventa de schimbare este mai mare
	9. Pentru reducerea probabilitatii de aparitie a metastabilitatii, in etapa de proiectare se introduc elemente de circuit, care se numesc sincronizatoare, pe traseul datelor ce vin din alte domenii de ceas sau vin complet asincron
12. **Mascarea semnalului de ceas (clock gating)**
	1. Tehnica mascarii semnalului de ceas se foloseste in circuite digitale, reducerea consumului inutil de putere
	2. Aceasta tehnica foloseste un semnal de control (enable) pentru a valida semnalul de ceas ajunge la componentele secventiale
	3. In practica este indicat sa se sincronizeze mai intai semnalele de validare
	4. Tehnica mascarii ceasului are ca scop reducerea consumului inutil de putere prin semnalul de control (enable)
	5. Mascarea se face doar cu celule tehnologice specializate
13. **Domeniile de ceas**
	1. Sunt zone din circuit in care elementele de logica secventiala functioneaza pe un anumit semnal de ceas, cu o anumita frecventa si o anume faza
	2. Pentru prevenirea metastabilitatii si pentru esantionarea corecta a semnalelor ce provin dintr-un domeniu A intr-un domeniu B se folosesc tehnici de Clock Domain Crossing (cand se trece dintr-un domeniu de ceas mai rapid intr-unul mai lent, pulsurile se latesc)
	3. Se foloseste sincronizare pentru prevenirea metastabilitatii (2 sau mai multe bistabile ce functioneaza pe ceasul de receptie)
	4. Pentru sincronizarea transmisiei de date intre domenii de ceas se utilizeaza tehnici si semnale de land shake
14. **Utilizarea resetului**
	1. Se recomanda folosirea semnalelor de reset sincrone cu ceasul, deoarece cele asincrone pot conduce la metastabilitate
	2. Cand se folosesc semnale de reset ce vin din exteriorul circuitului se recomanda utilizarea sincronizatoarelor
15. **Consumul de putere**
	1. Puterea consumata de circuitul digital reprezinta uunul dintre cele mai importante aspecte in functionalitatea si aplicabilitatea produselor in carre circuitele digitale vor fi utilizate
	2. Acesta are impact direct asupra temperaturii circuitului, deci si a cantitatii de caldura eliberata de circuit in exterior
	3. Circuitele digitale utilizeaza CMOS care are 2 componente de putere:
		1. Puterea statica
		2. Puterea dinamica
	4. **Puterea statica**
		1. Este puterea consumata de circuit cand nici intrarile si nici iesirile nu comuta (sunt in stare stabila 0 sau 1)
		2. Desi nu comuta, exista curenti care se scurg prin tranzistorii MOS
		3. La tehnologiile vechi puterea statica este neglijabila
	5. **Puterea dinamica**
		1. Atunci cand sunt in comutatie, tranzistorii CMOS consuma aceasta putere pentru a incarca capacitatile interne si capacitatile interconexiunilor 
		2. Un ciclu de comutare low-high-low va consuma puterea dinamica $P=f \cdot C \cdot V_{dd}^{2}$
		3. Componentele circuitelor digitale nu comuta la fel de des, motiv pentru care s-a introdus un paramentru de comutatie $\alpha$
		4. Formula puterii dinamice determina valoarea totala a puterii dinamice consumate de circuitul digital, adica este suma puterilor dinamice consumate de portile logice in comutatie
16. **Reducerea consumului de putere**
	1. Proiectantii de circuite digitale pot reduce doar puterea dinamica pe care o vor consuma viitorul circuit
	2. FPGA-urile consuma mai multa putere deoarece au componente logice ce permit programabilitatea
	3. Modalitati de reducere a consumului de putere:
		1. Reducerea tensiunii de alimentare
		2. Eliminarea glitch-urilor
		3. Reducerea etapelor de calcul astfel incat sa se scada nivelul de activare in functii logice
		4. Optimizari ale functiilor ce trebuie implementate
		5. Reducerea fan-out-ului
		6. Reducerea frecventei de functionare
		7. Mecanisme de clock gating
### Proiectarea utilizand circuite programabile
1. **Fluxul de proiectare ASIC**
	1. Principalele etape in proiectarea unui ASIC sunt:
		1. **Design entry (descrierea proiectului)**: Este modalitatea prin care proiectantii descriu functionalitaea circuitului proiectat (prin reprezentari schematice, limbaje HDL, blocuri de proprietate intelectuala, limbaje de nivel inalt (C/C++, SystemC, Matlab/Simulink))
		2. **Sinteza logica** : Reprezinta procesul prin care functionalitatea este transformata intr-o reprezentare de celule logice si conexiuni intre acestea
		3. **Partitionarea sistemului** : In aceasta etapa sistemul proiectat este impartit in blocuri functionale si functionalitatile sunt impartite intr-o ierarhie de module, ierarhie care cumuleaza cu modulul de top
		4. **Floorplan-ul** : Scopul acestuia este sa nu ramana spatii neutilizate pe chip si sa pozitioneze modulele ce comunica intre ele astfel incat sa se micsoreze traseele de interconectare evitand congestiile
		5. **Plasarea**: In aceasta etapa celulele rezultante in urma sintezei logice sunt plasate pe suprafata chip-ului, tinand cont de incarcarile pe traseele de interconectare (interconexiune)
		6. **Rutarea**: Rutarea se face in 2 pasi: rutarea globala (se definesc retele) si rutarea in detaliere (realizarea conexiunilor)
		7. **Extragerea parametrilor de circuit**: Parametrii fizici ai sarmelor sunt folositi pentru calculul intarzierilor in etapa de simulare post implementare
2. **Fluxul de proiectare utilizand FPGA**
	1. Principalele etape in proiectarea unui ASIC sunt:
		1. **Design entry (descrierea proiectului)**: Cea mai frecventa modalitate de design entry este utilizarea unei descrieri in limbajul HLD 
		2. **Sinteza logica** : Reprezentarea functionalitaii este translatata intr-o reprezentare cu porti logice si conexiuni intre acestea. La finalul etapei de sinteza logica rezulta fisiere netlist si rapoarte de sinteza
		3. **Implementarea**: Inglobeaza plasarea si ruratea. Intrarile etapei de implementare sunt netlist-urile rezultate in etapa de sinteza logica si constrangerile de arie si timp
		4. **Generarea sistemului**
3. **Proiectarea schematica**
	1. Aceasta este o metoda de reprezentare grafica a functionalitatii, utilizand porti logice si conexiuni intre ele
	2. Cu ajutorul uneltelor de proiectare (schematic capture) se deseneaza structura logica a functionalitatii
	3. Este de mentionat faptul ca este dificil de proiectat un sistem complex, de dimensiuni mari
	4. De asemenea, este dificil si depanarea sistemului
4. **Proiectarea bazata pe limbajele HDL (Hardware description languages)**
	1. Sunt limbaje create pentru a descrie functionalitatea hardware
	2. Acestea permit descrierea functionalitatii circuitelor digitale la diferite niveluri de abstractizare
		1. Nivel structural (reprezentat la nivel de poarta logica)
		2. Nivel functional (reprezentat de functiile logice si de registrii)
		3. Nivel comportamental (reprezentat de comportamentul unui circuit folosind bucle, procese, ecuatii ce descriu operatii)
	3. Aceste limbaje ofera niveluri de flexibilitate si productivitate mult mai mari
5. **Limbajul Verilog**
	1. Permite modelarea comportamentului la diferite niveluri de abstractizare
6. **Limbajul VHDL**
	1. Permite descrierea functionalitatii la nivel functional si comportamental
7. **Proiectarea folosind limbaje de nivel inalt**
	1. C/C++, Matlab/Simulink
	2. System C a aparut ca o extensie a C++, cu capacitati de modelare a logicii hardware similara cu HDLS
	3. Acest limbaj ofera principalele constructii de limbaj pentru modelarea logicii hardware:
		1. Elemente structurale
		2. Tipuri de date: module, porturi, interete, canale
		3. Canale de comunicatie: tipuri logice cu 4 stari, bit vectors, tipuri integer
		4. Elemente de control ale proceselor: semnale, structuri FIFO, semnale de ceas

### Simularea si verificarea functionala
1. **Verificarea functionala**
	1. Acest proces stabilesste corectitudinea functionarii unui circuit digital in etapa de proiectare
	2. Se compara descrierea circuitului (in format `HDL`) cu o alta descriere, comportamentala, de nivel inalt
	3. Circuitul care trebuie verificat este circuitul DUT (Device Under Test)
	4. Descrierea DUT-ului este de obicei la nivel RTL, reprezentat dprin elemente simple (porti logice,bistabile)
	5. DUT-ul este inglobat intr-un mediu de verificare (Testbench) si este verificat cu ajutorul simulatoarelor
	6. Metodele de verificare clasice folosesc medii de verificare descrise tot in limbaje de descriere hardware (`VHDL`, `Verilog`), iar cele moderne folosesc limbaje dedicate verificarii (`HVL`) - `C`, `SystemVerilog`
	7. Peste 50% din timpul dedicat proiectarii este alocat verificarii functiilor
	8. Verificarea functionala se bazeaza doar pe specificatii si testeaza design-ul ce un blackbox
	9. In proiectele mari se folosesc sisteme de bug tracking
2. **Planul de verificare**
	1. In aceasta etapa se stabilesc si detaliile de lucru in cadrul proiectului 
	2. Acestea pot consta in:
		1. Structura directoare
		2. Formatul documentelor, maniera de scriere a codului (coding style)
		3. Elemente ce vor fi testate
		4. Sistemul de control al versiunilor ce va fi utilizat
3. **Verificarea folosind simularea (tehnica simularii)**
	1. Aceasta tehnica implica utilizarea uneltelor de software `EDA` de simulare
	2. Verificarea codului `RTL` se face fara modelele de intarziere asociate portilor si sarmelor
	3. Utilizarea informatiilor ingreuneaza simularea
	4. In simularea comportamentala `RTL` spatiul vectorilor de test se restrange pe masura ce se urca in ierarhia circuitului, deoarece creste numarul de combinatii posibile si nu se mai poate aborda exhaustiv verificarea unui bloc logic
	5. Testele se organizeaza in registrii de teste, iar acestea sunt intotdeauna rulate in batch-node (mod consola, fara GUI)
4. **Etapele verificarii functionale**
	1. Verificarea blocurilor simple poate fi facuta de proiectantii blocurilor respective 
	2. Se pot utiliza parti din testbench-ul intregului sistem sau testbench-uri simple pentru a verifica functionalitatea de baza
	3. Se utilizeaza simularea proiectului, respectandu-se planul de verificare prestabilit, iar planul de verificare poate fi imbunatatit pe masura ce se detecteaza cazuri nedorite
	4. La nivelul de chip/sistem se executa un numar redus de teste (se verifica daca componentele chip-ului/sistemului sunt corect interconectate si functionalitatea in ansamblu este indeplinita)
	5. Dupa rularea testelor se colecteaza datele de acoperire; dupa analiza acestora, daca se constata ca gradul de acoperire nu este cel dorit, se pot defini teste sau scenarii suplimentare
	6. Code Coverage $\to$ analizeaza fiecare linie de cod din circuitul logic (`DUT`)
	7. Functional Coverage $\to$ analizeaza `DUT-ul` si testbench-ul din punct de vedere functional
	8. Dupa rularea acestora sunt incluse in liste de regresie care trebuiesc rerulate ulterior
5. **Limbajele folosite in verificarea functionala**
	1. Pentru verificare sunt utilizate atat limbajele de proiectare (`VHDL`,`Verilog`) cat si limbajele dedicate verificarii (`HDL` - Hardware Verification Language): `C`, `SystemVerilog`, `SystemC`
	2. Pentru asertii sunt folosite `PSL`, System Verilog Assertions (`SVA`)
	3. Limbajele de verificare sunt [[Programarea orientata pe obiecte|orientate pe obiecte]] sau au aspect oriented (de exemplu limbajul `C`) si au constructii pentru definirea constrangerilor, a punctelor de acoperire functionala, a asertilor complexe, ofera suport pentru generarea aleatoare de stimuli (random generation)
	4. Pentru testbench-uri simple se pot utiliza cu succes `VHDL` sau `Verilog`, insa pentru cele mai complexe, limbajele sunt limitate
	5. Mediile de verificare moderne sunt bazate pe limbajele de verificare
6. **Mediul de verificare**
	1. Testbench-ul reprezinta un mediu construit in jurul `DUT`-ului pentru a verifica functionalitatea acestuia prin simulare
	2. Acesta consta din componente de verificare care sunt create folosind limbaje de proiectare hardware (`Verilog`,`HDL`) sau limbaje dedicate verificarii (`SV`,`C`,`SystemC`)
	3. Un testbench este format din:
		1. Elemente generatoare de trafic catre `DUT`
		2. Elemente de interconectare cu `DUT`-ul
		3. Elemente de monitorizare
		4. Elemente de analiza a raspunsurilor
		5. Elemente de masurarea acoperirii functionale prin procesul de verificare 
		6. Elemente de raportare si verificare
	4. Cerintele unui mediu de verificare sunt urmatoarele:
		1. Flexibilitate: sa poata crea diferite scenarii de verificare, cu modificari minime aduse mediului de verificare
		2. Extensibilitate: sa permita adaugarea sau extinderea componentelor
		3. Reutilizabilitate: sa permita crearea de medii de verificare care pot fi folosite mai tarziu si in alte proiecte cu efort minim
7. **Componentele unui mediu de verificare**
	1. **Generatorul de trafic**
		1. Acesta creaza secvente de stimuli care se mai numesc vectori de test
		2. Datele generate, tipul si numarul secventelor pot fi valori aleatoare sau predefinite
	2. **Constrangerile**
		1. Ele disectioneaza generarea de stimuli restrangand plaja de valori aleatoare la cazurrile de interes
	3. **Interconectarea cu `DUT`-ul**
		1. Se realizeaza prin intermediul unor module ce transforma traficul generat in semnale pentru a fi aplicate intrarilor `DUT`
		2. Impelemntarea protocolului de comunicatie cu `DUT`-ul
	4. **Monitorul**
		1. Acesta preia semnalele de la porturile de iesire ale `DUT`-ului, dupa care, verifica daca s-a respectat protocolul de transmisie si transmite datele receptionate pentru verificarea si analiza de acoperire
	5. **Modelul de referinta**
		1. Acesta implementeazaq un model comportamental al `DUT`-ului
		2. El genereaza raspunsurile corecte pe care `DUT` ar trebui sa le intoarca la stimuli de intrare generati
	6. **Verificarea functionalitatii**
		1. Se face prin comportarea rezultatelor obtinute cu cele asteptate, provenite de la modelul de referinta
		2. Se transmit mesaje de eroare sau warning-uri cand apar diferente intre raspunsul `DUT`-ului si datele de referinta
	7. **Acoperirea functionala**
		1. Colecteaza datele de acoperire functionala obtinute prin procesul de verificare
		2. Nivelul de acoperire al codului este colectat automat de simulator ce creaza ulterior rapoartele de acoperire
8. **Verificarea formala**
	1. Este o metoda de verificare a functionalitatii unui circuit digital care foloseste metode matematice de analiza si unelte software dedicate pentru aceasta 
	2. Analiza formala utilizeaza metode matematice de reprezentare a [[Bazele teoretice ale circuitelor logice|logicii booleene]] si analiza matematica a functionalitatii (`SAT`)
	3. Analizatorul formal incearca sa demonstreze ca o anumita presupunere este falsa
	4. Pentru utilizarea ulterior de `FV` (Formal Verification) au fost create limbaje de asertii (`PSL` si `SystemVerilog`) si `VHDL` are constructia "assert"
	5. Prin aceasta metoda se pot identifica uneori mult mai rapid erorile dintr-un circuit
9. **Utilizarea asertilor**
	1. Asertiile sunt derivatii ale intentiei de proiectare si se pot insera in codul `RTL` sau in fisiere externe
	2. Cu ajutorul lor se pot identifica erorile direct la sursa
	3. Sunt utilizate des in automatele cu mai multe stari (care sunt mai greu de controlat)
10. **Erori de functionalitate**
	1. Erori de specificatii - specificatii incorecte sau incomplete, schimbari dese ale specificatiilor, planuri de verificare incomplete
	2. Erori de proiectare - implementarea in mod eronat a functionalitatii
	3. Medii de verificare incomplete sau incorecte - cresterea complexitatii `DUT`-ului duce la imposibilitatea anticiparii tuturor cazurilor posibile
	4. Reutilizarea modulelor din alte proiecte sau utilizarea modulelor `IP` - module cu erori nedectate sau incorect inglobate in noul proiect

### Implementarea proiectelor utilizand clp-uri
1. **Constrangerile, tipurile si modalitatile de definire**
	1. Constrangerile reprezinta circuite pe care uneltele software dedicate trebuie sa le respecte in procesul de implementare a FPGA-urilor 
	2. Acestea pot fi definite prin intermediul:
		1. Fisierelor de constrangeri
		2. Fisierelor de comenzi 
		3. Fisierelor de definire a constrangerilor in GUI a uneltelor software dedicate
	3. Producatorii de unelte software pentru implementarea FPGA utilizeaza formate proprietare de fisiere de constrangeri; aceste unelte software pun la dispozitia utilizatorului modalitati grafice de definire a a constrangerilor
	4. Constrangerile acceptate de uneltele software de implementare FPGA sunt de 2 tipuri:
		1. Constrangeri de timp: folosite inca din etapa de sinteza logica
		2. Constrangerile de implementare fizica: folosite in etapa de mapare,plasare si rutare
	5. Tipurile de constrangeri care pot fi aplicate sunt:
		1. Constrangeri asupra semnalelor de ceas
		2. Constrangeri de viteza de propagare a datelor de la pinii de intrare la celulele registru
		3. Constrangerile de viteza de propagare de la pinii de $1$ la pinii de $0$ trecand doar prin logica combinationala
		4. Constrangerile de plasare a blocurilor logice, a IP-urilor, a memoriilor sau a blocurilor aritmetice
		5. Constrangerile de alocare a pinilor dispozitivului la semnale de intrare
	6. Tipuri de analiza a implementarii:
		1. Analiza de timing
		2. Analiza implementarii fizice
2. **Analiza timpilor de propagare (analiza de timing)**	
	1. Pentru furnizarea retelelor de timing, unelte software implementeaza algoritmi de Static Timing Analysis (`STA`)
	2. Acesti algoritmi sunt utilizati pentru calculul timpilor de propagare necesari semnalelor de date in raport cu semnalele de ceas diferite de dezvoltator
	3. Timpii sunt calculati pe baza timpilor de propagare a componentelor utilizate
	4. Pentru raportarea de catre `STA`, sunt folositi anumiti termeni (ex: required time, arrival time, slack)
	5. Required time reprezinta timpul maxim pe care il poate consuma o cale de date pentru a ajunge la celula registru destinatie
	6. Arrival time reprezinta timpul efectiv la care o data ajunge la celula registru destinatie
	7. Slack reprezinta diferenta intre timpul maxim necesar ca o data sa ajunga la destinatie si timpul efectiv la care ea ajunge
	8. Analizele de timing se fac folosind valorile maxime de timp de propagare (max delay) sau folosind valorile minime de timp de propagare (min delay)
	9. Pentru analiza cailor de date se utilizeaza analiza max delay (din perspectiva respectarii timpului de set-up a datelor registru)
	10. In analiza max delay se verifica si timpii de recovery ai bistabililor
	11. Recovery time reprezinta timpul minim necesar intre dezactivarea semnalului de reset si frontul de ceas, pentru a nu genera metastabilitate 
	12. Cu ajutorul analizei de timing se obtin informatii despre caile de date:
		1. Numarul si natura cailor de date dintr-un anumit domeniu de ceas
		2. Caile critice care au cel mai mare timp de propagare
		3. Caile ce au o derivatie de timp, sub o anumita valoare
		4. Caile cu deviatia cea mai mare a timpilor de set-up
		5. Caile cu derivatia cea mai mare a timpilor de hold
3. **Analiza implementarii fizice**
	1. Dupa implementarea fizica, pentru generarea rapoartelor se pot folosi diverse metrici de analiza a implementarii (utilizarea resurselor, a congestiilor)
	2. Aceste metrici pot fi activate (prin intermediul GUI a software-ului pentru implementare FPGA ) si pe baza lor se vor genera rapoarte de analiza a implementarii fizice
	3. Metricii de analiza pot fi:
		1. Utilizarea LUT-urilor
		2. Utilizarea blocurilor logice
		3. Utilizarea celulelor registru
		4. Utilizarea multiplexoarelor
		5. Utilizarea memoriilor
		6. Utilizarea resurselor aritmetice
		7. Utilizarea resurselor DSP (Digital Signal Processing)
		8. Utilizarea pinilor (I/O)
		9. Utilizarea bufferelor asociate pinilor
	4. Tot aici se pot genera si rapoarte ale congestiilor, acestea arata zonele cu cea mai mare aglomerare de trasee si a modulelor ce sunt mapate in zona respectiva
4. **Estimarea consumului de putere**
	1. Puterea statica e data de curentii ce se scurg prin tranzistori si e dependenta de tehnologia de implementare, de tensiunea de alimentare si conditiile de temperatura exterioara
	2. Puterea dinamica e data de incarcarea/descarcarea capacitorilor capacitatilor la comutarea semnalelor 
	3. Dupa implementarea fizica a dispozitivelor FPGA, uneltele software dedicate pot estima consumul de putere al viitorului circuit
	4. Dupa implementarea fizica, rapoartele devin mai exacte, nu mai sunt niste simple estimari
	5. Uneltele software de implementare FPGA pun la dispozitia utilizatorului mecanisme de analiza a puterii
	6. Pentru calculul puterii consumate, analizatoarele utilizeaza si:
		1. Netlist-urile de implementare
		2. Informatii despre activitatea din circuit
		3. Valorile de tensiune utilizate
		4. Temperatura ambientala
	7. Pe baza acestor intrari se furnizeaza informatii despre curentul necesar functionarii si a temperaturii jonctiunilor interne
	8. Modalitati de reducere a consumului de putere:
		1. Selectarea cu atentie a tensiunii de operare
		2. Reducerea activitatii nedorite (reducerea/eliminarea glitch-urilor)
		3. Alegerea de dispozitive cu un consum mai redus de putere
		4. Alegerea unei frecvente de ceas minime ce asigura o functionalitate corecta
		5. Evitarea traseelor lungi de interconectare intre blocuri logice





## Bilete
### Bilet 1
1. Din sub-capitolul "Interconectarea circuitelor logice si parametri asociati", descrieti detaliat: Fan-In Fan-Out
2. Din sub-capitolul "Configurarea dispozitivelor programabile-FPGA", prezentati pe larg: a. Modelul de configurare Serial-Slave b. Modelul de configurare Serial-Master
3. Din sub-capitolul "Simularea si verificarea functionarii" prezentati pe larg: Mediul de verificare(Testbench-ul)
---

**Rezolvare:**

1. **Fan-In Fan-Out:**
	1. In terminologia ASIC (dar la fel sunt folosite si in cazul circuitelor FPGA) capacitatile porturilor de intrare si iesire sunt denumite fan-in si fan-out 
	2. Pentru o poarta logica, fan-in reprezinta capacitatea unui pin de intrare 
	3. Fan-out reprezinta capacitatea maxima pe care un pin de iesire o poate controla (daca bine-nteles poarta logica este alimentata la nivelul de tensiune corespunzator unuia din nivelulrile logice LOW si HIGH)
	4. ![[Pasted image 20240614135602.png]]
	5. Nota : intotdeauna fan-out este de mai multe ordine de marime mai mare decat fan-in (fan-out >> fan-in) 
	6. fan-out si fan-in masoara numarul de conexiuni ce pot fi realizate intre portile logice:
		1. fan-in caracterizeaza numarul de intrari
		2. fan-out caracterizeaza numarul maxim de porti logice ce pot fi conectate la o iesire
2. **Modelul de configurare Serial-Slave**
	1. In acest mod de configurare circuitul FPGA nu are controlul configurarii
	2. Datele de configurare sunt furnizate serial de catre un Master, care poate fi un procesor, un alt dispozitiv ce implementeaza logica de transfer a configurarii sau de alt circuit FPGA (cand sunt inlantuite in Daisy Chain)
	3. Circuitul Master este responsabil de controlul configurarii si furnizeaza ceasul si datele de configurare
	4. Circuitul Master va prelua datele de configurare de la memorie sau prin intermediul unui alt periferic si le va transmite catre circuitul FPGA
	5. ![[Pasted image 20240614135808.png]]
3. **Modelul de configurare Serial-Master**
	1. Circuitul FPGA dispune, pentru configurarea seriala de doi pini (doua porturi), unul de intrare si altul de iesire
	2. Pinul de intrare este folosit pentru receptionarea informatiei de configurare de la memoria externa
	3. ![[Pasted image 20240614135931.png]]
4. **Mediul de verificare(Testbench-ul)**
	1. Pentru verificarea functionalitatii folosind simularea, DUT (Device Under Test) este inconjurat de componente de verificare constituite intr-un mediu de verificare denumit testbench
	2. Testbench-urile sunt implementate cu ajutorul limbajelor de proiectare(Verilog/VHDL) sau a limbajelor de verificare (e, SystemVerilog)
	3. Structura unui testbench:
		1. elemente generatoare de trafic catre DUT
		2. elemente de interconectare cu DUT-ul (transformarea traficului in semnale de I/O pentru acesta)
		3. elemente de monitorizare (colectarea semnalelor de la porturile DUT sau din interiorul acestuia)
		4. elemente de analiza a raspunsurilor (verificarea corectitudinii)
		5. elemente de masurarea acoperirii functionale prin procesul de verificare
		6. elemente de raportare si notificare

### Bilet 2
1. Semnale de ceas si reset -> Domeniile de ceas
2. Analiza implementarii obtinute
	1. Tipuri de analiza al implementarii
	2. Analiza implementarii fizice
3. Fluxul de proiectare utilizand circuite FPGA -> Etapele principale in fluxul de proiectare FPGA
---

**Rezolvare:**

1. **Semnale de ceas si reset -> Domeniile de ceas**
	1. In circuitele digitale se folosesc adesea diferite domenii de ceas (zone din circuit in care elementele de logica secventiala functioneaza pe un anumit semnal de ceas, cu o anumita frecventa si o anumita faza)
	2. Multe semnalele de date tranziteaza domeniile de ceas (sunt calculate intr-un domeniu de ceas si apoi utilizate in alt domeniu de ceas)
	3. La tranzitatea din domeniul de ceas A in domeniul de ceas B se pot intalni urmatoarele situatii (raportat la frecventa ceasurilor):
	4. ![[Pasted image 20240614140318.png]]

2. **Analiza implementarii obtinute**
	1. **Tipuri de analiza al implementarii:**
		1. Dupa fiecare din etapele de Sinteza logica si Implementare Fizica, uneltele SW puse la dispozitie de producatorii de FPGA furnizeaza utilizatorilor diferite rapoarte cu informatii despre performantele de timp (timing) obtinute
		2. Tool-urile furnizeaza de asemenea informatii despre utilizarea resurselor dispozitivului FPGA de catre circuitul implementat
		3. Pentru a furniza rezultatele de timing obtinute, uneltele SW implementeaza algoritmi de Static Timing Analysis (STA)
		4. STA calculeaza timpii de propagare necesari semnalelor de date in raport cu semnalele de ceas definite de utilizator
	2. **Analiza implementarii fizice**
		1. Dupa implementarea fizica, se pot utiliza diverse metrici de analiza a implementarii (utilizarea resurselor, a ariei si a congestiilor) pentru a genera rapoarte
		2. Aceste metrici pot fi activate (prin intermediul formularelor din interfata grafica GUI a uneltelor SW de implementare FPGA) si pe baza lor se vor genera rapoarte de analiza a implementarii fizice
		3. Exemple de metrici de analiza a implementarii:
			1. utilizarea LUT-urilor (si a tipurilor acestora daca dispozitivul dispune de mai multe tipuri de LUT)
			2. utilizarea blocurilor logice (CLB, slice-uri)
			3. utilizarea celulelor registru (FF)
			4. utilizarea multiplexoarelor (MUX)
			5. utilizarea memoriilor (a blocurilor RAM) 
			6. utilizarea resurselor aritmetice
			7. utilizarea resurselor DSP 
			8. utilizarea pinilor (I/O) 
			9. utilizarea buffer-elorassociate pinilor 
			10. etc.
3. **Fluxul de proiectare utilizand circuite FPGA -> Etapele principale in fluxul de proiectare FPGA**
	1. In comparatie cu fluxul de proiectare ASIC, proiectarea circuitelor FPGA are mai putine etape (de exemplu etapele din proiectarea fizica sunt comasate in etapa de implementare fizica)
	2. De asemenea, rezultatul fluxului de proiectare FPGA este diferit deoarece rezultatul este sirul de biti (bitstream) necesar programarii circuitului si nu o reprezentare ce trebuie trimisa la turnatoriile de siliciu pentru producerea circuitelor digitale
	3. Principalele etape in fluxul de proiectare FPGA sunt:
		1. Design Entry 
		2. Sinteza logica
		3. Implementarea (Maparea, Plasarea, Rutarea)
		4. Generarea bitstream-ului

### Bilet 3
1. Rezistente de Pull Down si Pull Up
2. Metastabilitatea
3. Cum se proiecteaza FPGA

---

**Rezolvare**

1. **Rezistente de Pull Down si Pull Up**:
	1. Blocurile de I/O permit utilizarea de rezistente de Pull-up si Pull-down programabile
	2. Acestea sunt utile pentru a lega la sursa de tensiune (Vcc) sau la masa circuitului (Ground) pinii neutilizati (reducand astfel consumul de putere si sensibilitatea la zgomot)
	3. Aceste Pull-up and Pull-down implementeaza rezistivitati mari (50-100 kΩ)
	4. Implementarea rezistentelor programabile de Pull-up si Pull-down se realizeaza cu ajutorul unor tranzistori de tip p legati la Vcc (in cazul Pull-up) si de tip n legati la masa (in cazul Pull-down)
2. **Metastabilitatea**:
	1. Daca nu sunt respectati timpii de set-up si hold ($t_su$ si $t_{hold}$), adica data de intrare isi modifica valoarea logica in acest interval, bistabilul D poate intra in metastabilitate (iesirea bistabilului este nepredictibila)
	2. Metastabilitatea este o disfunctionalitate a circuitelor digitale 
	3. La finalul perioadei de instabilitate, iesirea bistabilului se va stabiliza la una din starile logice 0 sau 1 (dar nu se poate sti la care dintre cele doua valori se va stabiliza)
	4. Metastabilitatea apare atunci cand nu sunt respectate conditiile de set-up si hold (datele de la intrarea bistabilului isi schimba starea cand ar trebui sa fie stabile)
	5. Metastabilitatea poate aparea atunci cand semnalele de intrare sunt asincrone (vin din afara circuitului) sau cand datele de intrare sunt receptionate din alt domeniu de ceas (unde sunt folosite semnale de ceas cu alte frecvente sau cu faze diferite)
3. **Cum se proiecteaza FPGA**
	1. In comparatie cu fluxul de proiectare ASIC, proiectarea circuitelor FPGA are mai putine etape (de exemplu etapele din proiectarea fizica sunt comasate in etapa de implementare fizica)
	2. De asemenea, rezultatul fluxului de proiectare FPGA este diferit deoarece rezultatul este sirul de biti (bitstream) necesar programarii circuitului si nu o reprezentare ce trebuie trimisa la turnatoriile de siliciu pentru producerea circuitelor digitale
	3. Principalele etape in fluxul de proiectare FPGA sunt:
		1. Design Entry 
		2. Sinteza logica
		3. Implementarea (Maparea, Plasarea, Rutarea)
		4. Generarea bitstream-ului

### Bilet 4
1. Tehnologii de realizare a circuitelor FPGA 
	1. Circuitele FPGA bazate pe celule SRAM (avantaje dezavantaje)
	2. Circuitele FPGA bazate pe cellule SRAM: probleme de Securitate
2. Sincronicitatea in circuitele digitale: Parametrii temporali ai bistabilei D
3. Semnale de ceas si reset: Mascarea semnalelor de ceas
4. Porturile de intrare iesire: Transmisia diferentiala LVDS (principiu de functionare, avantaje)

---

**Rezolvare**
1. **Tehnologii de realizare a circuitelor FPGA** 
	1. **Circuitele FPGA bazate pe celule SRAM (avantaje dezavantaje)**
		1. Avantaje:
			1. se pot redefini (complet sau partial) functionalitatile implementate
			2. se pot adauga noi functionalitati (se pot extinde sau se pot imbunatati cele vechi)
			3. se pot alterna functionalitati (de ex. la punerea sub tensiune, circuitul realizeaza un ciclu de autotestare– self test– iar apoi poate continua, prin reprogramare automata, si executa functionalitatea de baza)
			4. producatorii de circuite FPGA pot utiliza cele mai noi tehnologii de memorii (cercetarea si dezvoltare in domeniul memoriilor este printre cele mai active in domeniul semiconductorilor)
			5. celulele SRAM utilizeaza aceeasi tehnologie CMOS ca si celelalte elemente al chip-ului, deci se pot folosi aceleasi procese de proiectare si aceleasi unelte software 
		2. Dezavantaje:
			1. trebuie reconfigurate la fiecare punere sub tensiune (continutul memoriei se pierde la oprirea alimentarii)
			2. deoarece informatia de programare trebuie reutilizata de fiecare data la punerea sub tensiune, necesita memorii auxiliare pentru stocarea acestei informatii
	2. **Circuitele FPGA bazate pe cellule SRAM: probleme de Securitate**
		1. Informatia de configurare este stocata in memorii auxiliare deci\ poate fi copiat
		2. Componentele de proprietate intelectuala (IP) sunt vulnerabile:
			1. desi nu exista unelte SW comerciale pentru reverse engineering (extragerea informatiei de configurare si recrearea schemei logice de functionare) si activitatea este una laborioasa, nu inseamna ca reverse engineering nu se poate face
			2. in anumite state se tolereaza activitatea de reverse engineering si extragerea informatiei de proiectare a blocurilor IPs
		3. Cea mai raspandita practica nu o constituie insa extragerea IP-urilor ci clonarea dispozitivelor (se creaza cablaje imprimate cu aceeasi structura, apoi se copiaza informatia de configurare a dispozitivului FPGA si se foloseste pe PCB ul nou creat)
2. **Sincronicitatea in circuitele digitale: Parametrii temporali ai bistabilei D**
	1. Exista trei parametri temporali asociati bistabilului de tip D: 
		1. timpul de set-up ($t_{su}$)
		2. timpul de hold ($t_{hold}$)
		3. timpul de propagare ($t_{prop}$) 
	2. Datele de intrare (prezente la intrarea D a bistabilului) trebuie sa fie stabile (sa nu mai schimbe starea logica) inainte ($t_{su}$) si dupa ($t_{hold}$) aparitia frontului de ceas
	3. Daca datele de intrare isi schimba valoarea logica in acest interval, in bistabil apare starea de metastabilitate
3. **Semnale de ceas si reset: Mascarea semnalelor de ceas**
	1. Arborii de ceas trebuie sa asigure distribuirea echilibrata si precisa a semnalului de ceas pe toata suprafata circuitului, deci mascarea ceasului trebuie sa se faca doar cu celule tehnologice specializate
	2. In circuitele FPGA arborii de ceas sunt predefiniti pe suprafata chipului si optimizati de producatori pentru a transmite semnalele de ceas cu intarzieri si decalaje minime
	3. Astfel, pentru implementarea mecanismelor de mascare a semnalelor de ceas, producatorii FPGA au implementate buffere specializate ce permit invalidarea ceasului fara a produce glitch-uri
4. **Porturile de intrare iesire: Transmisia diferentiala LVDS (principiu de functionare, avantaje)**
	1. Receptorul implementeaza la capatul liniei o rezistenta de cca 100 Ω (valoarea rezistentei este determinata si de impedanta liniei reprezentata de traseele celor doua linii de transmisie)
	2. La receptie se va sesiza o cadere de tensiune de +/- 350 mV (functie de sensul curentului) iar polaritatea tensiunii va fi utilizata pentru interpretarea nivelului logic transmis 
	3. Avantajele LVDS:
		1. Campul electromagnetic generat de trecerea curentului prin linii este mult redus (campurile electromagnetice generate de cele doua linii tind sa se anuleze reciproc deoarece au valoare egala si sens diferit), deci transmisia va crea mai putin zgomot
		2. Nu sunt afectate de zgomotul generat de alte linii de transmisie deoarece interferenta este identica pe ambii conductori ai liniei (ambele linii vor fi afectate de acelasi zgomot deci receptorul va vedea aceeasi diferenta intre linii)
### Bilet 5
1. **Circuite logice FPGA:**
	1. **Blocurile logice in circ. FPGA**
	2. **Programarea blocurilor logice**
2. **Sincronicitatea in circ. Digitale : Parametrii temporali ai bistabilei D**
3. **Simularea si verificarea functionala: Verificarea functionala**

---

**Rezolvare**
1. **Circuite logice FPGA:**
	1. **Blocurile logice in circ. FPGA
		1. Fata de primele versiuni, FPGA actuale au structura mult mai complexa
		2. Inca de la inceput, fiecare circuit FPGA era constituit dintr-o matrice de Blocuri Logice interconectate (cu interconectare programabila); tehnologia de implementare a LUT-urilor era cu celule SRAM
		3. Intr-un LUT cu 3 intrari (o memorie de 8 celule SRAM) se implementau functii de 3 variabile▪ In tehnologiile FPGA actuale, elementele registru pot fi preincarcate (cu valoarea logica 0 sau 1) si se potate configura functionalitatea ca bistabil de tip D (Dff) sau latch
	2. **Programarea blocurilor logice**
		1. De exemplu, pentrua implementa functia$(a ^ {!b}) \space |\space (b \& c)$ utilizand Lookup Tables (LUTs)
		2. Implementareafunctieipoatefi facuta prin incarcarea valorilor functiei din tabela de adevar(out1) in celulelede memorie SRAM ale LUT-ului 
		3. Adresa este data de tripleta {in1,in2,in3}
2. **Sincronicitatea in circ. Digitale : Parametrii temporali ai bistabilei D**
	1. Exista trei parametri temporali asociati bistabilului de tip D: 
		1. timpul de set-up ($t_{su}$)
		2. timpul de hold ($t_{hold}$)
		3. timpul de propagare ($t_{prop}$) 
	2. Datele de intrare (prezente la intrarea D a bistabilului) trebuie sa fie stabile (sa nu mai schimbe starea logica) inainte ($t_{su}$) si dupa ($t_{hold}$) aparitia frontului de ceas
	3. Daca datele de intrare isi schimba valoarea logica in acest interval, in bistabil apare starea de metastabilitate
3. **Simularea si verificarea functionala: Verificarea functionala**
	1. Procesul de verificare functionala (Functional Verification) stabileste corectitudinea functionarii unui circuit digital, in etapa de proiectare
	2. Se compara descrierea circuitului (in format HDL) cu o alta descriere, comportamentala, de nivel inalt
	3. Validarea comportamentului se face conform specificatiilor arhitecturale si functionale, urmand un plan de verificare prestabilit
	4. Se face abstractie de implementarea fizica a circuitului, verificandu-se doar implementarea logicii
	5. Circuitul ce trebuie verificat este denumit DUT (Device Under Test); Descrirea DUT-ului este de obicei la nivel RTL (Register Transfer Logic), reprezentat prin elemente simple (porti logice, bistabile)


## Rezolvari subiecte comune
### Parametrii temporali ai bistabilului d (3 bilete)
1. Exista trei parametri temporali asociati bistabilului de tip D: 
	1. timpul de set-up ($t_{su}$)
	2. timpul de hold ($t_{hold}$)
	3. timpul de propagare ($t_{prop}$) 
2. Datele de intrare (prezente la intrarea D a bistabilului) trebuie sa fie stabile (sa nu mai schimbe starea logica) inainte ($t_{su}$) si dupa ($t_{hold}$) aparitia frontului de ceas
3. Timpii de set-up si hold (la fel ca si timpul de propagare interna, $t_{prop}$) sunt caracteristici tehnologiei cu care sunt implementate bistabilele
4. Daca datele de intrare isi schimba valoarea logica in acest interval, in bistabil apare starea de metastabilitate
![[Pasted image 20240614142746.png|500]]
### Metastabilitatea (2 bilete)
1. Daca nu sunt respectati timpii de set-up si hold ($t_{su}$ si $t_{hold}$), adica data de intrare isi modifica valoarea logica in acest interval, bistabilul D poate intra in metastabilitate (iesirea bistabilului este nepredictibila)
2. Metastabilitatea este o disfunctionalitate a circuitelor digitale 
3. Cauze:
	1. Metastabilitatea poate aparea atunci cand semnalele de intrare sunt asincrone (vin din afara circuitului) sau cand datele de intrare sunt receptionate din alt domeniu de ceas (unde sunt folosite semnale de ceas cu alte frecvente sau cu faze diferite)
	2. Alte cauze ce pot crea metastabilitate sunt datorate semnalului de ceas utilizat, de exemplu cand apare defazajul semnalului de ceas (clock skew) sau cand panta de crestere/decrestere a ceasului (slew rate) este mare
	3. Nu in ultimul rand, metastabilitatea poate fi provocata de intarzierile prin logica combinationala (porti si interconexiuni)
4. Prevenire: 
	1. Din cauza multiplelor surse ce pot cauza metastabilitate, nu se poate elimina complet probabilitatea de aparitie a sa
5. Pentru reducerea probabilitatii de aparitie a metastabilitatii, in etapa de proiectare se introduce elemente de circuit denumite sincronizatoare pe trasele datelor ce vin din alte domenii de ceas sau vin complet asincron
![[Pasted image 20240614143033.png]]
### Etapele principale in fluxul de proiectare fpga (3 bilete)

1. Principalele etape in fluxul de proiectare FPGA sunt:
	1. Design Entry: Cea mai frecventa modalitate de design entry este prin utilizarea unei descrieri in limbaj HDL (Verilog sau VHDL)
	2. Sinteza logica: 
		1. In etapa de sinteza logica, la fel ca in cazul circuitelor ASIC, reprezentarea functionalitatii este translatata intr-o reprezentare cu porti logice si conexiuni intre acestea; in aceasta etapa exista numeroase optimizari (a logicii implementate, de crestere a vitezei, de scadere a puterii estimate, etc.)
		2. La finalul etapei de sinteza logica rezulta fisiere netlist si rapoarte de sinteza
	3. Implementarea (Maparea, Plasarea, Rutarea)
		1. Portile logice generate in etapa de sinteza sunt mapate pe blocurile circuitului FPGA (LUT, CLB, etc.) si sunt programate traseele de interconectare
	4. Generarea bitstream-ului
  

![[Pasted image 20240614143430.png|500]]

### Semnale de ceas si reset (2 bilete)
1. **Domeniile de ceas**
	1. In circuitele digitale se folosesc adesea diferite domenii de ceas (zone din circuit in care elementele de logica secventiala functioneaza pe un anumit semnal de ceas, cu o anumita frecventa si o anumita faza)
	2. Multe semnalele de date tranziteaza domeniile de ceas (sunt calculate intr-un domeniu deceas si apoi utilizate in alt domeniu de ceas)
	3. Acolo unde este posibil, cand se trece de la un ceas mai rapid la un ceas mai lent, pulsurile din domeniul de ceas rapid (semnalele cu durata de un ceas, sau mai multe dar totusi sub durata unei perioade de ceas lent) se latesc (se extinde durata pulsului la durata unei perioade de ceas din domeniul ceasului mai lent)
	4. Pentru prevenirea metastabilitatii se utilizeaza sincronizatoare (2 sau mai multe bistabile ce functioneaza pe ceasul de la receptie)
2. **Mascarea semnalelor de ceas**
	1. Tehnica mascarii ceasului (denumita clock gating in domeniul proiectarii circuitelor) se foloseste adesea in circuitele digitale pentru a reduce consumul inutil de putere 
	2. Aceasta tehnica foloseste un semnal de control (enable) pentru a valida (sau invalida) semnalul de ceas ce ajunge la componentele secventiale
	3. Principial se foloseste o poarta AND pentru a valida semnalul de ceas; in practica insa, utilizarea unei porti logice impreuna cu semnalul de ceas nu este recomandata deoarece aceasta poate produce glitch-uri pe semnalul de ceas; asa cum este reprezentat in figura, este recomandat sa se sincronizeze mai intai semnalul de validare
	4. Arborii de ceas trebuie sa asigure distribuirea echilibrata si precisa a semnalului de ceas pe toata suprafata circuitului, deci mascarea ceasului trebuie sa se faca doar cu celule tehnologice specializate
	5. In circuitele FPGA arborii de ceas sunt predefiniti pe suprafata chip-ului si optimizati de producatori pentru a transmite semnalele de ceas cu intarzieri si decalaje minime
	6. Astfel, pentru implementarea mecanismelor de mascare a semnalelor de ceas, producatorii FPGA au implementate buffere specializate ce permit invalidarea ceasului fara a produce glitch-uri

### Fan-in / fan-out
1. In terminologia ASIC (dar la fel sunt folosite si in cazul circuitelor FPGA) capacitatile porturilor de intrare si iesire sunt denumite fan-in si fan-out
2. Pentru o poarta logica, fan-in reprezinta capacitatea unui pin de intrare
3. Fan-out reprezinta capacitatea maxima pe care un pin de iesire o poate controla (daca bine-nteles poarta logica este alimentata la nivelul de tensiune corespunzator unuia din nivelulrile logice LOW si HIGH)
4. Nota : intotdeauna fan-out este de mai multe ordine de marime mai mare decat fan-in (fan-out >> fan-in)
5. Altfel spus, fan-out si fan-in masoara numarul de conexiuni ce pot fi realizate intre portile logice:
	1. fan-in caracterizeaza numarul de intrari
	2. fan-out caracterizeaza numarul maxim de porti logice ce pot fi conectate la o iesire
![[Pasted image 20240614143827.png]]
### Rezistentele de pull-up si pull-down

1. Rezistentele de Pull-up si Pull-down sunt utilizate pentru fortarea unui port de intrare/iesire la o anumita stare logica (HIGH=1 sau LOW=0)
2. Aceste rezistente sunt folosite pentru a preveni oscilatia unui port atunci cand acesta nu este conectat
	1. Pull-up "trage" valoarea interna la "weak High"
	2. Pull-down "trage" valoarea interna la "weak Low"
3. Rezistentele de Pull-up si Pull-down pot fi sub forma de componente discrete (plasate pe cablajul imprimat in imediata vecinatate a circuitului) sau pot fi realizate ca rezistente in interiorul circuitului integrat

![[Pasted image 20240614143954.png]]

### Circuite logice fpga

1. **Blocurile logice in circuitele FPGA**
	1. Inca de la inceput a fost folosit conceptul de Lookup Table (LUT)
	2. O structura simpla de Bloc Logic ce contine LUT cu 3 intrari, un registru si un MUX este prezentata in figura
	3. ![[Pasted image 20240614144144.png]]
	4. Fata de primele versiuni, FPGA actuale au structura mult mai complexa
	5. Inca de la inceput, fiecare circuit FPGA era constituit dintr-o matrice de Blocuri Logice interconectate (cu interconectare programabila); tehnologia de implementare a LUT-urilor era cu celule SRAM
	6. Intr-un LUT cu 3 intrari (o memorie de 8 celule SRAM) se implementau functii de 3 variabile
2. **Programarea blocurilor logice**
	1. De exemplu, pentrua implementafunctia(a ^ !b) | (b & c) utilizand Lookup Tables (LUTs)
	2. ![[Pasted image 20240614144324.png]]
	3. Implementarea functiei poatefi facuta prin incarcarea valorilor functiei din tabela de adevar(out1) in celulelede memorie SRAM ale LUT-ului

| int1 | int2 | int3 | out1 |
| ---- | ---- | ---- | ---- |
| 0    | 0    | 0    | 0    |
| 0    | 0    | 1    | 0    |
| 0    | 1    | 0    | 0    |
| 0    | 1    | 1    | 1    |
| 1    | 0    | 0    | 0    |
| 1    | 0    | 1    | 1    |
| 1    | 1    | 0    | 0    |
| 1    | 1    | 1    | 0    |

### Circuite fpga bazate pe celule sram
1. Majoritatea circuitelor FPGA sunt implementate utilizand celule SRAM (pot fi deci programate si reprogramate continuu)
2. **Avantaje:**
	1. se pot redefini (complet sau partial) functionalitatile implementate
	2. se pot adauga noi functionalitati (se pot extinde sau se pot imbunatati cele vechi)
	3. se pot alterna functionalitati (de ex. la punerea sub tensiune, circuitul realizeaza un ciclu de autotestare– self test– iar apoi poate continua, prin reprogramare automata, si executa functionalitatea de baza)
	4. producatorii de circuite FPGA pot utiliza cele mai noi tehnologii de memorii (cercetarea si dezvoltare in domeniul memoriilor este printre cele mai active in domeniul semiconductorilor)
	5. celulele SRAM utilizeaza aceeasi tehnologie CMOS ca si celelalte elemente al chip-ului, deci se pot folosi aceleasi procese de proiectare si aceleasi unelte software
3. **Dezavantaje:**
	1. trebuie reconfigurate la fiecare punere sub tensiune (continutul memoriei se pierde la oprirea alimentarii)
	2. deoarece informatia de programare trebuie reutilizata de fiecare data la punerea sub tensiune, necesita memorii auxiliare pentru stocarea acestei informati
4. **Probleme de Securitate:**
	1. Informatia de configurare este stocata in memorii auxiliare deci poate fi copiata
	2. Componentele de proprietate intelectuala (IP) sunt vulnerabile
	3. Cea mai raspandita practica nu o constituie insa extragerea IP-urilor ci clonarea dispozitivelor (se creaza cablaje imprimate cu aceeasi structura, apoi se copiaza informatia de configurare a dispozitivului FPGA si se foloseste pe PCB ul nou creat)

### Mediul de verificare(Testbench-ul)
1. Pentru verificarea functionalitatii folosind simularea, DUT (Device Under Test) este inconjurat de componente de verificare constituite intr-un mediu de verificare denumit testbench
2. Testbench-urile sunt implementate cu ajutorul limbajelor de proiectare(Verilog/VHDL) sau a limbajelor de verificare (e, SystemVerilog)
3. Structura unui testbench: 
	1. elemente generatoare de trafic catre DUT
	2. elemente de interconectare cu DUT-ul (transformarea traficului in semnale de I/O pentru acesta)
	3. elemente de monitorizare (colectarea semnalelor de la porturile DUT sau din interiorul acestuia)
	4. elemente de analiza a raspunsurilor (verificarea corectitudinii)
	5. elemente de masurarea acoperirii functionale prin procesul de verificare
	6. elemente de raportare si notificare

### Modelul de configurare serial-slave
1. In acest mod de configurare circuitul FPGA nu are controlul configurarii
2. Datele de configurare sunt furnizate serial de catre un Master, care poate fi un procesor, un alt dispozitiv ce implementeaza logica de transfer a configurarii sau de alt circuit FPGA (cand sunt inlantuite in Daisy Chain)
3. Circuitul Master este responsabil de controlul configurarii si furnizeaza ceasul si datele de configurare
4. Circuitul Master va prelua datele de configurare de la memorie sau prin intermediul unui alt periferic si le va transmite catre circuitul FPGA
5. ![[Pasted image 20240614135808.png]]
### Modelul de configurare serial-master
1. Circuitul FPGA dispune, pentru configurarea seriala de doi pini (doua porturi), unul de intrare si altul de iesire
2. Pinul de intrare este folosit pentru receptionarea informatiei de configurare de la memoria externa
3. ![[Pasted image 20240614135931.png]]


## Cursuri
### Curs 1

![[Fundamenele circuitelor logice programabile|Curs 1 CLP]]

### Curs 2

![[Evolutia circuitelor logice programabile|Curs 2 CLP]]