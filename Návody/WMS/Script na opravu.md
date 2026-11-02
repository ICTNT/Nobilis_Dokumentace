---
vytvořeno: 2025-06-24T13:35
oddíl: "Oprava skupin nad lokacemi"
zdroj: "OneNote / Návody/WMS / Oprava skupin nad lokacemi"
tags:
  - onenote-import
  - k-revizi
---
-- vrati lokace, ktere maji jinou referencio na skupinu zbozi nez je pripadna skupina z kmenove karty

SELECT \*

FROM d_bins t1

JOIN c_productgroups t2 ON t1.id_productgroups=t2.id

LEFT JOIN d_products t3 ON t1.id_products=t3.id

WHERE t1.id_products\>0

AND t1.id_productgroups \<\> t3.id_productgroups

AND t3.id_productgroups\<\>0

-- narovanani relace z lokace na skupinu zbozi dle aktualni skupiny zbozi z kmenove karty

begin tran

UPDATE d_bins SET id_productgroups=(SELECT id_productgroups FROM d_products WHERE id=d_bins.id_products)

WHERE id_products\>0

rollback tran
