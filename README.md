Da bismo sistematski testirali kalkulator koji obrađuje aritmetičke izraze i podržava prioritet računskih operacija, koristimo metod crne kutije (black box testing). Osim toga, napisaćemo i jedinicu test za metodu Calculate. Sledeći koraci će nam pomoći da identifikujemo potencijalne greške i nedostatke u programu.

Sistematsko testiranje (Black Box Testing)
Prvo, testiraćemo različite ulazne vrednosti kako bismo identifikovali eventualne greške:

Osnovne operacije:

2+3 očekivani rezultat: 5
5-2 očekivani rezultat: 3
3*4 očekivani rezultat: 12
8/2 očekivani rezultat: 4
Prioritet operacija:

2+3*4 očekivani rezultat: 14 (množenje ima prioritet nad sabiranjem)
10-2/2 očekivani rezultat: 9 (deljenje ima prioritet nad oduzimanjem)
(2+3)*4 očekivani rezultat: 20 (zagrade imaju najviši prioritet)
Složeniji izrazi:

10+5*4-3/3 očekivani rezultat: 27 (redosled: 5*4=20, 3/3=1, 10+20-1=29)
100/2+5*3-7 očekivani rezultat: 57.5 (redosled: 100/2=50, 5*3=15, 50+15-7=57.5)
(10+5)*(4-3) očekivani rezultat: 15
Nevalidni izrazi:

10/0 očekivani rezultat: greška (deljenje nulom)
5++3 očekivani rezultat: greška (neispravan operator)
7* očekivani rezultat: greška (nepotpun izraz)
abcd očekivani rezultat: greška (neispravan unos)
Pisanje jedinice testa za metodu Calculate
Pretpostavićemo da metoda Calculate prima string aritmetičkog izraza i vraća rezultat kao double. Koristićemo JUnit za pisanje testa.
