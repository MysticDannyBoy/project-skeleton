# Project Skeleton
Ez a projekt arról szól, hogy egy ún. "cégmotort" állítok össze open source toolok segítségével.

## Felhasznált appok
Ehhez a következő appokat használom fel:
- JBPM
	- egy masszívan mature, komplex "process engine", fullon BPMN 2.0 compliant, stb.
- OpenProject
	- egy open source Trello, több funkcióval, profi téma
- Corteza
	- ilyenünk nincs is, lényegében, amikor emailben vagy Google spreadsheetben adatokat tárolunk gány módon, na ez annak a felhasználóbarátabb verziója (is)
	- tudsz custom appokat létrehozni arra, hogy adatoka tárolj, módosíts, lekérj, összekapcsolj, stb.
	- van egy beépített CRM téma benne, de tudnánk a minta-tárolásokra is használni, stb.
- BookStack
	- egy tudástároló open source eszköz, lényegében egy kicsit friendly-bb verziója, de nem olyan profi, mint az Obsidian
- Apache Camel (Karavan)
	- egy integrációs framework, ami lehetővé teszi a különféle applikációk automatizált összekötését
	- ez kivenné az embereket, mint glue-code-ot a feladatokból

## "Cégmotor"
Miután a standardok leírásának módjánál rátaláltam a "process engine" azaz "folyamat motor" szavakra, eszembe nem jutott, hogy ilyen létezhet, és mégis.

Most a cég nyersen dolgozik, hasonlóan az "imperative programming"-hoz.
A cégnek szüksége lesz egy ERP-re, ami az OOP-ra hasonlít.
A kettő között van a "functional programming", és ez a "cégmotor", bár még mindig nem ERP, mégis egy integrált workflow követő akármi, ami könnyebb és következetesebb munkavégzést hoz létre.

## Port beosztás, alkalmazásonként
|App		|Port	|Login																				|URL																			 |
|---		|---	|---																				|---																			 |
|BookStack	|8000	|username: `admin@admin.com`<br> pass: `password`									|[http://localhost:8000/](http://localhost:8000/)|
|Corteza	|8100	|neked kell megadni, az első regisztrált felhasználó automatikusan admin lesz		|[http://localhost:8100/](http://localhost:8100/)|
|JBMP		|8200	|username: `wbadmin`<br> pass: `wbadmin`											|[http://localhost:8200/business-central](http://localhost:8200/business-central)|
|Karavan	|8300	|nincs login																		|[http://localhost:8300/](http://localhost:8300/)|
|OpenProject|8400	|username: `admin`<br> pass: `admin`												|[http://localhost:8400/](http://localhost:8400/)|