---
vytvořeno: 2025-02-27T13:59
oddíl: "Školení zákaznická"
zdroj: "OneNote / Návody/E-Shopy / Školení zákaznická"
tags:
  - onenote-import
  - k-revizi
---
\- nový zákazník na B2B bude procházet novým modulem na e-shopu - na e-shopu nahlásí, jestli je plátcem, zákaznická dostane info a předá na účtárnu ke kontrole, jestli zákazník skutečně je plátcem DPH. Pokud ano, schválí ho a zákaznická může poslat objednávku dál procesem. Případně pokud není plátcem, tak objednávku stornovat

\- nový stav *30 minut na úpravy* (pokud je potřeba delší čas na úpravy, přepnu do stavu *Editace objednávky*), do Money se propíše až po uplynutí této doby (ve stavu *Přijatá*), do té doby je jakkoliv editovatelná - pokud není platba on-line!

\- ve stavu *Nová* lze s objednávkou dělat cokoliv i v případě platby on-line

\- *Čeká na platbu převodem* - objednávka je v Money, vytvořená zálohovka, ale čeká na platbu

\- *Přijatá -* objednávka s osobním odběrem nebo objednávka, která už je v Money a pracuje se s ní

\- nově jsou dva stavy *Storno -* odlišuje se storno z Money a z e-shopu

\- stav *Problém s objednávkou* = nenaimportovala se do Money, hned předávat na IT

\- nový stav *Objednávka k přepracování* = stav z expedice *Chyba balení, Chyba kontroly*, pokud je u objednávky platba předem (Gopay …) je potřeba se nejprve dohodnout s účtárnou. U *Chyby vychystání, Chyba kontroly* se přepracuje celá objednávka včetně zálohovky - nutná součinnost účtárny.

\- pokud není zboží, a ví se to dopředu, vleze se do NETTO a dá se *Dealokovat* a *Smazat,* zákaznický servis opraví e-shop i Money (pokud není platba předem nebo on-line !) a po úpravách se dá objednávka do stavu *K alokaci*

\- u změny dopravy naklikám změnu dopravy a úplně dole do okénka opravím cenu dopravy

\- *Chyba vychystání, Chyba kontroly -* interní stav pro tyto chyby bude *Storno netto*, aby se v Netto vystornovala, ale v e-shopu bude dál k editování ve stavu *Objednávka k přepracování -* dá se pouze znovu stav *Přijato* a objednávka se pošlu znovu s přepsanými položkami novou exspirací

\- nové elektronické dárkové poukazy na B2C - nový modul na e-shopu, poukazy se dají nakupovat se zbožím, v systému se to samo rozdělí - zákazníkovi se pošle pdf s poukazem mailem a zboží jde do expedice k vychystání

\- v B2C nově v *Cenotvorbě* v *Dárkových poukazech* výpis všech poukazů, jestli byli utraceny, na jakou objednávku byly použity a dá se i znovu stáhnout PDF - pokud není zatím uplatněn

\- v administraci v *Objednávkách* v *Historii komunikace* se dá dohledat jaké všechny maily byly zákazníkovi odeslány a případně znovu odeslat např. QR kód

\- nově modul *Kontrola zaměstnaneckých* sešítků - i bez poznámky "na sešítek", přidal by se do adminu stav *Chybný* sešítek a zákaznická/fakturantky by denně vyfiltrovali objednávky s tímto stavem, opraví se a objednávka znovu proběhne kontrolou

- ⚠️ ⚠️ - zjistit zda se dá odpárovat dárkový poukaz po uplatnění u stornované objednávky - ve skutečnosti neuplatněn

- ⚠️ ⚠️ - napsat na E-Morfiq kvůli výběru poboček - vyhledavač "nenašeptává" + při opravě to nepřepisuje ID pobočky - musí se opravovat natvrdo v Money
