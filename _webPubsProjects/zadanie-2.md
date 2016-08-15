---
title: "Zadanie 2: Transformácia vybraného dokumentu do formátu DocBook"
date: 2016-04-10
tags: DocBook, XML, XSLT
---
**Znenie zadania**<br>
Predmetom 2. zadania je spracovanie vybraného dokumentu (ideálne bakalárskeho projektu) z pôvodného ľubovoľného (Word, OpenOffice, LaTeX, …) formátu do formátu DocBook a vygenerovanie cieľového tvaru v PDF. Výsledný dokument bude mať rozsah minimálne 10 a maximálne 15 strán. Do rozsahu sa nezapočítavajú úvodné strany (obsah, zoznamy obrázkov a tabuliek), použitá literatúra a prílohy.
Požadované a kontrolné konštrukcie sú:

* štandardné členenie textu na kapitola, podkapitola, podpodkapitola, príloha, generovaný obsah,
* zvýraznenie slov, zvýraznenie členenia textu odrážkami alebo číslovaním,
* odkazy na iné časti vlastného dokumentu, prípadne odkazy na URL,
* poznámka pod čiarou,
* zoznam použitej literatúry a zdrojov vrátane ich citácie v texte,
* vloženie obrázku a tabuliek, odkazy na ne v texte; zoznam obrázkov a tabuliek v úvode alebo závere textu,
* vytvorenie registra pojmov (indexu) s pojmami hierarchicky usporiadanými do dvoch úrovni, napríklad „cykly, while“, „cykly, for“ (najmenej ako ukážku na 10-15 pojmoch na predvedenie práce s registrom).
* Súčasťou požiadaviek na zadanie je vytvorenie správy o zadaní 2, ktorá bude súčasťou vašej stránky o Webovom publikovaní na GitHube. Správa o rozsahu 150-250 slov bude obsahovať informácie o použitých elementoch a atribútoch, prípadne ukážky XML/XSLT demonštrujúce vykonané prispôsobenie DocBook šablon (nepovinné).

**Výsledok**<br>
Dokument na spracovanie som si vybral moju bakalársku prácu. Vo výstupe sa nachdádza iba jeho časť a je doplnená o tabuľku a index ktore v pôvodnej práci nie sú. V práci s DocBookom som použil následovné elementy:

* chapter, para, appendix, section, title, subtitle...
* simplelist - k nemu je spravená aj modifikácia v šablóne na zväčšenie rozostupu medzi jednotlivými prvkami listu
* itemsizedlist s atributom mark
* orderedlist s atributom numeration
* indexterm spolu s elementom index
* xref s atribútom linked ktorý obsahuje id na prvok z literatúry a teda odkazuje na literatúru
* link s atribútom linked ktorý obsahuje id na kapitoly a podkapitoly a teda odkazuje na časti práce
* figure na zobrazenie obrázkov
* unlink na poznámku pod čiarou
* table na zobrazenie tabulky

Okrem elementov bol upravené aj XSL, v ktorom som upravil formát vypisovania kapitol. Taktiež som nastavil aby pri nadpise v hĺbke viac ako 3 nevypisovalo číslo podkapitol (xsl:param name="section.autolabel.max.depth" select="2"). Do XSL som pridal kód pre manualne odriadkovanie textu v elemente "para". Aby bolo možné vypísať zoznam tabuliek a obrázkov, bolo nutné dopísať parametre "figure" a "table" generate.toc.dd