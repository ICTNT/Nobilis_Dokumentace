---
vytvořeno: 2023-07-18T08:24
oddíl: "Připojování dat do Excelu, Power BI"
zdroj: "OneNote / Návody/Dokumentace datových modelů / Připojování dat do Excelu, Power BI"
tags:
  - onenote-import
  - k-revizi
---
Návod pro připojení datových zdrojů, na které máte jako uživatelé oprávnění do aplikací (Excel, Power BI)

- **Obecné informace**
  - Pokud bude chtít průvodce připojení jméno a heslo - nastavte jako obrázek níže, platí pro všechna připojení

  ![[Připojování dat do Excelu, Power BI - MicrosoftTeams-image.png]]

- Pokud se vám zobrazí hláška "**podpora šifrování**" viz níže pak dejte pouze **OK**

![[Připojování dat do Excelu, Power BI - MicrosoftTeams-image2.png]]

**Vlastní připojení zdroje dat.**

Krok 1. Klikneme na "Data"

![[Připojování dat do Excelu, Power BI - krok1.jpg]]

Krok 2. Klikneme na "Načíst data" / "Z databáze" / "Z databáze SQL serveru"

![[Připojování dat do Excelu, Power BI - krok2.jpg]]

Krok 3. Napíšeme do pole Server **mssql.nobilis.local\MoneyS4** a klineme na OK

![[Připojování dat do Excelu, Power BI - krok3.jpg]]

Krok 4. Vybereme záložku "S4_Agenda_001……."

![[Připojování dat do Excelu, Power BI - krok4.jpg]]

Krok 5. Rozklikneme záložku "S4_Agenda_001……."

![[Připojování dat do Excelu, Power BI - krok5.jpg]]

Krok 6. Do vyhledávácího pole napíšeme název zdroje, který chceme připojit. V našem případě "Nobilis_Prodej_BI", klikneme na něj, aby zezelenal - vpravo uvidíme náhled dat - znamená to, že máme správně vybráno.

![[Připojování dat do Excelu, Power BI - krok6.jpg]]

Krok 7. Klikneme na šipku vedle pole "načíst" a zvolíme "načíst do" viz obrázek

![[Připojování dat do Excelu, Power BI - krok8a.jpg]]

Krok 8. Nastavíme konfiguraci připojení. Většinou chceme kontingenční tabulku, můžeme chtít pouze Tabulku, dá se rovnou udělat i kontingenční graf - záleží na potřebě. Důležité tlačítko je "Přidat tahle data do datového modelu" - díky němu můžete používat funkci "Jednoznačný počet". Pozor ale na to, že narůstá velikost excelu, takže pokud ji nepotřebujete, pak bez datového modelu.

![[Připojování dat do Excelu, Power BI - krok7.jpg]]

Krok 9. Nyní vidíme, že Excel načítá data z databáze a dole ukazuje, že stahuje. Zatím je nemá v excelovém sešitu.

![[Připojování dat do Excelu, Power BI - krok8.jpg]]

Krok 10. Nyní vidíme, že Excel načetl všechna data z databáze a nyní je zpracovává do "sebe" to je vidět na spodní liště

![[Připojování dat do Excelu, Power BI - krok9.jpg]]

Krok 11. Zde už pohled, který známe, datový model je připojen a můžete používat. **U velkých dat doporučuji nepoužívat "Automatické ukládání"** zejména pokud máte soubor pak uložený na SharePointu - výrazně to zpomaluje práci. Pracujte a potom uložte **ručně tlačítkem diskety v levém rohu.**

![[Připojování dat do Excelu, Power BI - krok10.jpg]]

![[Připojování dat do Excelu, Power BI - krok11.jpg]]
