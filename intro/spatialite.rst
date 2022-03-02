.. index::
   single: Spatialite

Souborové databáze - SQLite
===========================

Již před příchodem SQLite existovaly souborové databáze. Jako příklad
můžeme uvést kdysi velmi oblíbený MS Access (JET). Výhoda souborového řešení
je zejména v tom, že můžeme kdykoli snadno komukoli naši databázi předat.
On si ji pak může snadno načíst, protože databázový systém SQLite je podporovaný
širokou škálou programátorských knihoven. SQLite se využívá jako pomocná
databáze jak v deskopových prostředích, tak v mobilních zařízeních.

V databázi je pak možné se dotazovat pomocí jazyka SQL (Structured Query Language)
nebo jiného jazyka.

.. figure:: images/sqlite-gui.png
   :class: middle

   Prohlížeč DB Browser pro SQLite.

Spatialite
----------

`Spatialite <https://www.gaia-gis.it/fossil/libspatialite/index>`_ je prostorové
rozšíření databáze
`SQLite <https://sqlite.org>`_. Přidává prostorové datové typy a základní prostorové dotazy a
operace dle standardu OGC Simple Features Access.

.. tip:: Více o standardu Simple Features Access ve školení :skoleni:`PostGIS
         <postgis-zacatecnik/kapitoly/1_uvod.html>`.


K efektivním prostorovým dotazům slouží
prostorové indexy v databázi.  Samotné dotazy pak realizuje knihovna (ovladač),
kterým se aplikace k databázi připojuje.

.. figure:: images/spatialite-gui.png
   :class: middle

   Prohlížeč spatialite-gui.
