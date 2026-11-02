---
vytvořeno: 2023-03-31T08:47
oddíl: "XML importy"
zdroj: "OneNote / Návody/Money S4 / XML importy"
tags:
  - onenote-import
  - k-revizi
---
Vyexportujeme ceník z Money do Excelu

![[XML importy - Nepojmenovaný obrázek.png]]

Máme připravený Excel soubor, potřebuje určit strukturu XML

Vyexportuji si XML

**Administrace =\> Výměna dat =\> Export XML**

nebo

![[XML importy - Nepojmenovaný obrázek-0.png]]

Vyexportovaný XML soubor si otevřu s PSPadu

Na první řádek v Excelu zkopíruji z XMLtagy s UTF8; S5Data a List a pod poslední řádek tabulky v Excelu zkopíruji uzavírací tagy s S5Data a List

Spojování řetězců v Excelu: **=CONCATENATE("\<PolozkaCeniku ObjectName";")**

![[XML importy - Nepojmenovaný obrázek-1.png]]

Kódová stránka UTF-8 BOM

Po zkopírování kódu z Excelu do PSPadu upravíme kód do odstavců pomocí této ikony

![[XML importy - Nepojmenovaný obrázek-2.png]]

- ⚠️ Musí se zvolit správné kódování

![[XML importy - Nepojmenovaný obrázek-3.png]]

Konfigurace importu

![[XML importy - Nepojmenovaný obrázek-4.png]]

**Import z XML =\> Přidat**
