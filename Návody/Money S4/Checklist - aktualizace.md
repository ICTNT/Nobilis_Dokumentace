---
vytvořeno: 2023-08-28T11:16
oddíl: "Checklist - aktualizace"
zdroj: "OneNote / Návody/Money S4 / Checklist - aktualizace"
tags:
  - onenote-import
  - k-revizi
---
1.  Odstavíme externí komunikace (e-shopy) přes ==firewall==

2.  Vypneme automatiky na VM21

![[Checklist - aktualizace - Nepojmenovaný obrázek.png]]

- ⚠️ Nejprve dáme **"Pozastavit"** a potom **"Zastavit"**

![[Checklist - aktualizace - Nepojmenovaný obrázek-0.png]]

3.  V Money zakážeme externí aplikace

![[Checklist - aktualizace - Nepojmenovaný obrázek-1.png]]

![[Checklist - aktualizace - Nepojmenovaný obrázek-2.png]]

4.  V databázi spustíme zálohu a vypneme server agenta

Pravým tlačítkem na BackupS4 =\> Start Job at Step …

![[Checklist - aktualizace - Nepojmenovaný obrázek-3.png]]

Pravým tlačítkem na SQL Server Agent =\> Stop

![[Checklist - aktualizace - Nepojmenovaný obrázek-4.png]]

5.  Zablokujeme triggery WMS_Prevodka_TR a WMS_Reklamace_TR

![[Checklist - aktualizace - Nepojmenovaný obrázek-5.png]]

![[Checklist - aktualizace - Nepojmenovaný obrázek-6.png]]

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Po aktualizaci provedeme:

Shrink databáze

Spustíme Money

Aktivujeme triggery

Spustíme job manager

V Money zapneme externí aplikace

Spustíme automatiky - první spustíme Automat2, Automat1 a nakonec ten poslední

Spustíme firewall

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Skript pro kontrolu:

select name, is_disabled

from Sys.triggers

![[Checklist - aktualizace - image0.jpg]]

clothes

- ⚠️ Žádný nesmí být "disabled" ( = nikde nesmí být **1** )
