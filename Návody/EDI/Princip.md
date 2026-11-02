---
vytvořeno: 2023-03-31T08:51
oddíl: "Princip"
zdroj: "OneNote / Návody/EDI / Princip"
tags:
  - onenote-import
  - k-revizi
---
- Využívá asi 7 zákazníků - lékárny (Pilulka), Rohlik.cz

- Automatické objednávání zboží mezi jednotlivými systémy

- Dodavatel, odběratel i položky mají nějaké čárové kódy (G piny)

- Zákazník předá zprávu v XML komunikátoru (u nás Grit). Ten ji přijme, zpracuje, vyhodnotí, jestli je validní a předá ji nám - my si ji přeložíme pro Money

- ⚠️ Jsou přísné podmínky dodání - ve chvíli kdy potvrdíme nesmí se stát, že nedodáme - velké pokuty

- Na vm21 je služba komunikátor

- Soubor "DESADV" - dodací listy vydané

- Složky "in" (co posílají oni nám) a "out" (co posíláme my jim)

- Když má objednávka v popisu ORION = objednávka z EDI

- Mají přednostní odbavení / nejvyšší prioritu - 1

- EDI objednávky se řídi ručně (k alokaci apod). Objednávka se naimportuje, nemá žádný stav. Někdo objednávku zkontroluje, případně upraví a požádá o alokaci.

- Z EDI objednávek se nevystavují automaticky faktury, protože EDI musí mít dodací listy. Účtárna je dělá ručně.
