.. index::
   single: Použití prostorových dotazů v GDAL

Použití prostorových dotazů v GDAL
----------------------------------

Dotazy je možné rovněž používat v rámci knihovny GDAL,
a to v různých případech užití. Jednou skupinou je využití
GDAL bin utils, které se ovládají z příkazového řádku (terminálu).

ogrinfo
=======

Nástroj ogrinfo umožňuje zobrazit informace o zdroji dat,
pokud jej zkombinujeme s SQL dotazem můžeme si např. vypsat
plochu největší parcely v našem cvičném území.

.. code-block:: bash

   ogrinfo ruian.gpkg -sql "SELECT Max(ST_Area(ST_Buffer(geom, 5))) FROM parcely"

Po zadání daného příkazu dostaneme plochu největší parcely v území.

.. code-block:: bash

  INFO: Open of `ruian.gpkg'
        using driver `GPKG' successful.

  Layer name: SELECT
  Geometry: None
  Feature Count: 1
  Layer SRS WKT:
  (unknown)
  Max(ST_Area(ST_Buffer(geom, 5))): Real (0.0)
  OGRFeature(SELECT):0
    Max(ST_Area(ST_Buffer(geom, 5))) (Real) = 279528.457700693

ogr2ogr
=======

Nástroj ogr2ogr dokáže provádět celou řadu zajímavých operací,
přičemž primární je konverze mezi formáty a souřadnicovými systémy.
V případě doplnění o SQL je možná dále realizovat výběry dat na
základě prostorových dotazů. Můžeme si tak např. seznam parcel,
které splňují podmínku vypsat do formátu CSV, který můžeme načíst
v běžném tabulkovém procesoru.

.. code-block:: bash

   ogr2ogr -f "CSV" budovy.csv ruian.gpkg -sql "SELECT s2.Kod, round(ST_Distance(s1.geom, s2.geom)) dist
                            FROM stavebniobjekty s1 JOIN stavebniobjekty s2 ON
                            (s1.Kod = 4598652 AND
                            s2.PocetPodlazi > 2 AND
                            ST_Distance(s1.geom, s2.geom) < 500)
                            ORDER BY ST_Distance(s1.geom, s2.geom)"

Po zadání daného příkazu dostaneme soubor budovy.csv s následujícím obsahem.

.. code-block:: bash

  Kod,dist
  "4598016",11
  "4598245",98
  "27488829",112
  "4598636",178
  "26676095",261
  "4598792",269
  "4596579",285
  "4598113",290
  "54232597",304
  "27934829",331
  "4599951",337
  "25832212",341
  "4597923",352
  "25053086",360
  "25213016",374
  "4599900",483
  "4596684",491

.. tip:: Vektorové formáty, do kterých můžete realizovat export najdete na
         <https://gdal.org/drivers/vector/index.html>.

TODO - další využití
