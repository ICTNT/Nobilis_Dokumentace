---
vytvořeno: 2026-03-12T09:07
oddíl: "Zápis"
zdroj: "OneNote / Návody/Samba / Zápis"
tags:
  - onenote-import
  - k-revizi
---
| Název tagu | Typ | Povinný | Popis |   |
|---|---|---|---|---|
| PRODUCT_ID | String | ano | databázové ID produktu | MoneyS4 |
| TITLE | String | ano | název produktu | MoneyS4 |
| PRICE | Float, \>=0 | ano | cena produktu včetně DPH | Přes API |
| URL | String | ano | URL produktu | Přes API - pole se jmenuje Curl |
| IMAGE | String | ne | URL hlavního obrázku produktu přibližně 300px x 300px | ? |
| DESCRIPTION | String | ne | detailní popis produktu (čistý text bez HTML tagů) | Nemáme |
| BRAND | String | ne | výrobce (značka) produktu | Konstanta |
| STOCK | Integer, \>=0, default:1 | ne | počet kusů produktu na skladě | Money S4 |
| PRICE_BEFORE_DISCOUNT | Float, \>0, PRICE_BEFORE_DISCOUNT \> PRICE | ne | původní cena produktu před slevou včetně DPH | Viz PRICE |
| PRICE_BUY | Float, \>0 | ne | nákupní cena produktu (pro analýzu marže a zisku) | \- |
| PRICES | \[NAME, VALUE\] | ne | [speciální ceny pro různé skupiny zákazníků](https://doc.samba.ai/knowledge-base/datove-feedy/#skupiny-zakazniku-s-ruznymi-cenami), viz PRICE_CATEGORY v zákaznickém feedu | \- |
| CATEGORYTEXT | String | ne | cesta kategorií oddělena svislítkem "\|" | Přes API funkce v SQL |
| PRODUCT_LINE | String | ne | produktová řada | MoneyS4 - skupina produktu |
| VARIANT | Seznam produktů | ne | Viz varianty produktů. | Musí se dořešit - naše MASTERY nesplňují požadavky ze zadání |
| SHOW | Boolean, default: TRUE | ne | informace, jestli se má produkt propagovat | Defaultně TRUE |
| PARAMETER | \[NAME, VALUE\] | ne | další parametry produktu,NAME nemusí být unikátní vizte příklad | Případný dovývoj |

Z \<[https://doc.samba.ai/knowledge-base/datove-feedy/#objednavkovy-feed](https://doc.samba.ai/knowledge-base/datove-feedy/#objednavkovy-feed)\>

**Zdroj**

| Název tagu | Typ | Povinný | Popis |   |
|---|---|---|---|---|
| CUSTOMER_ID | String | ano | zákaznické ID | MoneyS4 |
| NEWSLETTER_FREQUENCY | Enum: every day \| special occasions \| never | ano | informace o odběru newsletteru (never = odhlášen) | Nedokážeme splnit. Povinné? |
| NLF_TIME | Datetime (as string) | ne | datetime ve formátu YYYY-MM-DDThh:mm:ss.sTZD [(více informací)](https://www.w3.org/TR/NOTE-datetime)<br>Čas změny stupně přihlášení | Co to je? |
| EMAIL | String | ne | validní emailová adresa. Jedná se o povinný prvek v případě, že na zákazníka budete odesílat newslettery. | MoneyS4 |
| REGISTRATION | Datetime (as string) | ne | datetime registrace zákazníka ve formátu YYYY-MM-DDThh:mm:ss.sTZD [(více informací)](https://www.w3.org/TR/NOTE-datetime), výchozí hodnota: "1. 1. 1970" | Buďto datum první objednávky nebo nic. |
| FIRST_NAME | String | ne | křestní jméno | Nemáme na to čistá data |
| LAST_NAME | String | ne | příjmení | Nemáme na to čistá data |
| ZIP_CODE | String | ne | PSČ | PSČ první objednávky? Z registrace zákazníka? |
| PHONE | String | ne | telefonní číslo ve formátu odpovídajícím International Telecommunication Union. Mělo by obsahovat symbol plus ("+") jako mezinárodní předponu, kód státu a samotné číslo, například"+420777123456" pro Českou Republiku | \- |
| SMS_FREQUENCY | Enum: every day \| special occasions \| never | ne | informace o odběru novinek formou SMS (never = odhlášen), výchozí hodnota: "never" | \- |
| DATA_PERMISSION | Enum: full \| do_not_personalize \| anonymized_only | ne | výchozí hodnota: "full" | Defaultně full |
| PRICE_CATEGORY | String | ne | skupina zákazníka pro určení [speciální ceny](https://doc.samba.ai/knowledge-base/datove-feedy/#skupiny-zakazniku-s-ruznymi-cenami) - viz PRICES v produktovém feedu | Nemáme |
| PARAMETERS | \[NAME, VALUE\] | ne | další parametry zákazníka, NAME nemusí být unikátní, vizte p | Nemáme |

Z \<[https://doc.samba.ai/knowledge-base/datove-feedy/#objednavkovy-feed](https://doc.samba.ai/knowledge-base/datove-feedy/#objednavkovy-feed)\>

*Odkud budeme brát zákazníky? Jak budeme* *řešit přírustky? Zákazníky umíme vytáhnout jen z Money = zákazník, který má nějakou objednávku, ne pouze registrovaný zákazník*

|   |   |   |   |   |
|---|---|---|---|---|
| **Název tagu** | **Typ** | **Povinný** | **Popis** |  |
| ORDER_ID | String | ano | ID objednávky | MoneyS4 |
| CUSTOMER_ID | String | ne | ID zákazníka | Ideálně z MoneyS4 |
| CREATED_ON | Datetime (as String) | ano | datetime vytvoření objednávky ve formátu YYYY-MM-DDThh:mm:ss.sTZD [(více informací)](https://www.w3.org/TR/NOTE-datetime). | MoneyS4 |
| ITEMS |  | ano | produkty v objednávce | MoneyS4 |
| FINISHED_ON | Datetime (as String) | ne | datetime dokončení objednávky ve formátu YYYY-MM-DDThh:mm:ss.sTZD [(více informací)](https://www.w3.org/TR/NOTE-datetime). Nepoužívejte nebo ponechte prázdné, pokud dosud nebyla objednávka dokončena. | Nemáme přesné časy |
| STATUS | String | ne | stav objednávky. Povolené hodnoty: created, finished, canceled. | MoneyS4 |
| EMAIL | String | ne | validní emailová adresa | MoneyS4 |
| PHONE | String | ne | telefonní číslo ve formátu odpovídajícím International Telecommunication Union. Mělo by obsahovat symbol plus ("+") jako mezinárodní předponu, kód státu a samotné číslo, například"+420777123456" pro Českou Republiku | \- |
| ZIP_CODE | String | ne | PSČ adresy doručení | MoneyS4 (může se změnit, pokud se sáhne do objednávky) |
| COUNTRY_CODE | String | ne | Mezinárodní identifikace země adresy doručení dle ISO 3166-1 alpha-2, např. "CZ" | Pouze CZ |

Z \<[https://doc.samba.ai/knowledge-base/datove-feedy/#objednavkovy-feed](https://doc.samba.ai/knowledge-base/datove-feedy/#objednavkovy-feed)\>

|   |   |   |   |   |
|---|---|---|---|---|
| **Název tagu** | **Typ** | **Povinný** | **Popis** |  |
| PRODUCT_ID | String | ano | ID produktu nebo produktové varianty | MoneyS4 |
| AMOUNT | Number (integer, \>0) | ne | počet kusů objednaného produktu (default: 1) | MoneyS4 |
| PRICE | Number (\>=0) | ne | sumární cena všech kusů daného produktu včetně DPH. | MoneyS4 |

Z \<[https://doc.samba.ai/knowledge-base/datove-feedy/#objednavkovy-feed](https://doc.samba.ai/knowledge-base/datove-feedy/#objednavkovy-feed)\>

*Požadavek je bez balného / dopravy - umíme odstranit hromadně* *pouze všechny textové položky - poukazy, kupony atd. Znamená,* *že nebude souhlasit cena objednávky.*
