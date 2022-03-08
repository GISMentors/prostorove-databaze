.. index::
   single: Pohledy

Pohledy v SQL
-------------

Vytváření pohledu je užitečná funkce SQL databází. Když už se nám povede
vytvořit požadovaný :sqlcmd:`SELECT` se všemi :sqlcmd:`WHERE` podmínkami,
relacemi na další tabulky :sqlcmd:`JOIN` a aliasy :sqlcmd:`AS`, můžeme pro
budoucí využití ulžiž tento výraz to tzv. pohledu :sqlcmd:`VIEW`:

.. code-block:: sql

   CREATE VIEW pozemky AS
        SELECT p.DruhPozemkuKod, p.VymeraParcely, ku.Nazev FROM parcely AS p
        JOIN katastralniuzemi AS ku ON (p.KatastralniUzemiKod = ku.Kod);

V databázi vznikne nová virtuální "tabulka", se kterou můžeme dále pracovat. Je
to přehlednější, než opakovat pokaždé komplikovaný :sqlcmd:`SELECT`. Do pohledu
ale nemůžeme zapisovat (až na výjimky) a jsou tak rychlé, jako optimalizovaný je
:sqlcmd:`SELECT`.

Výhoda pohledu je rovněž v tom, že vždy vstupuje do originálních dat. Dotaz se
tedy vždy provádí znovu.
