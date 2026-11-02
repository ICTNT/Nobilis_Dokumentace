---
vytvořeno: 2023-03-02T14:33
oddíl: "Nastavení PC"
zdroj: "OneNote / Návody/Nastavení nového notebooku / Nastavení PC"
tags:
  - onenote-import
  - k-revizi
---
==P====říkazový řádek ( cmd ) :==

**ping** - odezva ip adresy

**ipconfi**g - výpis síťových připojení

**ipconfig al**l - výpis veškerých síťových připojení

**ipconfig/flushdns** - vyprázdnění mezi paměti ( při změně IP u zařízení )

**qwinsta** - na serveru VM2 pro zjištění aktivních uživatelů

**wmic bios get serialnumber** - zjištění sériového čísla

**dotnet** **--info** - kontrola verze

==Spustit :==

Control userpasswords2 - kontrola a nastavení práv uživatele

SystemPropertiesAdvanced - odebrání User

Disk pro software, drivers, \\nas3

![[Nastavení PC - Nepojmenovaný obrázek-1.png]]

![[Nastavení PC - Nepojmenovaný obrázek-2.png]]

[https://www.deviceinfo.me/](https://www.deviceinfo.me/)

Příkazový řádek, smazání zbytků složky v users

Krok 1.takeown /f C:\Users\suzana.hasaniova /r /d y

Krok 2. icacls C:\Users\suzana.hasaniova /grant Administrators:F /t

Krok 3. rmdir /s /q C:\Users\suzana.hasaniova
