---
vytvořeno: 2023-03-02T13:37
oddíl: "Nastavení PC"
zdroj: "OneNote / Návody/Nastavení nového notebooku / Nastavení PC"
tags:
  - onenote-import
  - k-revizi
---
**MyQ -** **pro kontrolu stavu tonerů a připojení tiskáren**

Přihlášení : [https://vm27:8090/cs/](https://vm27:8090/cs/)

Jméno: \*admin

Heslo: \*\*\*\*

Při založení nového uživatele se musí synchronizovat databáze s domény : ( MyQ - nastavení - synchronizace uživatelů )

![[Nastavení PC - MyQ.PNG]]

- ⚠️ Windows 10 / správa tisku

Přidat port - Standart TPC / IP port - Nový port

Název či IP adresa tiskárny : napsat název tiskárny

Název portu : název tiskárny

Pravým na vytvořený port a konfigurovat

![[Nastavení PC - Port.PNG]]

Přidat tiskárnu pomocí portu ( př. PRN005 ) a nainstalovat nový ovladač z disku ( ovladače \\nas2\install\Drivers \\Printer ) a vybrat tisk zkušební stránky.

- ⚠️ **Kontrola v MyQ v záložce tiskové fronty musí být vidět vytištěná zkušební stránka**

**Web : PRN005/ -** Kontrola tiskárny ve webovém rozhraní ( tiskový toner )

Přihlášení : itsprava / \*\*\*\*

Přihlášení Ricoh : admin

Tiskárny RICOH - objednává si sama tiskárna

Ostatní tiskárny Cesar Trade - info@cesertrade.cz tel: 774819472 , Jan Urban

![[Nastavení PC - Nepojmenovaný obrázek.png]]

- ⚠️ Windows 11 / Přidat tiskárnu nebo skener

Přidat zařízení =\> Přidat ručně

Přidat tiskárnu pomocí IP adresy nebo názvu hostitele

Typ zařízení =\> Zařízení TCP/IP

Hostitelský název čí IP adresa =\> vm27.nobilis.local

Název portu =\> název tiskárny

"Jsou vyžadovány dodatečné informace o portu." =\> Typ zařízení =\> Vlastní =\> Nastavení…

![[Nastavení PC - Port-0.PNG]]

Instalovat ovladač tiskárny =\> Z disku… =\> Použít aktuálně nainstalovaný ovladač

Sdílení tiskárny =\> Nesdílet tuto tiskárnu

- ⚠️ **Kontrola v MyQ v záložce tiskové fronty musí být vidět vytištěná zkušební stránka**

![[Nastavení PC - Nepojmenovaný obrázek-0.png]]

**Nastavení skenování u tiskáren :**

Tiskárna OSTRAVA - IP : 192.168.9.6

Heslo: naše QWE...

Tiskárna BRNO - IP : 192.168.10.8

Heslo: naše QWE…
