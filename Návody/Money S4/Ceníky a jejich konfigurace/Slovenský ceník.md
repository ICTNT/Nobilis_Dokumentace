---
vytvořeno: 2023-05-10T10:58
oddíl: "Ceníky a jejich konfigurace"
zdroj: "OneNote / Návody/Money S4 / Ceníky a jejich konfigurace"
tags:
  - onenote-import
  - k-revizi
---
Dokumentace ceníku SK v MS4

**Elektronický obchod – Nastavíme výchozí ceníky a sklady**

![[Ceníky a jejich konfigurace - clip_image002.jpg]]

**Ceník – konfigurace**

![[Ceníky a jejich konfigurace - clip_image004.jpg]]

Nastavíme platnost, ceník MUSÍ být aktivní, měna EUR – fixní kurz, Uživatelské proměnné – vložíme do pole **Stát ID – ID státu SK** – je to ceník pro Slovensko. U českého je to ID českého státu. Měna CZK.

![[Ceníky a jejich konfigurace - clip_image006.jpg]]

**Sazby DPH v katalogu**

![[Ceníky a jejich konfigurace - clip_image008.jpg]]

**Katalog / Obchodní podmínky**

\- nastavíme platné sazby pro daný stát. Každý produkt MUSÍ mít sazby pro oba státy CZ a SK. Je to z důvodu, že na základě CZ se pak spočítá správná cena s DPH pro výpočet ceny bez DPH pro SK ceník. Sazba musí mít datum Začátek intervalu vyplněn. Konec není povinný. Jedna sazba musí být vždy bez státu, takto to vyžaduje MS4.

**Výpočet SK s DPH je takto:**

Pokud je cena SK s daní tak s ní neděláme nic. Pokud je bez daně a zároveň je sazba DPH pro SK 20%, pak se podíváme na sazby v Čechách. Pak je vzorec: Cena bez DPH SK\* 1,21 (pokud je CZ 21%) nebo \* 1,15 (pokud je CZ 15%) – to celé pak děleno 1,20 a zaokrouhleno 0,01 matematicky. Pokud ani jedna z nich je možná pouze 10% a pak je vzorec (Cena bez DPH SK \*1,15)/1,10 a zaokrouhleno 0,01 matematicky. Hodnota 1,15 je tam schválně, protože Slováci nemají druhou sníženou, čili pro Česko je snížená 15% a druhá snížená 10%. Slováci mají snížená 10% ale ceník v MS4 počítá sníženou – 15% a proto musíme dopočítat cenu s DPH s 15% a pak spočítat správnou 10% DPH.

POZOR NA ZAČÁTEK INTERVALU – MUSÍ BÝT ZADÁN OD DOBY PLATNOSTI, PLATNÁ SAZBA SE VRACÍ Z DB PRO PŘESNÝ ČAS, NELZE TEDY NASTAVIT ZPĚTNĚ! Pokud je tedy 10.3. 2020 nemůžeme nastavit 9.3.2020 protože začátek intervalu musí být rovno nebo větší dnešnímu datumu a proto v tu chvíli neexistuje platná sazba a položka v ceníku SK nebude

![[Ceníky a jejich konfigurace - clip_image010.jpg]]

**Příklad chyby – pro datum 10.3. neexistuje platná sazba!!!**

**Příklady konfigurací sazeb DPH**

Zde je 21% sazba pro ČR

![[Ceníky a jejich konfigurace - clip_image011.png]]

Zde je 15% sazba pro ČR

![[Ceníky a jejich konfigurace - clip_image012.png]]

Zde je 20% sazba pro SK

![[Ceníky a jejich konfigurace - clip_image013.png]]

Zde je 10% sazba pro SK

![[Ceníky a jejich konfigurace - clip_image014.png]]

Zde je 10% sazba pro ČR – všimněte si povahy sazeb jsou vyplněny – to Slováci nemají

![[Ceníky a jejich konfigurace - clip_image015.png]]
