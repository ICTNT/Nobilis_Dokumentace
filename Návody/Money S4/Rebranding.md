---
vytvořeno: 2024-06-07T11:14
oddíl: "Rebranding"
zdroj: "OneNote / Návody/Money S4 / Rebranding"
tags:
  - onenote-import
  - k-revizi
---
Postup:

1.  Vytvořit produktový klíč
2.  Oklíčovat seznam od produkt oddělení
3.  Aktualizovat VIEW Nobilis_SeznamEtiketRebranding
4.  XLS import - sklady - provedeme import konfigurace EtiketyREB (kontrola)
5.  Po importu nastavit hlavního dodavatele a stav etiket na např. Novinka (budoucí produkt)
6.  Pustit script:

with info

as

(select Katalog, MinimalniObjednavka, PovinnyNasobek, KodSklad_Objednavka_UserData

from Nobilis_SeznamEtiketRebranding)

select A.Katalog, A.Nazev, Dodavatel.ID as IDDod, Dodavatel.MinimalniObjednavka, Dodavatel.PovinnyNasobek, Dodavatel.KodSklad_Objednavka_UserData

, I.\*

from Artikly_Artikl as A

join Artikly_ArtiklProduktovyKlic as Klic on Klic.Root_ID=A.ID and Klic.ProduktovyKlic_ID='36ac61a3-28b2-4931-999d-378c5d53a12a'

join Ciselniky_DruhArtiklu as Druh on Druh.ID=A.DruhArtiklu_ID and Druh.ID='a45219b1-4032-4fc6-8710-28231d893ba4'

join Artikly_ArtiklDodavatel as Dodavatel on Dodavatel.ID=A.HlavniDodavatel_ID

join info as I on I.Katalog=A.Katalog

7.  V excelu sestavit update pro všechny etikety
8.  Nastavíme sklady - skladové zásoby - přidat hromadně
9.  Doplnit rozměry + přední strana přes script:

with Info

as

(Select Katalog, ROZ_ET_UserData, KodPredniEtikety_UserData, NavinEtikety_UserData

from Nobilis_SeznamEtiketRebranding)

select Z.ID as IDZAsoby, Etiketa.Katalog, Etiketa.Nazev, I.\*

from Sklady_Zasoba as Z

join Artikly_Artikl as Etiketa on Etiketa.ID=Z.Artikl_ID

join Artikly_ArtiklProduktovyKlic as Klic on Klic.Root_ID=Etiketa.ID and Klic.ProduktovyKlic_ID='36ac61a3-28b2-4931-999d-378c5d53a12a'

join Ciselniky_DruhArtiklu as Druh on Druh.ID=Etiketa.DruhArtiklu_ID and Druh.ID='a45219b1-4032-4fc6-8710-28231d893ba4'

join Info as I on I.Katalog=Etiketa.Katalog

where Z.Sklad_ID='839e143e-938f-42fd-ab0d-e81c1eaf0fe1'

10. V excelu sestavit update pro všechny etikety
