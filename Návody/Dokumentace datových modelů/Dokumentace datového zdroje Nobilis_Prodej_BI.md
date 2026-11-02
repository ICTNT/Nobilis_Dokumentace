---
vytvořeno: 2023-05-02T13:41
oddíl: "Prodej_BI"
zdroj: "OneNote / Návody/Dokumentace datových modelů / Prodej_BI"
tags:
  - onenote-import
  - k-revizi
---
Tento datový zdroj poskytuje obraz prodeje našich produktů. Komu, za kolik, jakými kanály, s jakou čistou marží,
do jakého regionu, přidělený obchodník daného prodeje apod.

- Model obsahuje data všech položek **faktury vydané** a **prodejky vydané**
- Data jsou od roku 2019
- Před aktualizací je potřeba požádat IT o prověření oprávnění načíst data do zdroje "Nobilis_Prodej_BI"
- Tento model je "mentální" přípravou na budoucí nasazení BI, cílem je doladit tento zdroj k dokonalosti, abychom
  z něj mohli vycházet. Budu rád za podněty k jeho vylepšení.

Popis jednotlivých polí:

|   |   |
|---|---|
| ID položky dokladu | Unikátní ID každé položky dokladu, využijeme například při počítání počtu položek dokladu |
| ID Dokladu | Unikátní ID dokladu, využijeme při počítání dokladů, kolik. **Je potřeba použít - jednoznačný počet v nastavení hodnot KTG tabulky** |
| ID produktu | Unikátní ID položky katalogu, najdeme v money v katalogu. Využijeme pro výpočet kolikrát se unikátně ukazuje v prodejních dokladech. Je potřeba použít - jednoznačný počet v nastavení hodnot KTG tabulky. Například kolikrát bez ohledu na množství si ho koupil zákazník XY |
| Jednotková cena s DPH | Jednotková cena s DPH (za 1 měrnou jednotku). U plátců DPH s 0% DPH je pak shodná s cenou bez DPH. |
| Množství položky | Celkové množství položky. **U dobropisů a vratek je mínusová hodnota.** |
| Obrat bez DPH | Obrat bez DPH za položku dokladu. U dobropisů a vratek je mínusová hodnota. |
| Obrat s DPH | Obrat s DPH za položku dokladu. U dobropisů a vratek je mínusová hodnota. |
| Skladová nebo neskladová položka | Hodnota 0 = neskladová, 1 = skladová. Můžeme se setkat také s názvem textová položka (0). S vazbou na skladovou zásobu (1). Většina slevových kupónů jsou neskladové, proto **pozor na filtrování.** |
| Prodejny nebo eshopy | Hodnoty: B2B e-shop, B2C e-shop, B2B prodejna, B2C prodejna.<br>Logika: pokud je to faktura bez přiděleného obchodníka, pak je to B2C e-shop<br>: pokud je to prodejka bez přiděleného obchodníka, pak je to B2C - prodejna<br>: s obchodníkem je to pouze opačně |
| Název výrobku | Název výrobku, pokud se jedná o skladovou položku, bereme aktuální název z katalogu, pokud ne, pak přímo z položky dokladu |
| Název master karty | Nadřazená karta produktu. Využijeme při sčítání za celý produkt bez ohledu na varianty. Jednoznačným počtem zjistíme počty produktů v jednotlivých produktových řadách apod. Pokud produkt nemá master kartu (difuzér) použijeme název z položky dokladu. |
| Katalogový kód produktu | Interní označení každého výrobku. Skladová položka - bereme aktuální z katalogu. Pokud je neskladová, pak z položky dokladu |
| Druh položky výrobku | Druh položky katalogu (vzorky v sáčku, obaly, vlastní výrobky, Anglie apod.) |
| Rok uvedení novinky | Hodnota z uživatelského sloupce v katalogu. (Jaro 2023, Podzim 2022…) |
| Objem produktu | Číselná hodnota (1,100,200,500,5000…) objem produktu bez jednotek. |
| Aktivní / Neaktivní | Využijeme pro oddělení vyřazených produktů nebo zjištění obratu vyřazených apod. Pokud má produkt stav "Vyřazen/prodej ukončen" pak je hodnota **"Prodej ukončen"** v opačném případě pak **"Prodává se".** |
| Manažerská pořizovací cena | **Od roku 2022 (včetně)** používáme nově manažerské pořizovací ceny. Zde není jednotková manažerská pořizovací cena, ale propočtená vč. zohlednění vratek apod. Dostanete tedy vždy násobek dle množství položky. Pokud produkt **nemá vyplněnou cenu pro každý rok** v katalogu produktu v uživatelských sloupcích, pak "Čistá marže" **bude 100%**, protože nemáme žádné náklady, stejně tak pozor na obaly, vzorky v sáčku a zboží. Potřeba důkladně udržovat aktuální údaje v katalogu. |
| Čistá marže | Jedná se o rozdíl mezi manažerskou pořizovací cenou a obratem bez DPH. Nezohledňuje slevy slevovým kódem. |
| Produktová řada | Název skupiny v katalogu, kam je výrobek zařazen. |
| Nadskupina produktové řady | Název nadřazené skupiny v katalogu, dle stromové struktury. (PLEŤ, TĚLO, PRO MUŽE…) |
| Typ položky | Pokud je jednotková cena **\<= 1.00** pak ji považujeme za **dárek**. Na eshopu se prodávají za 0.1, na prodejnách se prodávají za jinou cenu 1 Kč<br>Pokud se jedná o neskladovou položku a zároveň je mínusová cena bez DPH, pak se bude jednat o nějakou **slevu nebo dárkový poukaz**<br>Ve všech ostatních případech by to měla být **prodejní položka** **\* vyjímka je například brožura k EO, jelikož** **se nejedná o dárek, ale kupón na položku** |
| Kraj fakturace | Dle PSČ - fakturační adresy/obchodní adresy z dokladu najdeme Kraj, pokud nenajdeme shodu, pak je hodnota "prázdné". Bohužel jsou **chyby** někdy zbytečné - převážně na prodejnách (není zákazník na dokladu, není vyplněno u něj psč, zahraniční objednávky). **Je potřeba udržovat číselníky PSČ v Money.** Více info u IT.<br>Nedohledatelné - 0,10-0,25% z ročního obratu |
| Region fakturace | Viz Výše. |
| Stát fakturace | Fakturační stát z dokladu. **Vždy v vazbou na číselník! Také častá chyba.** |
| Rok (datum vystavení FV,PV) | V závorce je upřesněno z jakých dokladů a jaký datum to je. (Datum vystavení dokladu, FV - Faktura vydaná, PV - Prodejka vydaná). Formát: 2022,2023…<br>Datumové číselníky mají i další informace, více info u IT. |
| Měsíc rok (datum vystavení FV,PV) | 012021,022021… |
| Měsíc (datum vystavení FV,PV) | 01,02,03…12 |
| Číslo týdne (datum vystavení FV,PV) | 11,12,30,50…. |
| Název dne (datum vystavení FV,PV | Pondělí, Úterý…. |
| Kvartál (datum vystavení FV,PV) | První, druhý, třetí, čtvrtý |
| Pololetí (datum vystavení FV,PV) | 1, 2 |
| Název měsíce (datum vystavení FV,PV) | Leden, únor…prosinec |
| Víkend (datum vystavení FV,PV) | 1/Pravda = Je víkend<br>0/Nepravda = Pracovní den (nezohledňuje svátky) - ty by se musely doplnit do datumového číselníku, více info u IT |
| Den v měsíci (datum vystavení FV,PV) | 01,02,03…31 |
| Den v týdnu (datum vystavení FV,PV) | 1,2,3,4,5,6,7 |
| Celé datum<br>(celé datum vystavení FV, PV) | 12/03/2019 |
| Rok (datum<br>vystavení OP) | Viz informace výše. Datum vystavení dokladu, OP - objednávka přijatá), pokud doklad nemá objednávku, pak bereme datum z faktury nebo prodejky. **(Výjimka např. EDI, přebírá se datum z dodacího listu)**<br>(Měsíce, týdny atd analogicky jako výše) |
| Druh svátku<br>(datum vystavení OP) | K datumu vystavení objednávky zákazníkem zobrazíme druh svátku. Hodnoty mohou být:<br>oblíbené dny, ostatní svátky, státní svátek, významné dny |
| Název svátku (datum vystavení OP) | Název svátku |
| Pracovní den (datum vystavení OP) | Informace, zdali se jednalo o pracovní den, či den pracovního volna. |
| Rok (datum registrace zákazníka) | Viz informace výše. (Datum registrace zákazníka), pokud doklad má vazbu na zákazníka, pak z jeho vytvoření záznamu bereme informace o jeho registraci. (zápis do money) - **nemusí přesně odpovídat oproti eshopu.** Pokud by to mělo být přesné číslo, pak musí eshopy přenášet datum registrace. Kde doklad nemá vazbu je pak "prázdné"<br>(Měsíce, týdny atd analogicky jako výše) |
| Činnost obecně | V money je to pole poznámka v číselníku činností. U dokladů od roku 2019 jsou většinou shodné s polem Činnost název. U starších dokladů to tak nebude. Proto tato "spojka" |
| Činnost název | Název činnosti |
| Nadčinnost | Sdružení činností. Prodejci, profesionálové, spotřebitelé apod. |
| KZ a OP | Sdružení činností. Koncoví zákazníci, obchodní partneři, zahraničí |
| Faktura nebo prodejka | Členění dle typu dokladu - Faktury (e-shopy), Prodejky (prodejny) |
| Příznak dobropis/vratka | Pokud je doklad dobropisem nebo vratkou, pak je hodnota:<br>1/pravda = je dobropis nebo vratka<br>0/nepravda = není vratka nebo dobropis |
| Číslo dokladu | Číslo dokladu z money, prodejky vydané nebo faktury vydané. **Číslo dokladu na paragonu není shodné s číslem dokladu v money.** |
| Číslo objednávky (VS) | Variabilní symbol z dokladu prodejka nebo faktura. U nás shodné s číslem objednávky v eshopu a WMS. |
| Skupina dokladu | Název skupiny dokladu prodejky a faktury. Využijeme například pro členění prodejen. |
| IČ zákazníka | Aktuální IČO zákazníka z firem. Nepochází z dokladu, slouží spíš pro vyhledávání. |
| Zákazník - název firmy | Název firmy z firem. Pokud se jedná o koncového spotřebitele, je pole většinou prázdné. |
| Zákazník osoba | Jméno a příjmení hlavní osoby na kartě zákazníka. Je povinné pro eshopy. |
| Zákazník e-mail | Email z hlavní osoby na kartě zákazníka. Je povinné pro eshopy. |
| Zákazník telefon | Telefon z hlavní osoby na kartě zákazníka. Je povinné pro eshopy. |
| Přidělený obchodník | Jméno a příjmení přiděleného obchodníka, který je nastaven na dokladu prodejka nebo faktura. |
| Způsob platby | Způsob platby dokladu. U faktury je to jasné. U prodejek není platba. Kontrolujeme zdali je Hotově nebo Platba online (platba na terminálu kartou) anebo zákazník kombinoval úhrady Kombinace plateb |
| Způsob dopravy | Způsob dopravy na dokladu. Faktury jasné. U prodejek nahrazujeme za Osobní odběr |
