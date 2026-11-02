---
vytvořeno: 2023-06-22T13:14
oddíl: "Uzávěrka"
zdroj: "OneNote / Návody/Pokladní zařízení SQL / Uzávěrka"
tags:
  - onenote-import
  - k-revizi
---
**Prodejna ERP -** **Manažer** =\> Přehledy =\> Doklady

![[Uzávěrka - Nepojmenovaný obrázek.png]]

Zvolíme období (pro jistotu včetně "dneška", kdyby už proběhly nějaké prodeje)

V **Money** =\> Prodejní místa Centrály PSQL

![[Uzávěrka - Nepojmenovaný obrázek-0.png]]

Zvolíme prodejnu, v které děláme uzavírku a dáme **Dávkový import**

![[Uzávěrka - Nepojmenovaný obrázek-1.png]]

Kontrola v transakci **Prodejky vydané**

Do filtru **Hodnota / Dolní meze** (V **Manažerovi** je to **Uzávěrka Č.**)

![[Uzávěrka - Nepojmenovaný obrázek-2.png]]

Dáme **Zaúčtování prodeje** - konfiguraci necháme stejnou

=\> Opravíme datum

=\> **Provést zaúčtování prodejek**

![[Uzávěrka - Nepojmenovaný obrázek-3.png]]

V **Manažeru** neřešit **"X"** ve sloupci **"Z"** - náhledová uzávěrka / otevřená

**\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

**Supervizor pokladny** 159753

![](data:image/svg+xml;base64,PHN2ZyBzdHlsZT0iaGVpZ2h0OiA1Mi45M3B4OyBsZWZ0OiA4NS41OXB4OyBwb2ludGVyLWV2ZW50czogbm9uZTsgcG9zaXRpb246IGFic29sdXRlOyB0b3A6IDYyNi43M3B4OyB3aWR0aDogMTIzLjAxcHg7IiB2aWV3Ym94PSI4NS41OSA2MjYuNzMgMTIzLjAxIDUyLjkzIj48cGF0aCBkPSJNIDExMyA2NjggbCAwLjExIDAgMC4zOCAwIDAuNjggMCAwLjgzIDAgMC44NyAwIDEuMDIgMCAxLjA2IDAgMC45OCAwIDEuMDYgMCAxLjAyIDAgMC45OCAwIDEuMDIgMCAwLjk4IDAgMS4wMiAwIDAuOTggMCAwLjk4IDAgMS4wMiAwIDAuOTggMCAxLjAyIDAgMC45OCAwIDEuMDIgMCAwLjk4IDAgMS4wMiAwIDAuOTggMCAxLjI1IDAgMS4yNSAwIDEuMjUgMCAxLjEzIDAgMC44NyAtMC4xMSAwLjgzIC0wLjE1IDAuNzkgLTAuMTkgMC44NyAtMC4xOSAwLjgzIC0wLjExIDAuOTQgLTAuMDQgMC45OCAtMC4wOCAxLjI1IDAgMS4yNSAwLjA4IDEuNCAwIDEuMzYgLTAuMDggMS4zMiAwIDEuMTcgMC4wOCAxLjEzIDAgMS4xMyAtMC4wOCAxLjA2IDAgMC45NCAwLjA4IDAuOTggMCAxLjAyIC0wLjA4IDAuOTggMCAwLjk4IDAuMDggMS4yOSAwIDEuMjUgLTAuMDggMS4zNiAwIDEuNTEgMC4wOCAxLjU1IDAgMS41MSAtMC4wOCAxLjI5IDAgMS4yOSAwLjA4IDEuMSAwIDEuMTMgLTAuMDggMS4wNiAwIDAuOTQgMC4wOCAwLjk4IDAgMS4wMiAtMC4wOCAwLjg3IDAgMC45OCAwLjA4IDAuOTQgMCAxLjEzIC0wLjA4IDEuMzIgMCAxLjM2IDAuMDggMS40IDAgMS40NCAtMC4wOCAxLjI5IDAgMS4xMyAwLjA4IDEuMTMgMCAxLjA2IC0wLjA4IDAuOTQgMCAwLjk4IDAuMDggMS4wMiAwIDAuODcgLTAuMDggMC43NiAwIiBmaWxsPSJub25lIiBvcGFjaXR5PSIwLjUwIiBzdHJva2U9InJnYigyNTUsIDM3LCAwKSIgc3Ryb2tlLWxpbmVjYXA9InNxdWFyZSIgc3Ryb2tlLWxpbmVqb2luPSJiZXZlbCIgc3Ryb2tlLXdpZHRoPSIxOSI+PC9wYXRoPjxwYXRoIGQ9Ik0gOTUgNjM3IGwgMC4xMSAwIDAuMzggMCAwLjY4IDAgMC44MyAwIDAuODcgMCAxLjEzIDAgMS4zMiAwIDEuMjkgMCAxLjI1IDAgMS4zMiAwIDEuMjUgMCAxLjIxIDAgMS4yNSAwIDEuMjkgMCAxLjI1IDAgMS4yMSAwIDEuMTMgMCAxLjA2IDAgMS4wNiAwIDEuMTMgMCAxLjI5IDAgMS4zMiAwIDEuNTEgMCAxLjU1IDAgMS42MyAwIDEuODEgMCAyIDAgMS45MyAwIDIgMCAxLjgxIDAgMS42MyAwIDEuNDQgMCAxLjMyIDAgMC45OCAtMC4xMSAwLjg3IC0wLjE1IDAuNzYgLTAuMTkgMC44MyAtMC4xOSAwLjg3IC0wLjExIDEuMDYgLTAuMDQgMS4yNSAtMC4wOCAxLjMyIDAgMS4yNSAwLjA4IDEuMTcgMCAxLjEzIC0wLjA4IDEuMDYgMCAxLjA2IDAuMDggMS4xMyAwIDEuMDYgLTAuMDggMS4wNiAwIDEuMDIgMC4wOCAwLjk0IDAgMC45OCAtMC4wOCAxLjA2IDAgMS4wMiAwLjA4IDEuMDYgMCAwLjk4IC0wLjA4IDEuMjEgMCAxLjEgMC4wOCAxLjIxIDAgMS4xNyAtMC4wOCAxLjAyIDAgMS4wNiAwLjA4IDAuODcgMCIgZmlsbD0ibm9uZSIgb3BhY2l0eT0iMC41MCIgc3Ryb2tlPSJyZ2IoMjU1LCAzNywgMCkiIHN0cm9rZS1saW5lY2FwPSJzcXVhcmUiIHN0cm9rZS1saW5lam9pbj0iYmV2ZWwiIHN0cm9rZS13aWR0aD0iMTkiPjwvcGF0aD48L3N2Zz4=)
