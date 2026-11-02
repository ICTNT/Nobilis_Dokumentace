---
vytvořeno: 2023-05-10T11:13
oddíl: "Objednávky přijaté"
zdroj: "OneNote / Návody/Money S4 / Objednávky přijaté"
tags:
  - onenote-import
  - k-revizi
---
\<?xml version="1.0" encoding="UTF-8"?\>

\<S5Data\>

\<ObjednavkaPrijataList\>

\<ObjednavkaPrijata ID="E9575EFF-F8B8-49DA-B87D-0DD7C1503C18"\> \<!-- Generováno Eshopem. Pokud mažu položky musí ID zůstat pro dohledání objednávky, kde chci provádět mazání --\>

\<Group ID="CBC2E787-6849-41D7-A282-CEB137814BD9"/\> \<!-- zde doplníme ID skupiny podle typu objednávky --\>

\<VariabilniSymbol\>261242\</VariabilniSymbol\> \<!-- číslo objednávky 6ti místná řada --\>

\<Nazev\>Eshop 261242\</Nazev\> \<!-- prefix + číslo objednávky 6ti místná řada --\>

\<ICO/\>

\<DIC/\>

\<ICDPH/\> \<!-- Pro SK plátce Opakuje se v DIČ, jinak prázdné pro CZ--\>

\<Odkaz\>VO-2020-110-001793\</Odkaz\> \<!-- Interní číslo objednávky zadané v eshopu do formuláře--\>

\<DatumVystaveni\>2021-04-01 00:26:01\</DatumVystaveni\> \<!-- Datum vystavení objednávky na eshopu --\> (V money není pole datetime, přicházíme o časový údaj)

\<VytvoreniObjednavky_UserData\>2021-04-01 00:26:01\</VytvoreniObjednavky_UserData\> \<!-- Datum vystavení objednávky na eshopu --\>

\<PozDatumExpedice_UserData\>2021-04-01 00:00:00\</PozDatumExpedice_UserData\> \<!-- Datum požadované expedice zákazníkem, čas 00:00:00 pouze den --\>
 \<Obchodnik_ID\>bccf2576-f4a6-44c4-80f7-377d10b63d54\</Obchodnik_ID\> \<!-- ID přiděleného obchodníka z konfigurace seznamu obchodníků v eshopu, kde ID vložíme ručně. --\>

\<Poznamka/\> \<!-- Poznámka z objednávky --\>

\<ZpusobDopravy_ID\>E5C391DC-6DF8-4283-8A29-9B6C024B65CD\</ZpusobDopravy_ID\> \<!-- číselník MS4 --\>

\<ZpusobPlatby_ID\>9728C883-FD62-496E-9162-DE9616D5A320\</ZpusobPlatby_ID\> \<!-- číselník MS4 --\>

\<CenovaHladinaObj_UserData\>maloobchodník\</CenovaHladinaObj_UserData\> \<!-- textem zápis cenové hladiny objednávky (pro interní statistiky) --\>

\<StavObjednavky_UserData\>Nová\</StavObjednavky_UserData\> \<!-- textem zápis změny stavu objednávky Nová/Přijato/Storno --\>

\<Mena_ID\>00F9ADB2-D300-42C3-9240-AE1320B019CC\</Mena_ID\> \<!-- číselník MS4 --\>

\<CelkovaCastka\>297\</CelkovaCastka\>

\<CelkovaCastkaCM\>297\</CelkovaCastkaCM\>

\<AdresaKontaktniOsoba_ID\>78640940-903E-4616-9940-3A1E20CDCC60\</AdresaKontaktniOsoba_ID\> \<!-- reference na xml zákazníka \<Osoby\>

\<HlavniOsoba ObjectName="Osoba" ObjectType="Object" ID="78640940-903E-4616-9940-3A1E20CDCC60"/\>

\<SeznamOsob ObjectName="Osoba" ObjectType="List"\>

\<Osoba ID="78640940-903E-4616-9940-3A1E20CDCC60"\> --\>

\<AdresaPrijemceFakturyKontaktniOsoba_ID\>78640940-903E-4616-9940-3A1E20CDCC60\</AdresaPrijemceFakturyKontaktniOsoba_ID\> \<!-- viz výše --\>

\<Adresa\>

\<Firma ID="F248BC07-3535-4834-B02A-347A821FBFED"/\> \<!-- reference na xml zakaznika \<FirmaList\>\<Firma ID="F248BC07-3535-4834-B02A-347A821FBFED"\>--\>

\</Adresa\>

\<AdresaKoncovehoPrijemceStat_ID\>3D3F235C-DF25-42AD-9CCE-1B460E3A3C5F\</AdresaKoncovehoPrijemceStat_ID\> \<!-- číselník MS4, stát doručovací adresy (ekokom) --\>

\<AdresaKoncovehoPrijemce\>

\<KontaktniOsobaNazev\>Alena Bártová\</KontaktniOsobaNazev\>

\<KontaktniOsobaJmeno\>Alena\</KontaktniOsobaJmeno\>

\<KontaktniOsobaPrijmeni\>Bártová\</KontaktniOsobaPrijmeni\>

\<Nazev\>Alena Bártová\</Nazev\> \<!-- zde pokud není vyplněn název firmy, pak vkládáme osobu, pouze v případě, že to bude vyžadovat přepravce, WMS apod. Pro MS4 jinak není potřeba, expedice z MS4 už nebudeme dělat--\>

\<Ulice\>Hradilova 51\</Ulice\>

\<Misto\>Klimkovice\</Misto\>

\<PSC\>74283\</PSC\>

\<Stat\>Česká republika\</Stat\>

\<Email\>alena.bartova@email.cz\</Email\>

\<Telefon\>+420774322876\</Telefon\>

\<Mobil/\>

\</AdresaKoncovehoPrijemce\>

\<AdresaPrijemceFaktury\>

\<Firma ID="F248BC07-3535-4834-B02A-347A821FBFED"/\> \<!-- reference na xml zakaznika \<FirmaList\>\<Firma ID="F248BC07-3535-4834-B02A-347A821FBFED"\>--\>

\</AdresaPrijemceFaktury\>

\<Polozky ObjectName="PolozkaObjednavkyPrijate" ObjectType="List" DeleteItems="1"\> \<!-- mazání podřízených seznamů následné importování všech položek objednávek znovu. Vždy nove GUID položky. Lze použít do doby, než je položka vyřízena (vyskladněna)--\>

\<PolozkaObjednavkyPrijate ID="A613FB81-1AC3-4775-9671-2283237115D8"\>

\<JednCena\>139\</JednCena\> \<!-- pokud je sleva, pak cena po slevě za jednotku--\>

\<JednCenaCM\>139\</JednCenaCM\> \<!-- pokud je sleva, pak cena po slevě za jednotku--\>

\<Sleva\>0.00\</Sleva\> \<!-- hodnota slevy--\>

\<DPH\>

\<Sazba\>21.00\</Sazba\>

\</DPH\>

\<!-- \<DruhSazbyDPH\>2\</DruhSazbyDPH\> --\> \<!-- Zde pozor. Pokud je TypCeny=0 a zároveň Sazba=0.00 pak se přidává element \<DruhSazbyDPH\>2\</DruhSazbyDPH\> --\>

\<TypCeny\>1\</TypCeny\> \<!-- TypCeny má hodnoty 1 - s DPH, 0- bez DPH --\>

\<Mnozstvi\>1\</Mnozstvi\>

\<Nazev\>Kojenecký olej na zoubky Jakoubek 10 ml\</Nazev\> \<!-- přesný název z view Artikl.Nazev--\>

\<Poznamka/\>

\<Katalog\>N1918B\</Katalog\>

\<Jednotka\>ks\</Jednotka\>

\<ObsahPolozky ID="73A2D742-4BF8-4474-B9A8-DE1CF8B34E38"\> \<!-- Vždy generujeme ID--\>

\<Mnozstvi\>1\</Mnozstvi\> \<!-- Množství položek--\>

\<Artikl_ID\>66479904-38D0-494C-A7A1-590174974F20\</Artikl_ID\> \<!-- zde ID artiklu z view Artikl.ID--\>

\</ObsahPolozky\>

\<TypObsahu EnumValueName="SObsahem"\>1\</TypObsahu\> \<!-- Pokud je zapsáno takto, znamená to, že je položka produkt a vyžadujeme ho v objednávce nikoli textem, ale s propojením na sklad a import se kouká do obsahu--\>

\</PolozkaObjednavkyPrijate\>

\<PolozkaObjednavkyPrijate ID="329BA02E-FF5A-4665-B7AE-29E058B45DA6"\>

\<JednCena\>109\</JednCena\>

\<JednCenaCM\>109\</JednCenaCM\>

\<Sleva\>0.00\</Sleva\>

\<DPH\>

\<Sazba\>21.00\</Sazba\>

\</DPH\>

\<NepodlehatSleveDokladu\>true\</NepodlehatSleveDokladu\> \<!--Pokud přichází s daty Artikl.NepodlehaSlevam true (doplníme do zdroje), tak prosím do objednávky poslat zpět do MS4, jinak element není--\>

\<TypCeny\>1\</TypCeny\>

\<Mnozstvi\>1\</Mnozstvi\>

\<Nazev\>Inhalační tyčinka proti nevolnosti\</Nazev\>

\<Poznamka/\>

\<Katalog\>N1650B\</Katalog\>

\<Jednotka\>ks\</Jednotka\>

\<ObsahPolozky ID="5F12DC49-56FB-49A6-91E1-C394CC5F8980"\>

\<Mnozstvi\>1\</Mnozstvi\>

\<Artikl_ID\>770CF4E8-AD53-46F6-A218-54BDDAED519C\</Artikl_ID\>

\</ObsahPolozky\>

\<TypObsahu EnumValueName="SObsahem"\>1\</TypObsahu\>

\</PolozkaObjednavkyPrijate\>

\<PolozkaObjednavkyPrijate ID="4EF455E8-2691-4ECB-97F3-070BC215CD17"\>

\<JednCena\>49\</JednCena\>

\<JednCenaCM\>49\</JednCenaCM\>

\<DPH\>

\<Sazba\>21.00\</Sazba\>

\</DPH\>

\<Mnozstvi\>1\</Mnozstvi\>

\<Nazev\>Zásilkovna\</Nazev\>

\<Poznamka/\>

\<Katalog\>ZACZ\</Katalog\> \<!-- Číselník MS4, většinou kod zadaný v konfiguraci doprav a plateb eshopu, dle něj se pak dohledává ve view s dopravami a platbami interní ID v MS4 pro potřeby ID doprav v hlavičce objednávky--\>

\<Jednotka\>ks\</Jednotka\>

\<TypCeny\>1\</TypCeny\>

\<ObsahPolozky ID="12FB25DA-AD55-4DE5-8C9D-BF4536CAEBB5"\>

\<Mnozstvi\>1\</Mnozstvi\> \<!-- Zde TypObsahu Enum.... chybí, jelikož se jedná o neskladovou položku. Takto zapisujeme dopravu, platbu, uplatnění kreditů, vše co chceme mít textem, vždy si vyjasníme. --\>

\</ObsahPolozky\>

\</PolozkaObjednavkyPrijate\>

\<PolozkaObjednavkyPrijate ID="971A845A-7450-4B92-AABE-D40359E6303F"\>

\<JednCena\>0\</JednCena\>

\<JednCenaCM\>0\</JednCenaCM\>

\<DPH\>

\<Sazba\>21.00\</Sazba\>

\</DPH\>

\<Mnozstvi\>1\</Mnozstvi\>

\<Nazev\>Okamžitý online převod\</Nazev\>

\<Poznamka/\>

\<Katalog\>OOP\</Katalog\> \<!-- Číselník MS4, většinou kod zadaný v konfiguraci doprav a plateb eshopu, dle něj se pak dohledává ve view s dopravami a platbami interní ID v MS4 pro potřeby ID doprav v hlavičce objednávky--\>

\<Jednotka\>ks\</Jednotka\>

\<TypCeny\>1\</TypCeny\>

\<ObsahPolozky ID="F11C09F5-9B42-41E0-9F5A-B0C2F0E9A2FC"\>

\<Mnozstvi\>1\</Mnozstvi\>

\</ObsahPolozky\>

\</PolozkaObjednavkyPrijate\>

\</Polozky\>

\</ObjednavkaPrijata\>

\</ObjednavkaPrijataList\>

\</S5Data\>
