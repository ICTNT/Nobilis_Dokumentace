---
vytvořeno: 2023-05-10T11:12
oddíl: "Zákazníci"
zdroj: "OneNote / Návody/Money S4 / Zákazníci"
tags:
  - onenote-import
  - k-revizi
---
\<?xml version="1.0" encoding="UTF-8"?\>

\<S5Data\>

\<FirmaList\>

\<Firma ID="F248BC07-3535-4834-B02A-347A821FBFED"\> \<!-- Párování na ID firmy. Zasílá se v rámci xml a systém ho převezme. --\>

\<Group ID="00bff583-7a0d-4c31-b87b-a71e8e2d8ea5"/\> \<!-- Párování na ID Skupiny. Zasílá se v rámci xml. Budou to ty tři OZ, zaměstnanec, Obchodní partner B2B, id dodáme --\>

\<Kod/\>

\<ICO/\>

\<DIC/\>

\<ICDPH/\> \<!-- Zde pro slováky plátce je to jejich IČDPH - Duplikuje se v DIČ --\>

\<PlatceDPH\>false\</PlatceDPH\> \<!-- Příznak plátce DPH --\>

\<ObchStat_ID\>3D3F235C-DF25-42AD-9CCE-1B460E3A3C5F\</ObchStat_ID\> \<!-- číselník států MS4 --\>

\<FaktStat_ID\>3D3F235C-DF25-42AD-9CCE-1B460E3A3C5F\</FaktStat_ID\>

\<ProvStat_ID\>3D3F235C-DF25-42AD-9CCE-1B460E3A3C5F\</ProvStat_ID\>

\<HlavniOsoba_ID\>78640940-903E-4616-9940-3A1E20CDCC60\</HlavniOsoba_ID\> \<!-- ID hlavní osoby, opakuje se níže. --\>

\<Nazev\>Alena Bártová\</Nazev\>

\<Adresy\>

\<OdlisnaAdresaProvozovny\>true\</OdlisnaAdresaProvozovny\> \<!-- zapíná "záložky" adres v MS4, pokud tento element chybí, data se v MS4 nepropíší --\>

\<ObchodniAdresa\>

\<Nazev\>Alena Bártová\</Nazev\>

\<Ulice\>Hradilova 51\</Ulice\>

\<Misto\>Klimkovice\</Misto\>

\<NazevStatu\>Česká republika\</NazevStatu\>

\<KodPsc\>74283\</KodPsc\>

\</ObchodniAdresa\>

\<Provozovna\>

\<Nazev\>Alena Bártová\</Nazev\>

\<Ulice\>Hradilova 51\</Ulice\>

\<Misto\>Klimkovice\</Misto\>

\<NazevStatu\>Česká republika\</NazevStatu\>

\<KodPsc\>74283\</KodPsc\>

\</Provozovna\>

\</Adresy\>

\<SeznamSpojeni ObjectName="Spojeni" ObjectType="List"\>

\<Spojeni ObjectName="Spojeni" ObjectType="Object" ID="28D92B21-7FE8-4210-9551-6309D0D2D4BB"\>

\<Poradi\>1\</Poradi\> \<!-- povinné --\>

\<SpojeniCislo\>+420774322876\</SpojeniCislo\>

\<Osoba_ID\>78640940-903E-4616-9940-3A1E20CDCC60\</Osoba_ID\> \<!-- ID hlavní osoby --\>

\<TypSpojeni_ID\>999A45ED-7C85-425C-8230-D58AE08A21C6\</TypSpojeni_ID\>

\<Vychozi\>false\</Vychozi\>

\</Spojeni\>

\<Spojeni ObjectName="Spojeni" ObjectType="Object" ID="70ADCACB-AF32-4812-AD7C-8FE5B04A6B93"\>

\<Poradi\>2\</Poradi\>

\<SpojeniCislo\>alena.bartova@email.cz\</SpojeniCislo\>

\<Osoba_ID\>78640940-903E-4616-9940-3A1E20CDCC60\</Osoba_ID\> \<!-- ID hlavní osoby --\>

\<TypSpojeni_ID\>DC748A02-43ED-4CC5-8264-4994B56919D0\</TypSpojeni_ID\>

\<Vychozi\>true\</Vychozi\> \<!-- email je výchozí spojení --\>

\</Spojeni\>

\</SeznamSpojeni\>

\<Osoby\>

\<HlavniOsoba ObjectName="Osoba" ObjectType="Object" ID="78640940-903E-4616-9940-3A1E20CDCC60"/\> \<!-- Definice hlavní osoby --\>

\<SeznamOsob ObjectName="Osoba" ObjectType="List"\>

\<Osoba ID="78640940-903E-4616-9940-3A1E20CDCC60"\> \<!-- ID hlavní osoby --\>

\<AdresaStat_ID\>3D3F235C-DF25-42AD-9CCE-1B460E3A3C5F\</AdresaStat_ID\>

\<Jmeno\>Alena\</Jmeno\>

\<Prijmeni\>Bártová\</Prijmeni\>

\<Nazev\>Alena Bártová\</Nazev\>

\<CisloOsoby\>1\</CisloOsoby\>

\<Adresa\>

\<Ulice\>Hradilova 51\</Ulice\>

\<Misto\>Klimkovice\</Misto\>

\<NazevStatu\>Česká republika\</NazevStatu\>

\<KodPsc\>74283\</KodPsc\>

\</Adresa\>

\</Osoba\>

\</SeznamOsob\>

\</Osoby\>

\<!-- Níže máme elementy pro cenovou hladinu, CRM - přidělený obchodník, změna činnosti zákazníka --\>

\<ObchodniPodminky\>

\<SeznamHladin ObjectName="FirmaCenovaHladina" ObjectType="List" DeleteItems="1"\> \<!-- Smažeme hladiny a založíme nové níže. --\>

\<FirmaCenovaHladina\>

\<CenovaHladina_ID\>d9ed50e8-77ad-4416-97f5-17859632cdb6\</CenovaHladina_ID\> \<!-- ID cenové hladiny vyšší než třezalkové, v případě, že není vyšší pak element je pouze jednou s pořadím 1 a hladinou třezalkovou --\>

\<Poradi\>1\</Poradi\> \<!-- Pořadí, povinný údaj --\>

\</FirmaCenovaHladina\>

\<FirmaCenovaHladina\>

\<CenovaHladina_ID\>da0268b7-f04e-4d15-b4c6-4b5541a15819\</CenovaHladina_ID\> \<!-- ID cenové hladiny třezalkové --\>

\<Poradi\>2\</Poradi\>

\</FirmaCenovaHladina\>

\</SeznamHladin\>

\</ObchodniPodminky\>

\<Cinnosti ObjectName="FirmaCinnost" ObjectType="List" DeleteItems="1"\> \<!-- Smažeme seznam činností. A založíme nové níže (pouze 1) --\>

\<FirmaCinnost\>

\<Cinnost_ID\>ae82179f-a499-45dd-8040-887bfdafd2c5\</Cinnost_ID\> \<!-- číselník činností MS4 --\>

\</FirmaCinnost\>

\</Cinnosti\>

\<CRM\>

\<Obchodnik ObjectName="FirmaObchodnik" ObjectType="List" DeleteItems="1"\> \<!-- Smažeme seznam obchodníků. --\>

\</Obchodnik\>

\</CRM\>

\</Firma\>

\<!-- Nutno založit nový job ke zpracování, kvůli překrývající se platnosti obchodníků, nelze bohužel v MS4 jinak --\>

\<Firma ID="F248BC07-3535-4834-B02A-347A821FBFED"\> \<!-- ID toho samého zákazníka --\>

\<CRM\>

\<Obchodnik\>

\<FirmaObchodnik\>

\<Obchodnik_ID\>19c1fe4b-00d6-4058-832d-ec7a97d18652\</Obchodnik_ID\> \<!-- ID obchodníka číselníku MS4 --\>

\<PlatnostDo\>9998-12-31T00:00:00\</PlatnostDo\> \<!-- takto je zápis pro MS4 - platnost nekonečno --\>

\<PlatnostOd\>2021-04-12T00:00:00\</PlatnostOd\> \<!-- zde prosím vyplnit datum od kdy má být obchodník přidělen, bude to zřejmě datum, kdy bude upraven v eshopu. --\>

\</FirmaObchodnik\>

\</Obchodnik\>

\</CRM\>

\</Firma\>

\</FirmaList\>

\</S5Data\>
