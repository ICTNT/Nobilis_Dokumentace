---
vytvořeno: 2024-11-12T08:51
oddíl: "Nový B2C eshop"
zdroj: "OneNote / Návody/Money S4 / Nový B2C eshop"
tags:
  - onenote-import
  - k-revizi
---
- Nepracujeme s činnostmi (produktech, zákaznících)
- Cenové hladiny (nebudou v B2C)
- B2C nemá platbu na fakturu, nepotřebujeme příznak na zákazníka povolené platby
- Přidělený obchodník nepotřebujeme
- Zásoby, budeme řešit překročení minimálního množství pro B2C/B2B?
- Dodat XML zakazník + objednávka (ID skupiny pro zákazníky)
- Kody pro import zákazníků a objednávek
- Pozapínat parametry pro nový B2C v Money

XML objednávek do Money
- dle B2B

XML Zákazník:
- \<Group ID="00bff583-7a0d-4c31-b87b-a71e8e2d8ea5"/\>

- Vyhodit celý blok hladiny, obchodníci

Zápis do tabulky "System_XmlExchangeImport"

- Vše stejné, jen jiný KodImportu - EM_B2C

EmorfiqTesting: 35nhEb
