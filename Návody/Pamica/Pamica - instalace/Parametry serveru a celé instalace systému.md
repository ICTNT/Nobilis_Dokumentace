---
vytvořeno: 2023-11-07T15:04
oddíl: "Pamica - instalace"
zdroj: "OneNote / Návody/Pamica / Pamica - instalace"
tags:
  - onenote-import
  - k-revizi
---
INFO

- server by měl splňovat tyto požadavky:  [http://www.stormware.cz/systemove-pozadavky/#uroven_3](http://www.stormware.cz/systemove-pozadavky/#uroven_3)

CPU

- Intel Xeon Gold 6126 2.60 GHz

RAM

- 16 GB

- v             13:00 aktuálně využito      3,8  GB

- v             14:00 aktuálně využito      4,7  GB

HDD

- C             159  GB         -         133 GB FREE

OS

- Microsoft Windows Server 2022 Standard (x64) Build 20348.2031

NÁZEV SERVERU

- VM30

DOMÉNA

- ANO (nobilis.local)

SQL SERVER

- Microsoft SQL Server 2022 Express

INSTALACE SQL SERVER - již instalován správcem

- instance pamica

- nastavení SharedMemory, NamedPipes, TCP/IP - OK

INSTALACE PAMICA SQL

- konfigurace složek:

![[Pamica - instalace - Nepojmenovaný obrázek.png]]

- nastavení připojení k SQL:

![[Pamica - instalace - Nepojmenovaný obrázek-0.png]]

- automatická údržba    - každý den v 1:00 (údržbu spouští soubor C:\STORMWARE\UlohySQLServeru\Udrzba.cmd; při údržbě nesmí být POHODA nikde spuštěna)

- záloha databází       - každý den ve 2:00  + automatické odmazávání po 30 dnech (zálohu spouští soubor C:\STORMWARE\UlohySQLServeru\Zaloha.cmd)

Pozn:

Naplánované úlohy se spouští pod uživatelem "herak".

Pokud budete tohoto uživatele rušit (měnit heslo), tak nezapomeňte přenastavit uživatele u naplánovaných úloh pro údržbu a zálohu.
