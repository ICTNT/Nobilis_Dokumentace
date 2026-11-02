---
vytvořeno: 2023-05-10T11:07
oddíl: "Katalog - KNV"
zdroj: "OneNote / Návody/Money S4 / Katalog - KNV"
tags:
  - onenote-import
  - k-revizi
---
**Dárkové poukázky Nobilis Tilia**

1.  V eshopu bude kategorie dárkové poukázky a v ní 3 dárkové poukazy v hodnotě 500 Kč, 1000 Kč, 2000 Kč
2.  Potřebujeme, aby zákazník tento poukaz koupil zcela samostatně, tj. nemohl si k němu přidat jakékoli jiné zboží z obchodu. Představa je taková, že u poukazu bude napsáno něco jako „Objednejte zde“ následně bude zobrazen formulář pro vyplnění povinných údajů (Jméno, Příjmení, adresa, email, telefon, stát /fixní výběr Slovensko, česká rep./), v dalším kroku bude nejspíš platba – zde potřebujeme, aby si zákazník mohl zvolit pouze dopravu Česká pošta a způsob platby předem. Pokud to bude zákazník ČR, bude mít poštovné 40 Kč, pokud Slovensko, tak jinou částku (upřesním), bude to tedy vázáno na výběr státu.
3.  Odeslání a potvrzení objednávky (zpracování nechám na vás)
4.  Emailové potvrzení objednávky by bylo stejné jako u jiných objednávek
5.  Struktura objednávky datově:

    ![[Katalog - KNV - clip_image002.jpg]]
6.  do tagu „KodDarkovyPoukaz_userdata“ potřebujeme zapsat kód poukázky z číselné řady viz. kapitola KODY
7.  Jako název nyní máme u standardních objednávek př. ESHOP 35641, my bychom u objednávky poukazu potřebovali př. ESHOP 35641 – dárkový poukaz

**KÓDY**

a\) budeme mít 3 číselné řady pro každou hodnotu zvlášť (DP500, DP1000, DP2000)

b\) kódy budou mít fixní roční platnost, potřebujeme je jednorázově získat třeba jako csv. To z důvodu tisku na poukázky, takže nějaký export.

c\) 3 měsíce před koncem platnosti (to si ohlídáme sami) bude potřeba překlopit na 3 nové řady na další rok a ty z minulého zavřít, by nešly již uplatnit, aby se zkrátka vybíraly poukázky nové na další rok, ty co se nevyčerpají z roku minulého, se deaktivují a papírové skartují.

d\) kód poukázky potřebujeme zapsat do tagu, viz obrázek, výběr jak jsme si řekli ne náhodně, ale postupně, je to z důvodu, že budeme mít stejně řazenou hromádku vytištěných poukázek, bude tak snazší jejich nalezení.

**Uplatnění dárkového poukazu**

1.  Stejný princip jako stávající poukázky pouze s jednou prosbou: Uplatnění poukazu se do objednávky přidává textem – bylo by možné zvolit si, co se tam napíše?

![[Katalog - KNV - clip_image004.jpg]]

Do pole katalog bychom potřebovali napsat UP1000 a do pole název Dárková poukázka v hodnotě 1000 Kč (kod poukázky)

**Kódové značení pro vysvětlení:**

**Tyto tři budou v money jako výrobek**

DP500 – dárková poukázka v eshopu v kategorii „dárkové poukázky“ hodnota 500 Kč

DP1000 - dárková poukázka v eshopu v kategorii „dárkové poukázky“ hodnota 1000 Kč

DP2000 - dárková poukázka v eshopu v kategorii „dárkové poukázky“ hodnota 2000 Kč

**Toto by se přidalo do objednávky textem po uplatnění kódu**

UP500 – Dárková poukázka v hodnotě 500 Kč (kod poukázky)

UP1000 – Dárková poukázka v hodnotě 1000 Kč (kod poukázky)

UP2000 – Dárková poukázka v hodnotě 2000 Kč (kod poukázky)

![](data:image/svg+xml;base64,PHN2ZyBzdHlsZT0iaGVpZ2h0OiAyNHB4OyBsZWZ0OiAxNDE3LjdweDsgcG9pbnRlci1ldmVudHM6IG5vbmU7IHBvc2l0aW9uOiBhYnNvbHV0ZTsgdG9wOiA0NjYuN3B4OyB3aWR0aDogMjRweDsiIHZpZXdib3g9IjE0MTcuNyA0NjYuNyAyNCAyNCI+PHBhdGggZD0iTSAxNDI5IDQ3OCBsIDAgMCIgZmlsbD0ibm9uZSIgb3BhY2l0eT0iMC41MCIgc3Ryb2tlPSJyZ2IoMCwgMjQ5LCAwKSIgc3Ryb2tlLWxpbmVjYXA9InNxdWFyZSIgc3Ryb2tlLWxpbmVqb2luPSJiZXZlbCIgc3Ryb2tlLXdpZHRoPSIyMyI+PC9wYXRoPjwvc3ZnPg==)
