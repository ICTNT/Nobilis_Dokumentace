---
vytvořeno: 2023-05-22T14:50
oddíl: "Import nové položky + editace položky"
zdroj: "OneNote / Návody/Praxe / Import nové položky + editace položky"
tags:
  - onenote-import
  - k-revizi
---
Zadání:

Řádky 2 a 3 založit jako nové položky a u položky na řádku 4 změnit název produktu.

![[Import nové položky + editace položky - Nepojmenovaný obrázek.png]]

V Katalogu najdeme patřičnou skupinu (v tomto případe 02_KV) a vyexportujeme si XML některé položky z této skupiny.

![[Import nové položky + editace položky - Nepojmenovaný obrázek-0.png]]

Pro první dvě položky, které budeme přidávat, si musíme najít **ID Druhu položky**

**Druhy položek katalogu** =\> sloupec **ID** =\> řádek **MASTER** =\> vložíme toto ID do našeho excel souboru

=\> řádek **VYR** (vlastní výrobek) =\> vložíme toto ID do našeho excel souboru

![[Import nové položky + editace položky - Nepojmenovaný obrázek-1.png]]

To samé pro **ID produktu**, položky, u které měníme název

**Katalog** =\> klikneme na nějaké políčko ve sloupci **Katalog** =\> a vložíme kód z Excelu od Martina **XE0023A** =\> z odpovídajícího řádku zkopíruji **ID** a vložím do Excel souboru

![[Import nové položky + editace položky - Nepojmenovaný obrázek-2.png]]

Předepíšeme si XML soubor v Excelu ( zelené sloupce si doplníme a ID najdeme v Money )

![[Import nové položky + editace položky - Nepojmenovaný obrázek-3.png]]

![[Import nové položky + editace položky - Nepojmenovaný obrázek-4.png]]

![[Import nové položky + editace položky - Nepojmenovaný obrázek-5.png]]

Zkopírujeme do PSPadu.

Pokud máme vše správně, mělo by se nám všechno takto zarovnat po kliknutí na **Upraví HTML kód pro větší čítelnost**

![[Import nové položky + editace položky - Nepojmenovaný obrázek-6.png]]

- ⚠️ Pozor na správné kódování **Unicode UTF-8 BOM** (v záložce **Kódová stránka**)

- ⚠️ V elementech jako je **INCI** apod se můžou vyskytovat znaky **\< \>**, také XML nenaimportujeme, protože se to bere jako element. Pokud v textu použijeme např. tag pro tučné písmo **\<b\>** musíme celý text obalit tímto tagem **\<\![CDATA\[** *text* **\]\]\>** (jinak by Money nebralo **\<b\>** jako tag a písmo bychom neměli tučně)

Uložíme kód jako XML soubor.

Nastavíme se v Money konfiguraci importu.

**Administrace** =\> **Výměna dat** =\> **Import z XML**

![[Import nové položky + editace položky - Nepojmenovaný obrázek-7.png]]

Přidáme novou konfiguraci nebo pokud máme už jinou svoji, tak ji můžeme upravit

Vyplňujeme **Kód**, **Název** a **Vstupní XML soubor** = adresa k našemu XML souboru

![[Import nové položky + editace položky - Nepojmenovaný obrázek-8.png]]

Pokud přidáváme novou konfiguraci dáme **Přidat** opravujeme existující konfiguraci dáme **Opravit**

Pro přidání 1. položky a editaci 3. položky

![[Import nové položky + editace položky - Nepojmenovaný obrázek-9.png]]

![[Import nové položky + editace položky - Nepojmenovaný obrázek-10.png]]

Musíme XML naimportovat ještě jednou (= prvním importem jsme nahráli pouze master, takže je potřeba ještě variantu)

![[Import nové položky + editace položky - Nepojmenovaný obrázek-11.png]]

![[Import nové položky + editace položky - Nepojmenovaný obrázek-12.png]]

![[Import nové položky + editace položky - Nepojmenovaný obrázek-13.png]]

Řešení:

![](data:image/svg+xml;base64,PHN2ZyBzdHlsZT0iaGVpZ2h0OiAxMzIuMDJweDsgbGVmdDogMzcuNjlweDsgcG9pbnRlci1ldmVudHM6IG5vbmU7IHBvc2l0aW9uOiBhYnNvbHV0ZTsgdG9wOiAyNzEwLjdweDsgd2lkdGg6IDgyMi4wM3B4OyIgdmlld2JveD0iMzcuNjkgMjcxMC43IDgyMi4wMyAxMzIuMDIiPjxwYXRoIGQ9Ik0gNjMgMjgzMCBsIDAuMTIgMCAwLjM5IDAgMC43IDAgMC44NiAwIDAuODkgMCAxLjA1IDAgMC45MyAwIDEuMTcgMCAxLjI0IDAgMS4yOCAwIDEuMzIgMCAxLjY3IDAgMi4wMiAwIDIuMTggMCAyLjQ1IDAgMi42MSAwIDMuMDMgMCAzLjM0IDAgMy40NiAwIDMuNzMgMCAzLjgxIDAgMy42NiAwIDMuNDYgMCAzLjUgMCAzLjI3IDAgMy4xNSAwIDIuODQgMCAyLjQ1IDAgMi4yOSAwIDIuMDIgMCAxLjc5IDAgMS43MSAwIDEuOTQgMCAxLjc5IDAgMS43NSAwIDEuNjcgMCAyLjE0IDAgMi4xOCAwIDIuMjkgMCAyLjY0IDAgMi43MiAwIDIuNjEgMCAyLjg0IDAgMi45MiAwIDIuOCAwIDIuNzYgMCAyLjcyIDAgMi43NiAwIDIuNjQgMCAyLjI5IDAgMi4zMyAwIDIuNjggMCAyLjk2IDAgMy4xNSAwIDMuMTUgMCAzLjIzIDAgMy4xNSAwIDMuMTUgMCAyLjk2IDAgMi45MiAwIDIuODggMCAyLjg0IDAgMy4wMyAwIDIuOCAwIDIuOTIgMCAyLjg0IDAgMi44OCAwIDIuOTYgMCAzLjAzIDAgMy4xOSAwIDIuOTYgMCAyLjggMCAyLjYxIDAgMi42MSAwIDIuNjggMCAyLjg0IDAgMi45OSAwIDIuODQgMCAyLjkyIDAgMy4xOSAwIDMuNDIgMCAzLjY2IDAgMy43MyAwIDMuNTQgMCAzLjQyIDAgMy4wNyAwIDIuOTYgMCAyLjcyIDAgMi40OSAwIDIuNTMgMCAyLjQxIDAgMi41MyAwIDIuNDkgMCAyLjYxIDAgMi4zNyAwIDIuMTggMCAyLjI2IDAgMi4yOSAwIDIuMDYgMCAxLjk0IDAgMS45NCAwIDEuODMgMCAxLjg3IDAgMi4wNiAwIDIuNDEgMCAyLjU3IDAgMi45OSAwIDMuMzQgMCAzLjU0IDAgMy43MyAwIDQuMDQgMCA0LjAxIDAgNC4wNCAwIDQuMDQgMCAzLjg5IDAgMy41IDAgMy4yMyAwIDMuMDMgMCAyLjY4IDAgMi40MSAwIDIuMSAwIDIuMzMgMCAyLjYxIDAgMi45NiAwIDMuMDMgMCAzLjExIDAgMy4xOSAwIDMuMzQgMCAzLjE1IDAgMy4yMyAwIDMuNDIgMCAzLjQ2IDAgMy40MiAwIDMuNTQgMCAzLjY5IDAgNC4wMSAwIDQuMTYgMCA0LjMyIDAgNC4zOSAwIDQuMzYgMCA0LjM5IDAgNC4zNiAwIDQuMjQgMCA0LjM5IDAgNC42NyAwIDQuOSAwIDQuODIgMCA0LjUxIDAgNC44MiAwIDQuODIgMCA0LjUxIDAgNC40MyAwIDQuMTYgMCA0LjAxIDAgNC4wNCAwIDQuMDQgMCA0LjAxIDAgNC40MyAwIDQuNjcgMCA0LjYzIDAgNC40NyAwIDQuMDggMCAzLjY5IDAgMy40NiAwIDMuMDcgMCAyLjkyIDAgMi45NiAwIDIuNzYgMCAyLjY4IDAgMi42MSAwIDIuNDkgMCAyLjE4IDAgMS45OCAwIDEuNjcgMCAxLjM2IDAgMS4yNCAwIDEuNCAwIDEuMjggMCAxLjQ4IDAgMS41NiAwIDEuNzEgMCAxLjk0IDAgMi4wNiAwIDEuOTggMCAyLjA2IDAgMi4xNCAwIDIuMDYgMCAxLjk4IDAgMi4wNiAwIDIuMSAwIDIuMzMgMCAyLjI2IDAgMi4xOCAwIDIuMjYgMCAyLjA2IDAgMi4xIDAgMi4yMiAwIDIuMSAwIDIuMDYgMCAxLjk4IDAgMS45NCAwIDEuODcgMCAxLjc5IDAgMS42NyAwIDEuNjcgMCAxLjc1IDAgMS43NSAwIDEuNzkgMCAxLjg3IDAgMS43OSAwIDEuNzUgMCAxLjY3IDAgMS41OSAwIDEuNDggMCAxLjU2IDAgMS40IDAgMS4yOCAwIDEuMzYgMCAxLjQgMCAxLjI0IDAgMS4xNyAwIDEuMjggMCAxLjIxIDAgMS4yOCAwIDEuMzYgMCAxLjQgMCAxLjM2IDAgMS4zNiAwIDEuNCAwIDEuMzYgMCAxLjIxIDAgMS40NCAwIDEuNCAwIDEuMjEgMCAxLjI0IDAgMS4yOCAwIDEuMzYgMCAxLjI4IDAgMS4yMSAwIDEuMTcgMCAxLjA5IDAgMS4yMSAwIDEuMjggMCAxLjMyIDAgMS4xMyAwIDEuMDUgMCAxLjA5IDAgMS4wMSAwIDEuMDkgMCAxLjA1IDAgMS4wMSAwIDEuMDUgMCAxLjAxIDAgMS4wNSAwIDEuMDEgMCAxLjA1IDAgMS4wMSAwIDEuMDUgMCAxLjAxIDAgMS4yOCAwIDEuMjggMCAxLjU2IDAgMS42NyAwIDEuNjcgMCAxLjg3IDAgMi4zNyAwIDIuNTcgMCAyLjUzIDAgMi40MSAwIDIuMTQgMCAxLjk0IDAgMS42NyAwIDEuNDggMCAxLjMyIDAgMS40NCAwIDEuMjggMCAxLjIxIDAgMS4yOCAwIDEuMzYgMCAxLjU2IDAgMS40OCAwIDEuNCAwIDEuNDggMCAxLjU2IDAgMS41OSAwIDEuNDQgMCAxLjQ4IDAgMS41MiAwIDEuNTYgMCAxLjU2IDAgMS42NyAwIDEuOTEgMCAyLjAyIDAgMS45OCAwIDEuOTEgMCAxLjg3IDAgMS44NyAwIDIuMDYgMCAyLjI2IDAgMi4zMyAwIDIuMjYgMCAyLjQxIDAgMi4zMyAwIDIuMjYgMCAyLjE4IDAgMi4xNCAwIDEuOTEgMCAxLjk0IDAgMS44NyAwIDEuODcgMCAxLjc5IDAgMS41OSAwIDEuNDQgMCAxLjMyIDAgMS4zMiAwIDEuMjEgMCAxLjI4IDAgMS4zNiAwIDEuNCAwIDEuMjQgMCAxLjMyIDAgMS4yOCAwIDEuNDQgMCAxLjQgMCAxLjM2IDAgMS4yMSAwIDEuMjggMCAxLjI4IDAgMS41NiAwIDEuNTYgMCAxLjQgMCAxLjI4IDAgMS4wOSAwIDEuMTcgMCAxLjA5IDAgMS4wNSAwIDEuMDkgMCAxLjAxIDAgMC45NyAwIDEuMDUgMCAwLjkzIDAgMS4wNSAwIDEuMDkgMCAxLjAxIDAgMC44NiAwIDAuNzggMCAwLjcgMCAwLjc4IDAgMC45NyAwIDEuMDEgMCAwLjk3IDAgMC43OCAwIiBmaWxsPSJub25lIiBvcGFjaXR5PSIwLjUwIiBzdHJva2U9InJnYigwLCAyNDksIDApIiBzdHJva2UtbGluZWNhcD0ic3F1YXJlIiBzdHJva2UtbGluZWpvaW49ImJldmVsIiBzdHJva2Utd2lkdGg9IjIzIj48L3BhdGg+PHBhdGggZD0iTSA0OSAyNzIyIGwgMCAwIDAuMiAwIDAuNjYgMCAxLjE4IDAgMS40NSAwIDEuOTcgMCAyLjE3IDAgMi41IDAgMi4zNyAwIDIuOTYgMCAzLjAyIDAgMi45NiAwIDIuODMgMCAyLjg5IDAgMy4wOSAwIDMuMTYgMCAzLjIyIDAgMi45NiAwIDMuMDIgMCAzLjI5IDAgMy4wMiAwIDIuNyAwIDIuNjMgMCAyLjMgMCAyLjE3IDAgMS45NyAwIDIuMzcgMCAyLjk2IDAgMi44OSAwIDIuODMgMCAyLjc2IDAgMi43IDAgMi4zNyAwIDIuMSAwIDIuMyAwIDIuMTcgMCAyLjE3IDAgMi4xNyAwIDIuMzcgMCAyLjE3IDAgMi4xIDAgMi4xNyAwIDIuMyAwIDIuMTcgMCAyLjUgMCAyLjM3IDAgMi4zIDAgMi4xNyAwIDIuMzcgMCAyLjQzIDAgMi4wNCAwIDIuMyAwIDIuMTcgMCAyLjE3IDAgMS45NyAwIDIuMzcgMCAyLjcgMCAyLjk2IDAgMy4yOSAwIDIuODMgMCAzLjE2IDAgMy4zNSAwIDMuNjggMCAzLjk0IDAgNC4wMSAwIDMuODggMCAzLjgxIDAgMy45NCAwIDMuODEgMCAzLjIyIDAgMi43NiAwIDIuODMgMCAzLjAyIDAgMy4zNSAwIDMuMjkgMCAzLjM1IDAgMy42OCAwIDQuMDEgMCA0LjA4IDAgNC4zNCAwIDQuMDEgMCAzLjg4IDAgMy44MSAwIDMuNzUgMCAzLjU1IDAgMy42MiAwIDMuODggMCA0LjI3IDAgNC4zNCAwIDQuNDcgMCA0LjM0IDAgNC40NyAwIDQuNTQgMCA0LjQ3IDAgNC41NCAwIDQuNjcgMCA0LjY3IDAgNC44IDAgNC40NyAwIDQuMzQgMCA0LjQ3IDAgNC4zNCAwIDQuMzQgMCA0LjE0IDAgMy42OCAwIDMuNjIgMCAzLjU1IDAgMy45NCAwIDMuNjIgMCAzLjQyIDAgMy40MiAwIDMuMjIgMCAzLjYyIDAgMy44MSAwIDMuODggMCAzLjQ4IDAgMy4yOSAwIDMuMjIgMCAzLjQyIDAgMy4zNSAwIDIuODMgMCAyLjk2IDAgMy4xNiAwIDMuNDggMCAzLjY4IDAgMy40OCAwIDMuMTYgMCAzLjIyIDAgMi45NiAwIDMuMDIgMCAyLjgzIDAgMy4wMiAwIDMuNDIgMCAzLjAyIDAgMy4xNiAwIDIuODMgMCAyLjk2IDAgMy4xNiAwIDMuMDIgMCAyLjgzIDAgMi44MyAwIDIuNyAwIDIuNSAwIDIuNDMgMCAyLjE3IDAgMi4yNCAwIDIuMjQgMCAyLjI0IDAgMi4xNyAwIDEuOTcgMCAxLjk3IDAgMi4wNCAwIDIuMyAwIDIuMTcgMCAyLjM3IDAgMi44MyAwIDIuNzYgMCAyLjUgMCAyLjYzIDAgMi41NiAwIDIuNDMgMCAyLjE3IDAgMi4yNCAwIDIuMTcgMCAyLjEgMCAxLjk3IDAgMS44NCAwIDEuODQgMCAxLjcxIDAgMS44NCAwIDEuNzcgMCAxLjY0IDAgMS43MSAwIDEuNjQgMCAxLjUxIDAgMS44NCAwIDEuNzcgMCAxLjcxIDAgMS4zMSAwIDEuMzEgMCAxLjMxIDAgMS4zMSAwIDEuNTEgMCAxLjcxIDAgMS42NCAwIDEuNzEgMCAxLjg0IDAgMS45NyAwIDEuNjQgMCIgZmlsbD0ibm9uZSIgb3BhY2l0eT0iMC41MCIgc3Ryb2tlPSJyZ2IoMCwgMjQ5LCAwKSIgc3Ryb2tlLWxpbmVjYXA9InNxdWFyZSIgc3Ryb2tlLWxpbmVqb2luPSJiZXZlbCIgc3Ryb2tlLXdpZHRoPSIyMyI+PC9wYXRoPjwvc3ZnPg==)
