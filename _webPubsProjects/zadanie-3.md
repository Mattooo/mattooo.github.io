---
title: "Zadanie 3: Transformácia vybraného dokumentu do formátu DocBook"
date: 2016-05-12
tags: xPath, XML, XSLT, CSS, HTML
---
**Znenie zadania**<br>
Analyzujte možnosti zápisu jednoduchej prezentácie v jazyku XML. Identifikujte základné súčasti prezentácie a navrhnite XML elementy pre ich označkovanie (metadátové, štrukturálne, inline). Dbajte na znovupoužiteľnosť a vyvarujte sa redundancií. Návrh elementov zrealizujte opísaním typu dokumentu pomocou vybraného jazyka (DTD, XSD, RELAX NG) spolu s vysvetlením účelu jednotlivých elementov. Vo vami navhrnutom jazyku vytvorte ukážkovú prezentáciu, ktorá bude demonštrovať možnosti tvorby prezentácií podľa definície typu dokumentu.

Navrhnite a vytvorte XSLT šablóny pre konverziu prezentácie z XML do XHTML+CSS a pre konverziu prezentácie z XML do PDF. Klaďte dôraz na znovupoužitie jednotlivých šablon pre viaceré výstupné formáty. Umožnite zadávanie parametrov transformácií.

Súčasťou požiadaviek na zadanie je vytvorenie správy o zadaní 3, ktorá bude súčasťou vašej stránky o Webovom publikovaní na GitHube.

**Výsledok**<br>
Vytvoril som zápis jednoduchej prezentácie v jazyku XML. Pomocou atribútov elementov je možné robiť jednoduché fomrátovanie slajdov prezentácie. Validita dokumentu zabezpečuje inline definícia typu dokumentu (DTD), ktorá je súčasťou XML prezentácie. Vytvorili sme XSLT šablónu, ktorá súbor XML prekonvertuje do výstupných HTML súborov. Tieto súbory už obsahuhú jednotlivé stránky prezentácie.

Základné elementy XML:

* slide - základný element przentácie, môže mať atribút type s hodnotou intro. Takýto slajd je vygenerovaná ako úvdný
* text - element slajdu obsahujúci odsek
* title - element slajdu obsahujúci nadpis
* li - element slajdu obsahujúci zoznam. Nutné zadať atribút atribút type=(ol alebo ul) kde ol je číslovaný zoznam ul odrážky
* img - možnosť vloženia obrázka do slajdu. Atribúty name ktorý označuje názov obrázku a size, ktorý označuje veľksoť obrázku

Všetky elementy elementu slide, je možne konfigurovať menením parametrov:

* color
* weight
* align
* size
