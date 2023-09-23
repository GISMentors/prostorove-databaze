.. index::
   single: MBTiles

MBTiles
-------

Jiným příkladem uložení prostorových dat je struktura
`MapBox Tiles <https://github.com/mapbox/mbtiles-spec>`_, která umožňuje uložení
dlaždic dat, a to jak v rastrové nebo i vektorové formě.

Struktura
=========

Struktura databáze je jednoduchá. Jedná se o dvě tabulky a jeden index. V praxi
se využívají spíše pohledy na datovou tabulku. Důležitá je tabulka `metadata`.
GeoPackage a MBTiles jsou do vysoké míry zaměnitelné formáty (GeoPackage je
univerzálnější a metadatově bohatší).

Do MBTiles lze uložit pouze dlaždicovaná data (rastrová či vektorová ve formátu
PBF), v souřadnicovém systému WebMercator (EPSG:3857).

.. figure:: images/mbtiles.png
   :class: middle

   Struktura MBTiles
