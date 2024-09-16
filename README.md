# Project Skeleton
Ez a projekt arról szól, hogy egy ún. "cégmotort" állítok össze open source toolok segítségével.

## Felhasznált appok
Ehhez a következő appokat használom fel:
- Joget Workflow
	- egy drag-and-drop "process engine", BPMN compliant, Peti vágja, használta már stb.
	- a JBPM-et hivatott leváltani, egyszerűbb a kezelő felülete
- OpenProject
	- egy open source Trello, több funkcióval, profi téma
- Corteza
	- ilyenünk nincs is, lényegében, amikor emailben vagy Google spreadsheetben adatokat tárolunk gány módon, na ez annak a felhasználóbarátabb verziója (is)
	- tudsz custom appokat létrehozni arra, hogy adatoka tárolj, módosíts, lekérj, összekapcsolj, stb.
	- van egy beépített CRM téma benne, de tudnánk a minta-tárolásokra is használni, stb.
- BookStack
	- egy tudástároló open source eszköz, lényegében egy kicsit friendly-bb verziója, de nem olyan profi, mint az Obsidian
- Apache NiFi
	- egy data-flow framework, ami lehetővé teszi a különféle applikációk automatizált adat-összekötést
	- ez kivenné az embereket, mint glue-code-ot a feladatokból
	- drag-and-drop megoldásokat alkalmaz
	- Apache Camel (Karavan)-t hivatott leváltani

## Korábban használni tervezett appok
- JBPM
	- egy masszívan mature, komplex "process engine", fullon BPMN 2.0 compliant, stb.
	- a Joget Workflow-t könnyebb használni, és Peti ismeri, és használta, szóval inkább azt használjuk
		- a Joget az csak BPMN, ez pedig BPMN 2.0 compliant; mindenesetre, nekünk a célnak ez is megfelel
- Apache Camel (Karavan)
	- egy integration framework, és bár komplexebb integrációkra képes, nekünk egyelőre az Apache NiFi megfelel a célnak

## Hiányos területek
- ticketing szoftver

## Tesztelnivaló appok
- Apache Airflow
	- workflow automatizáló rendszer, Python alapú, lehet, hogy meglenne a haszna valahol
- osTicket
	- ticketing szoftver
- Zammad
	- ticketing szoftver, ígéretesebb, mint az osTicket
- Mautic
	- marketing automatizáló szoftver, valamire használható


## "Cégmotor"
Miután a standardok leírásának módjánál rátaláltam a "process engine" azaz "folyamat motor" szavakra, eszembe nem jutott, hogy ilyen létezhet, és mégis.

Most a cég nyersen dolgozik, hasonlóan az "imperative programming"-hoz.
A cégnek szüksége lesz egy ERP-re, ami az OOP-ra hasonlít.
A kettő között van a "functional programming", és ez a "cégmotor", bár még mindig nem ERP, mégis egy integrált workflow követő akármi, ami könnyebb és következetesebb munkavégzést hoz létre.

## Port beosztás, alkalmazásonként
### Élő appok
|App			|Port	 |Login																																														|URL																						 |
|---			|---	 |---																																														|---																						 |
|BookStack		|8000	 |username: `admin@admin.com`<br> pass: `password`																																			|[http://localhost:8000/](http://localhost:8000/)											 |
|Corteza		|8100	 |neked kell megadni, az első regisztrált felhasználó automatikusan admin lesz																												|[http://localhost:8100/](http://localhost:8100/)											 |
|OpenProject	|8400	 |username: `admin`<br> pass: `admin`																																						|[http://localhost:8400/](http://localhost:8400/)											 |
|Apache NiFi	|8443[^1]|a username és pass a `docker logs nifi`-ban lesz, valahogy így:<br>`Generated Username [8e1989c8-7afc-403b-8e74-751cbfe58355]`<br>`Generated Password [zNmwmi4PkB8nEIPgYTRk79wU1SR1Lpyy]`	|[https://localhost:8443/nifi/](https://localhost:8443/nifi/)								 |
|Joget Worfklow	|8500	 |username: `admin`<br> pass: `admin`																																						|[http://localhost:8500/](http://localhost:8500/)											 |
|Zammad			|8600	 | ilyen nincs																																												|[http://localhost:8600/](http://localhost:8600)											 |
|NocoDB			|8700	 | ilyen nincs																																												|[http://localhost:8700/](http://localhost:8700)											 |
|Rocket.chat	|3000	 | ilyen nincs																																												|[http://localhost:3000/](http://localhost:3000)											 |

### Leváltott appok

|App			|Port	 |Login																																														|URL																						 |
|---			|---	 |---																																														|---																						 |
|JBMP			|8200	 |username: `wbadmin`<br> pass: `wbadmin`																																					|[http://localhost:8200/business-central](http://localhost:8200/business-central)			 |
|Karavan		|8300	 |nincs login																																												|[http://localhost:8300/](http://localhost:8300/)											 |


[^1]: A NiFi belső, konténeren belüli beállításainak köszönhetően csak a `HTTPS` protokollt, és a `8443`-as portot fogadja el.