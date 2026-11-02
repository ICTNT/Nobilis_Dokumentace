---
vytvořeno: 2026-03-26T14:56
oddíl: "Nový android"
zdroj: "OneNote / Návody/WMS / Nový android"
tags:
  - onenote-import
  - k-revizi
---
1\. Instalovat Android USB Driver

2\. Někam, třeba do adresáře TEMP, rozbalit platform-tools-latest-windows.zip

3\. Na terminálu TC21 spustit recovery mód: Terminál vypnout/restartovat a držet pevně tlačítku PPT (PushToTalk). Levý bok, horní tlačítko.

Až terminál zavibruje a zobrazí se logo Zebry, tak tlačítko PPT pustit. Měl by naběhnout recovery mód, viz RecoveryMode.jpg

4\. Terminál připojte přes USB k PC (případně připijte dokovací stabici/cradle přes USB k PC a terminál vložtre do cradle)

5\. Na terminálu zvote v recovery modu nabídku "Apply upgrade from ADB"

6\. Na PC spustte

adb.exe sideload c:\\..\\

C:\Users\pavel.vana\>Y:\IT\instal\Nemazat\TC21Upgrade_A11_A13\ADB\platform-tools\adb.exe sideload Y:\IT\instal\Nemazat\TC21Upgrade_A11_A13\HE_FULL_UPDATE_11-64-10.00-RG-U00-STD-HEL-04.zip

![[Nový android - Nepojmenovaný obrázek.png]]
