---
vytvořeno: 2023-05-17T11:38
oddíl: "Platební terminál"
zdroj: "OneNote / Návody/Pokladní zařízení SQL / Platební terminál"
tags:
  - onenote-import
  - k-revizi
---
![[Platební terminál - Nepojmenovaný obrázek.png]]

Tisk Konfigurace - na terminálu v nabídce :

- Admin
- Manager
- Config
- Cash Network

- Admin
- Technik\* ( heslo 9696 ) (4646 ) musí se sjednotit!
- Network

Potvrdit zeleným až do nabídky výběru nastavení a nastavit :

|   |   |
|---|---|
| Ter. | Gateway ( brána ) |
| Ter. | IP pokladny |
| Ter. |  |
| Manažer | IP terminálu |

Rozdíl m160ezi 192.168.**202**.153 a 192.168.**200**.153 je cílové nastavení pro externí a interní připojení do sítě. 202 externí a 200 interní.

Ověření nastavení :

Admin

Manager

Config

Tests

Ověření Gateway ( musí být 10/10 ) a term.diag pro kontrolu výtisku. Na konci musí být 2x OK

První kontrola IP adresy v Oktabu !!

**!!** **Při nefunkční odezvě terminálu směrem ven je potřeba zkontrolovat rozsah v routeru.**

**( Platí při externím připojení )**

**Např. IP adresa 192.168.202.224 a rozsah je 101-199 ( 224 mimo )**

**Jméno : brána ( např. 192.168.202.5 )**

**Heslo : \*\*\***
