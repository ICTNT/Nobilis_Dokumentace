---
vytvořeno: 2023-05-10T11:15
oddíl: "Ceníky a jejich konfigurace"
zdroj: "OneNote / Návody/Money S4 / Ceníky a jejich konfigurace"
tags:
  - onenote-import
  - k-revizi
---
Mezinárodní DPH na e-shopu, cenotvorba českého a slovenského

e-shopu, dokumentace napojení

**Cíl:**

Cílem je splnění legislativy ČR a SK v rámci DPH a cen pro zákazníky na dvou eshopech. Maximálně zautomatizovat proces objednávek, eliminovat chyby zákazníků, které by mohly mít dopad na zpracování navazujících dokladů v MS4. Jasně definovat podmínky nákupu na obou eshopech.

**Definice eshopů:**

Český eshop – jedná se o prodejní kanál pro zákazníka, který má fakturační stát Českou republiku, koncovou zemi doručení své zásilky má do ČR. Nakupuje v sazbách DPH 21, 15, 10 %. Plátci i neplátci daně nakupují vždy vč. DPH. Registrovat se na tomto e-shopu bude pouze zákazník z ČR. Přihlášení zákazníka SR je zakázáno. Produkty mají kod eshopu \* „WebTown“ a jsou vždy v Kč. EUR je zakázáno. Dopravy a platby pro SK jsou zakázány.

Slovenský eshop – jedná se o prodejní kanál pro zákazníka, který má fakturační stát Slovensko, koncovou zemi doručení své zásilky na Slovensko, Nakupuje v sazbách 10%, 20%, 0%. Registrace na tomto e-shopu možná pouze pro SK. Přihlášení a registrace ČR zakázána. Produkty k tomuto eshopu mají kod eshopu \* „WebTownS“. Dopravy a platby ČR jsou zakázány. Měna EUR, Kč – zakázáno.

Technické informace napojení MS4.

1\. Formuláře

a\) Formulář pro eshop ČR – registrace apod. – odebrat výběr státu SK, košík odebrat zemi doručení SK. Košík odebrat SK.

b\) Formulář pro eshop SK – registrace apod. – odebrat výběr státu CZ, košík odebrat zemi doručení CZ. Přidat pole IČDPH. Bude tak IČ, DIČ a IČDPH. Pokud zákazník vyplní IČDPH má vždy přednost a určuje, zdali je zákazník plátce. Proto v xml se zákazníkem odchází příznak plátce DPH „true“. ICDHP plníme do elementu DIC. Pokud zákazník vyplní obojí (DIC A ICDPH), DIC nepřenášíme. Pokud nevyplní ICDPH je pro nás neplátce, a proto bude mít ceny v průběhu nákupu a košíku vždy s DPH. A v xml je element platce DPH „false“. V opačném případě (plátce – má IČDPH) ukazujeme ceny bez DPH na produktech i v košíku a i platba bude bez dph. Objednávka – položky do MS4 přichází jako typ ceny „0“ – bez DPH a element „DruhSazbyDPH“ má hodnotu 2. ICDPH – prosím validované pole.

2\. Produkty aktivní pro eshopy: View - EObchod_Obchod – seznam eshopů založených v MS4. Doplníme o nový záznam WebTownS. Jejich ID je pak důležitou vazbou do view EObchod_ObchodArtikl, kde hledáme stejné root_ID a následně bereme artikl_ID, které říká, který produkt má být aktivní pro zákazníka. Déle view \_EObchod_ObchodCenik kde root_ID =ID (eshopu) najdeme platný ceník (cenik_ID) pro eshop, který existuje v MS4. Totožná logika je v případě druhé konfigurace a to skladů EObchod_ObchodSklad.

3\. Ceny: Každý z eshopu má vlastní ceník.

Český v Kč s hladinami beze změny. Všechny ceny s DPH i bez DPH si eshop bere hotové. Sazby DPH vždy z položky ceníku (EObchod_PolozkaCeniku). Cenik_ID z konfigurace viz výše.

Slovenský v EUR s hladinami beze změny. Všechny ceny s DPH i bez DPH si eshop bere hotové. Sazby DPH vždy z položky ceníku (EObchod_PolozkaCeniku_SK). Cenik_ID z konfigurace viz výše.

Oba ceníky fungují na stejném principu vč. modify_date. Obsahují stejné sloupce.

4\. objednávky XML

a\) CZ eshop – Položky objednávek vždy typ ceny „1“. Měna Kč. Posíláme cenu vč. DPH pro MO i VO, Group_ID = CBC2E787-6849-41D7-A282-CEB137814BD9 (ID skupiny objednávek v MS4)

b\) SK eshop – neplátce, tedy ten, co nakupuje s daní. Položky objednávek typ ceny „1“. Měna EUR. Posíláme cenu vč. DPH. Group_ID = 55E8D885-AACE-463D-850E-B102A13B721D (ID skupiny objednávek v MS4)

c\) SK eshop – plátce, tedy ten, co nakupuje bez DPH. Položky objednávek typ ceny „0“ a element „DruhSazbyDPH“ má hodnotu 2. Posíláme cenu bez DPH do elementu „cena“. Měna EUR. Group_ID = 1635BE4C-7230-4F9D-96AC-5FB58234F1C2 (ID skupiny objednávek v MS4)

Cena dopravy a sazby na dopravách musí odpovídat nastavením jako položky v jednotlivých případech. a, b, c.

5\. Přehled datových zdrojů

CZ eshop

\_EObchod_Cenik -platný ceník pro CZ

\_EObchod_PolozkaCeniku – položky ceníku CZ – zde sazba DPH

\_EObchod_PolozkaCenikuCenovaHladina – cenové hladiny CZ – zde jsou také sazby pro jistotu

SK eshop

\_EObchod_Cenik_SK – platný ceník pro SK

\_EObchod_PolozkaCeniku_SK položky ceníku SK – zde sazba DPH

\_EObchod_PolozkaCenikuCenovaHladina_SK – cenové hladiny SK – zde jsou také sazby pro jistotu

6\. Uživatelé eshopu

a\) CZ eshop pouze pro české zákazníky. SK zakázat přihlášení, respektive přesměrovat na slovenský.

b\) SK eshop pouze pro slovenské zákazníky. CZ zakázat přihlášení, respektive přesměrovat na český.

\*Kod není finální
