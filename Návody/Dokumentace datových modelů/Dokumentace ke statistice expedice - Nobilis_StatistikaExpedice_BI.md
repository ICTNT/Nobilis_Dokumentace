---
vytvořeno: 2023-08-07T10:54
oddíl: "StatistikaExpedice_BI"
zdroj: "OneNote / Návody/Dokumentace datových modelů / StatistikaExpedice_BI"
tags:
  - onenote-import
  - k-revizi
---
Tento datový zdroj poskytuje data o průběhu objednávky od času vytvoření objednávky až po její expedici. Zachycuje jednotlivé milníky, které umožňují vypočítat, zdali jsme objednávku vyřídili včas, pokud ne tak z jakého důvodu apod. Obsahuje pouze expedované zásilky, nikoli ty v procesu, smazané a stornované zde také nejsou. Pro výpočty byly vytvořeny zcela nové funkcionality a pole.

Obecné funkce:

- **Každých 15 minut - všechny dny je nastaven job v SQL, který prochází objednávky a doplňuje jednotlivé důvody zpoždění (pořadí dle číslování):**
  1.  **nestandardní objem** - pokud objednávka obsahuje položku s jinou dodací lhůtou \>3 pak je to nestandardní dodání, hodnotu čteme z katalogu z dodací lhůty
  2.  **na přání zákazníka** - pokud si zákazník vyplnil požadovaný datum expedice
  3.  **chybějící zboží** - pokud má objednávka stav "čeká na zboží" a obsahuje položku, která má dostupné množství menší než 0, pak se jedná o chybějící zboží
  4.  **obsahuje poznámku** - pokud je vyplněna poznámka u objednávky pak objednávku označíme

- **Každých 20 minut - všechny dny od 22.00-6.25:59 je nastaven job v SQL, který nastavuje následující pracovní den a čas expedice.**
  1.  Pokud začátek expedice respektive změna stavu objednávky na "k expedici" připadá na nepracovní den expedice (Nobilis_Dim_Date) nebo nepracovní čas expedice (Nobilis_Dim_Time), pak hledáme další možný pracovní den a čas a ukládáme ho do pole Expedice pracovní - jedná se o první možný čas, kdy můžeme na objednávce začít pracovat. Vyplňujeme jen pokud nebyl zahájen picking, protože expedice může pracovat i po pracovní době.
- **Doplnění triggeru WMS_Pickheader_TR zde jsou doplněny další stavy objednávek a pokud k nim dojde obtiskneme časové razítko do patřičných polí objednávky přijaté**
  1.  (přijato, k alokaci, k expedici, expedováno, probíhá vychystání, připraveno ke kontrole)
- **Vytvoření Scalar-valued funkcion pro výpočet pracovních dní mezi dvěma datumy, funkce vrátí počet pracovních dní, nikoli pracovních dní expedice. Dle Nobilis_Dim_Date.**
  1.  Vstupními parametry jsou DatumPrvni, DatumDruhe
- **Vytvoření Table-valued funkcion pro výpočet technických odstávek během procesu vyřízení objednávky, funkce vrací datum(y) a jméno(a) odstávek (max dva výpadky mezi procesem K expedici a Expedováno)**
  1.  Vstupními parametry jsou DatumPrvni, DatumDruh
- **Rozšíření konektorů eshopů**
  1.  Datum a čas vytvoření objednávky zákazníkem
  2.  Požadované datum expedice

Co je potřeba udržovat: (tabulka pro kontrolu Dim_Date_Dim_Time_PracovniDobyExpedice)

- **Tabulku Nobilis_Dim_Date** - zde nastavujeme pracovní dny expedice a vyplňujeme technické výpadky
- **Tabulku Nobilis_Dim_Time** - zde se nastavuje pracovní doba expedice, nyní 6.30-15.00 hod.

Popis jednotlivých polí - ==počítaná pole==

| Název pole | Krátký popis | Doplňující informace | Revize/Přidáno |
|---|---|---|---|
| Číslo objednávky/VS | Variabilní symbol, údaj pro dohledání objednávky ve všech systémech Netto, MS4, Eshopy |  |  |
| Popis objednávky | Textový popis objednávky z hlavičky "Eshop XXX" |  |  |
| Způsob platby | Způsob platby u objednávky |  |  |
| Stát koncového příjemce | Požadovaný stát doručení objednávky |  |  |
| Způsob dopravy | Způsob dopravy u objednávky |  |  |
| Služba dopravy | Podrobná informace o službě dopravy, upřesnění služby dle přepravce |  |  |
| Počet balíků | Nyní fixní hodnota, čekáme na data |  |  |
| Celková hmotnost objednávky | Součet hmotností položek dle Money S4 |  |  |
| Celkové množství položek objednávky | Součet počtu ks (pouze ty, co lze vychystat) ne doprava, ne kupony… |  |  |
| Počet položek v objednávce (druhů) | Počet druhů položek v objednávce (pouze ty, co lze vychystat) ne doprava, ne kupony… |  |  |
| Částka v Kč bez DPH | Částka bez DPH z faktury vydané | U interních objednávek faktury nejsou vystaveny. Data se načítají až po fakturaci ve večerních hodinách, den zpětně. |  |
| Město dodání | Město koncového příjemce, můžeme rozpadnout například osobní odběry na pobočky |  |  |
| Priorita objednávky | 1, 2, …9 |  |  |
| Typ objednávky | Upřesnění typu objednávky podle prodejního kanálu<br>hodnoty:<br>Objednávka B2B eshop CZ<br>Objednávka B2B eshop SK<br>Objednávka B2C eshop CZ<br>Objednávka B2C eshop SK<br>Objednávka EDI<br>Objednávka interní |  |  |
| Skupina objednávky | Skupina objednávky dle Money S4 |  |  |
| Činnost název | Název činnosti |  |  |
| Nadčinnost | Sdružení činností. Prodejci, profesionálové, spotřebitelé apod. |  |  |
| KZ a OP | Sdružení činností. Koncoví zákazníci, obchodní partneři, zahraničí |  |  |
| Důvod zpoždění objednávky | Popis důvodu zpoždění objednávek |  |  |
| Datum a čas vytvoření na eshopu | Přesný datum a čas vytvoření objednávky zákazníkem | • ⚠️ ~~Čas se nyní dodělává, den je ale správně~~  Již hotovo, časy jsou již podle e-shopů | 19.12.2023 |
| Požadovaný datum expedice zákazníkem | Požadovaný datum expedice zákazníkem<br>(ve vývoji) |  |  |
| Datum a čas zápisu do Money | Zápis do Money | Pokud je doba mezi *vytvořením zákazníkem* a *zápisem do money* neúměrně dlouhá, pak buďto objednávka obsahovala poznámku, anebo byly potíže s importem do money |  |
| Datum a čas vytvoření zálohové faktury | Datum a čas, kdy jsme vystavili zálohovou fakturu v money k objednávce s platbou předem či platbou online kartou |  |  |
| Datum zadání platby zákazníkem z BV | Den kdy zákazník zadal platbu v bance. Párujeme na variabilní symbol a hledáme pouze platby od 1.1.2023 a dále, v minulosti jsou duplicitní variabilní symboly. **Kontrolovat KTG v nástroji.** |  |  |
| ==Od objednávky k úhradě zákazníkem (pracovní dny)== | Hodnoty: 0 = ještě ten den, 1=první pracovní den … | *Datum vytvoření objednávky*; *Nejstarší přijatá platba* -1 den pokud nebyl 0, cílem je získat dny pro další výpočet celkové doby. Nechceme, aby se nám napočítávaly "půldny" |  |
| ==Od zadání platby po spárování u nás (pracovní dny)== | Hodnoty: 0 = ještě ten den, 1=první pracovní den … | *Nejstarší přijatá platba*; *Spárování úhrady v NT* -1 den, pokud nebyl 0, cílem je získat dny pro další výpočet celkové doby. Nechceme, aby se nám napočítávaly "půldny" |  |
| Datum a čas spárování/žádost o alokaci | Změna stavu objednávky na "K alokaci", u online plateb je to moment spárování úhrady a posun do WMS |  |  |
| Datum a čas povolení k expedici | Změna stavu na "k expedici" |  |  |
| ==Od alokace k povolení expedice (pracovní dny)== | Hodnoty: 0 = ještě ten den, 1=první pracovní den … | *Datum a čas spárování/žádost o alokaci; Datum a čas povolení k expedici.* Pokud je doba mezi *Datumem a časem spárování/žádosti o alokaci* a *Datumu a času povolení k expedici* dlouhá, pak zkoumáme pole poznámka, zdali nemáme nestandardní objem, chybějící zboží nebo nějakou jinou poznámku, případně požadované datum expedice zákazníkem. Pokud nic z toho, pak doba vznikla zpožděním doplňování pickovacích zón ze zásobního skladu. Objednávka dlouho čekala na zboží. |  |
| Reálný možný začátek expedice | • ⚠️ Generovaný datum - job v SQL, který nastavuje následující pracovní den a čas expedice. **Nefunguje u reklamací.** | Doplňujeme podle Nobilis_Dim_Date.PracovniDenExpedice, pokud nebyl ještě zahájen picking |  |
| ==Od možného začátku ke skutečnému pickingu (dny)== | Hodnoty: 0 = ještě ten den, 1=první pracovní den … | Pokud je vyplněn *Reálný možný začátek expedice*, bereme tento, pokud ne pak *Datum a čas povolení k expedici; Datum a čas začátku pickování.* Rozdíl dní (Datediff - obyčejný rozdíl mezi dny) mezi těmito dvěma datumy. Jak dlouho čekala objednávka na zahájení vychystání od povolení k expedici. |  |
| Kód pickera objednávky | Kódové označení pickera, který pickovat danou objednávku |  |  |
| Datum a čas začátku pickování | Změna stavu "probíhá vychystání" | Údaj z Netto control. |  |
| Datum a čas konce pickingu | Změna stavu "připraveno ke kontrole" | Údaj z Netto control. |  |
| ==Doba trvání pickingu (min)== | Délka pickování v minutách | *Datum a čas začátku pickování*; *Datum a čas konce pickingu* |  |
| ==Doba trvání pickingu (dny)== | Délka pickování ve dnech. 1 = ten den |  |  |
| Datum a čas začátku balení | Zde ještě nemáme hodnoty, potřebujeme je z WMS |  |  |
| Datum a čas konce balení | Změna stavu na "Expedováno", Potvrzení kontroly na balícím stanovišti | Údaj z Netto control. |  |
| Číslo balicího stanoviště | INSP1,2,3… čísla balících stolů |  |  |
| ==Od objednání k expedici (pracovní dny)== | Hodnoty: 0 = ještě ten den, 1=první pracovní den … | Zde jde o celkový počet pracovních dní z pohledu zákazníka, jak dlouho jsme pracovali na objednávce, doba než zákazník zaplatil je odečtena. Pokud nám trvalo dlouho spárovat úhradu, či jsme neměli zboží apod. Doba se započítává. |  |
| Datum a čas svozu | Datum a čas uzávěrky svozu |  |  |
| Datum a čas doručení | Zde ještě nemáme hodnoty, potřebujeme je z WMS |  |  |
| Chybová zpráva WMS | Různé chybové hlášky. | Ve vyhodnocení to bereme jako "Nelze vyhodnotit, chybná adresa" v celkovém vyhodnocení dáváme jako "V pořádku" |  |
| Picking časové údaje | Různé časové údaje vztažené k *Datumu a začátku pickování* | Podle časových údajů lze sestavovat KTG tabulky, pole můžeme doplnit o další ukazatele z tabulek Nobilis_Dim_Date, Nobilis_Dim_Time |  |
| Pracovní čas expedice | Hodnoty:<br>V pracovní době<br>Mimo pracovní dobu | Můžeme počítat kolik objednávek bylo pickováno mimo pracovní dobu expedice. |  |
| Datum a popis výpadku v NT | U všech objednávek v procesu od "Vytvoření objednávky" do "Datum svozu", tam byla technická odstávka. Ukazujeme datumy technické odstávky a její důvod. | • ⚠️ MAX 2 výpadky po sobě jdoucí mezi vytvořením objednávky a odesláním. |  |
| Výpadek příznak | Hodnoty:<br>Bez výpadku<br>Byl výpadek | Použijeme pro kontingenční tabulku, nepotřebujeme například přesný název výpadku apod. |  |
| Příznak odběrného místa dopravy | Hodnoty:<br>0 = není to doprava s odběrným místem<br>1 = jedná se o dopravu s doručením na odběrné místo |  | 19.12.2023 |
| První datum - připraveno k vyzvednutí | Datum, kdy dopravci poprvé poslali informaci, že je zásilka připravena k vyzvednutí |  | 19.12.2023 |
| Počet žádostí k vyzvednutí | Počet, kolikrát poslali upozornění, že zásilka je připravena k vyzvednutí |  | 19.12.2023 |
| Datum vyzvednutí zásilky/doručeno na adresu | Datum, kdy zákazník dostal zásilku do ruky. |  | 19.12.2023 |
| Vráceno odesílateli | Příznak, zdali byla zásilka vrácena zpět do Nobilis Tilia |  | 19.12.2023 |
| Datum odeslání zpět | Datum odeslání zásilky zpět do Nobilis Tilia |  | 19.12.2023 |
| ==Počet dní od odeslání k doručení/předání na odběrné místo (dny)== | Pokud se jedná o dopravu s odběrným místem, pak počítáme od odeslání od nás do doručení na odběrné místo. Pokud je to zásilka do ruky, pak počítáme od odeslání k doručení. Kalendářní dny. |  | 19.12.2023 |
| ==Počet dní čekání na vyzvednutí zásilky (dny)== | Počet dní od první informace o zásilce připravené k vyzvednutí a vyzvednutí příjemcem. Kalendářní dny. |  | 19.12.2023 |
| ==Vyhodnocení detail== | Do tří dnů<br>Chybělo zboží a je víc než tři dny<br>Chybělo zboží, ale je do tří dnů<br>Chybová zpráva WMS a je více než tři dny<br>Chybová zpráva WMS, ale je do tří dnů<br>Na přání zákazníka<br>Obsahuje poznámku a je více než tři dny<br>Obsahuje poznámku, ale je do tří dnů<br>Problém s párováním/Chyba importu a je více než tři dny<br>Problém s párováním/Chyba importu, ale je do tří dnů<br>Více než tři dny<br>Wellness balení a je víc než tři dny<br>Wellness balení, ale je to tří dnů |  |  |
| ==Vyhodnocení celkové== | V pořádku / Není v pořádku | Vyhodnocení detail prohlásíme v celkovém hodnocení jako v pořádku nebo není v pořádku podle potřeby |  |
