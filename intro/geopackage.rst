.. index::
   single: GeoPackage

GeoPackage
----------

`OGC GeoPackage <https://geopackage.org>`__ je otevřený standard
:wikipedia:`OGC`. Jedná se o formát založený na SQLite. V nejčastěji používané
variantě využívá ale i knihovny pro SpatiaLite. Oproti SpatiaLite
přidává další struktury, a to zejména metadata a také možnosti uložení
rastrových dat.

V prostředí nástroje QGIS se můžete na GeoPackage dívat
ze dvou pohledů.

GeoPackage v QGIS - přístup 1
=============================

První z nich přístupuje ke GeoPackage jako k běžnému zdroji dat. Data
načteteme např. v prohlížečí, jak ukazuje obrázek níže.

.. figure:: images/geopackage.png
   :class: large
           
   Načtení GeoPackage v QGIS

Na obrázku vidíme v prohlížeči soubor ve formátu GeoPackage s obsahem
dat z RÚIAN.

GeoPackage v QGIS - přístup 2
=============================

Druhý pohled na formát GeoPackage umožňuje správce databází. Zde
můžete v plné síle využísqt dotazovací jazyk SQL, včetně prostorových
dotazů.

.. figure:: images/geopackage2.png
   :class: large

   Správce databází GeoPackage v QGIS
