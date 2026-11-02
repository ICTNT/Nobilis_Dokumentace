---
vytvořeno: 2023-07-12T10:44
oddíl: "Veletrh"
zdroj: "OneNote / Návody/Pokladní zařízení SQL / Veletrh"
tags:
  - onenote-import
  - k-revizi
---
**Ve firemni siti:**

**ProdejnaSQL**

**Přihlášení do zařízení**:

Prodejna

Popcorn489

Pokladna ma DHCP rezervaci 192.168.200.150

Terminal ma pevnou IP 192.168.200.xxx

GateWay a DNS urcuje DHCP (nemusi se nastavovat) 192.168.200.5

**ProdejnaSQL1**

**Přihlášení do zařízení**:

Prodejna

Popcorn489

Pokladna ma DHCP rezervaci 192.168.200.151

Terminal ma DHCP rezervaci 192.168.200.167

GateWay a DNS urcuje DHCP (nemusi se nastavovat) 192.168.200.5

**OKTAB**

**Přihlášení do zařízení**:

Prodejna

Popcorn489

Oktab ma automatickou IP dle DHCP

**Je nutne v ProdejneSQL nebo Oktabu (dle toho kde je terminal)**

spustit ProdejnaSQL – Manažer

komponenty

rozkliknout "terminál"

nastavit IP terminalu (192.168.200.167)

**v terminalu VX520:**

ADM - M+ manazer - technik - heslo "9696" - Cash register - Network - TCP klient - IP adress (zadat IP ProdejnySQL1 - 192.168.200.151)

** **

**V externí síti:**

**ProdejnaSQL**

neumisťuje se mimo síť

**ProdejnaSQL1(pripojeni přes router/modem TP-link MR200 – detaily na straně 3)**

**Přihlášení do zařízení**:

Prodejna

Popcorn489

**Přihlášení do VPN !!!**:

ProdejnaSQL1

Popcorn489

musí byt pod timto uctem kvůli rezervaci IP VPN!

Pokladna ma DHCP rezervaci od routeru TPlink 192.168.202.151

Terminal ma DHCP r rezervaci od routeru TPlink 192.168.202.167

GateWay a DNS urcuje DHCP (nemusi se nastavovat) 192.168.202.5

VPN adresa na FW rezervovano 172.26.75.201

**OKTAB**

**Přihlášení do zařízení**:

Prodejna

Popcorn489

**Přihlášení do VPN !!!**:

Prodejnaoktab

Popcorn489

musí byt pod timto uctem kvůli rezervaci IP VPN!

Pokladna ma DHCP rezervaci od routeru TPlink 192.168.202.153

Terminal ma DHCP r rezervaci od routeru TPlink 192.168.202.167

GateWay a DNS urcuje DHCP (nemusi se nastavovat) 192.168.202.5

VPN adresa na FW rezervovano 172.26.75.202

**Je nutne v ProdejneSQL nebo Oktabu (dle toho kde je terminal)**

spustit ProdejnaSQL – Manažer

komponenty

rozkliknout "terminál"

nastavit IP terminalu (192.168.202.167)

**v terminalu VX520:**

ADM - M+ manazer - technik - heslo "9696" - Cash register - Network - TCP klient - IP adress (zadat IP pokladny - 192.168.202.151) original heslo je 4646

**Router/modem TP Link MR200**

**Varianta data (SIM)**

do LAN1 a do LAN2 připojit Prodejnu SQL a terminál

Zapnout Router/modem

Spustit Prodejnu a terminál

**Varianta pevný internet (veletrhy)**

do LAN1 a do LAN2 připojit Prodejnu SQL a terminál

do LAN4/WAN pripojit kabel od poskytovatele

Zapnout Router/modem

Spustit Prodejnu a terminál

Na WAN je nastaveno DynamicIP – vezme si tedy IP adresu zarizeni, brany a DNS automaticky z DHCP poskytovatele.

**Pokud by byl problém:**

V prohlížeči spustit administraci routeru (192.168.202.5) – heslo (jako ITsprava na stanicich QWE……….)

Advanced – network – internet

nastavit pevnou IP na stejny subnet jako je IP brany poskytovatele

nastavit GW a DNS dle poskytovatele

priklad GW poskytovatele je 192.168.150.10:

IP Adress se zada 192.168.150.20

GW 192.168.150.10

DNS 192.168.150.10

Z \<[https://nobilistilia.sharepoint.com/sites/it/Sdilene%20dokumenty/DokumentyIT/Návody%20NT/PokladnySQL%20a%20Oktab/Nastavení%20prodejny%20SQL%20na%20veletrh%20a%20po%20příjezdu%20-%20sit,%20terminal,%20router.docx](https://nobilistilia.sharepoint.com/sites/it/Sdilene%20dokumenty/DokumentyIT/Návody%20NT/PokladnySQL%20a%20Oktab/Nastavení%20prodejny%20SQL%20na%20veletrh%20a%20po%20příjezdu%20-%20sit,%20terminal,%20router.docx)\>
