# Úložiště tripletů

* dalo by se to udělat v relační databázi jako jedna tabulka se třema sloupcama, ale na to nejsou ty databáze optimalizované

## Triple Store

* ta tabulka (SPO) se třemi sloupci **v relační databázi** (Subjekt, Predikát, Objekt)
* hodí se tím víc, čím víc máme predikátů (+)
* self-joiny v dotazu (-)

## ID Triple Store

Taky relační databáze

* číselníková tabulka (sloupce URI  a ID) a SPO tabulka už jenom s IDčkama
* výhoda v tom, že ta SPO tabuka má jeden datový typ, jinak stejně špatné

## Multigraf ID Triple Store

To samé jako ID Triple Store, ale v SPO tabulce je ještě sloupec **G** (identifikace grafu)

## Property tables

Agreguje predikáty pro podobné subjekty do jedné tabulky (Podobné jako klasická relační databáze, entity jsou ve stejných tabulkách). Už to má stejné neduhy jako relační databáze (např. řídkost).

## Verticaly partitioned tables

Pro každý predikát se udělá tabulka s dvěma sloupečky (subjekt, objekt).

## Hexastores

Vytvoří se indexy pro všechny možné permutace S,O a P

++ rychlé joins

-- 5x více dat

# RDF Repositories

