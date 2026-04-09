# Power BI Tricks
## Sisällysluettelo
- [Dynaaminen Power BI matriisin rivien ja sarakkeiden suodatus](#dynaaminen-power-bi-matriisin-rivien-ja-sarakkeiden-suodatus)
- [User Defined Functions - Käyttäjän määrittelemät funktiot](#user-defined-functions---käyttäjän-määrittelemät-funktiot)
  - [Toinen esimerkki UDF:n käytöstä](#toinen-esimerkki-udfn-käytöstä)
  - [Käyttäjän valinta UDF-parametrina](#käyttäjän-valinta-udf-parametrina)
- [Calculation Groups - Laskentaryhmät ](#calculation-groups---laskentaryhmät)
- [Uutta Power BI:ssä (tammikuu 2026) - Porautuminen suoraan työkaluvihjeestä](#uutta-power-bissä-tammikuu-2026---porautuminen-suoraan-työkaluvihjeestä)
- [Taulukko ja väripalkki selitteenä](#taulukko-ja-väripalkki-selitteenä)
- [Python-visualisointi](#python-visualisointi)
- [Uutta Power BI:ssä (helmikuu 2026) - Korttivisuaalin kategoriat ja suodatustoiminnallisuus](#uutta-power-bissä-helmikuu-2026---korttivisuaalin-kategoriat-ja-suodatustoiminnallisuus)
- [Power BI -raportin esimerkkisivu](#power-bi--raportin-esimerkkisivu)
- [Uutta Power BI:ssä (maaliskuu 2026)](#uutta-power-bissä-maaliskuu-2026)
  - [Viivakaavion selitteet ja johtoviivat](#viivakaavion-selitteet-ja-johtoviivat)
  - [Visualisointien moderni ulkoasu](#visualisointien-moderni-ulkoasu)
- [Power BI Modelling MCP Server](#power-bi-modelling-mcp-server)
- [Dynaaminen ranking RANKX-funktiolla](#dynaaminen-ranking-rankx-funktiolla)
 
--- 
### Dynaaminen Power BI matriisin rivien ja sarakkeiden suodatus
Lopputulos Power BI matriisin rivien ja sarakkeiden dynaamisesta suodatuksesta.

Esimerkissä oleva data on Microsoftin Contoso demodataa.
<br>

![GIF, joka näyttää miten raportin slicer muuttaa näkymää](Demotiedosto.gif)

<br>

---
### User Defined Functions - Käyttäjän määrittelemät funktiot
Esimerkkinä numeron muotoilu. Perinteinen tapa vaatii muotoilumerkkijonon tai DAX-koodia jokaiseen mittariin, johon muotoilu halutaan kohdistaa. Käyttäjän määrittelemällä funktiolla toki vaatii saman toimenpiteen, mutta koodia ei tarvitse kirjoittaa toisteisesti ja ylläpito helpottuu. Mahdolliset muutokset täytyy tehdä funktiota käytettäessä vain yhteen paikkaan.

Muotoile-kohtaan asetetaan esim. seuraava DAX-koodi.

![Measure Format](Format1.png)


UDF:n kohdalla vastaava koodi olisi seuraava, mutta muotoile-kohtaan asetetaan ainoastaan funktion nimi.

![Measure Format with UDF](Format2.png)

Käytetyn UDF-funktion koodi.

![UDF-esimerkkikoodi](Function.png)

M Sales Quantity -sarake tehty perinteisellä tavalla ja M Revenue UDF:n avulla - laskennan lopputulos on tietenkin identtinen.

![Numeron muotoilu - M Sales Quantity perinteisellä tavalla ja M Revenue UDF:n avulla](UDF.png)

<br>

#### Toinen esimerkki UDF:n käytöstä

Mittarit luotu perinteisellä tavalla.

<img src="Mittarit%20p1.png" width="20%"> <img src="Mittarit%20p2.png" width="20%"> <img src="Mittarit%20p3.png" width="20%">


Vs. ratkaisu, jossa mittarit käyttävät funktiota.

![Mittarit käyttävät funktiota](Mittarit%20funktiolla.png)

<br>

Laskennan lopputulokset ovat (tietenkin) identtisiä.

![Visualitointi - laskennan lopputuloksessa ei ole eroa](Visu.png)


#### Käyttäjän valinta UDF-parametrina

Mittari voidaan tehdä myös ottamaan käyttäjän valinta, joka toimii dynaamisena parametrina funktiolle. Huom, tässä käytetään samaa funktiota, joka on esitelty edellisessä kohdassa.

![](Mittari%20UDF%20ja%20dynaaminen%20parametri.png)

Esimerkki, miten laskenta tapahtuu dynaamisesti.

![](UDF%20Dynamic%20Parameter.gif)

---
### Calculation Groups - Laskentaryhmät

Laskentaryhmillä saadaan mukavasti rajoitettua mittarien määrää, jolloin ylläpidosta tulee helpompaa ja datapaneeli pysyy kuosissa. Alla tästä esimerkki.

Perusmittari

![Esimerkki perusmittarista](CG%20Measure.png)

Laskentaryhmään tehty neljä eri aikalaskentaa.

![Laskentaryhmä](CG%20Model.png)

Yksittäisen laskentakohteen koodi.

![Yksittäisen laskentakohteen koodi](CG%20Code.png)

Esimerkki lopputuloksesta visualisoinnin muodossa.

![Visualitointi 1](CG1.png)

![Visualitointi 2](CG2.png)

---
### Uutta Power BI:ssä (tammikuu 2026) - Porautuminen suoraan työkaluvihjeestä
Huom! Lievä hitaus porautumisessa johtuu todennäköisesti mallitiedoston tietomallista ja siinä olevista lukuisista kaksisuuntaisista suhteista.

Uuden toiminnallisuuden myötä raportin käyttäjä pääsee porautumaan hieman helpommin tarkemmalle tasolle tietoon.
![](DrillThrough%20from%20Tooltip.gif)

---
### Taulukko ja väripalkki selitteenä
Kumpi on selkeämpi? Toiseen lisätty väripalkki selitteeksi ilmaisemaan värisävyn merkitystä.

![](Table%20visualization%20with%20color%20bar%20as%20a%20legend.png)

---
### Python-visualisointi
Pythonilla voi luoda visualisointeja Power BI -raporteille. Alla esimerkki laatikko- ja janakaaviosta (Boxplot). Ensin pätkä koodista ja sitten itse visualisointi.

![](Py-koodi.png)

![](Py-visu.png)

---
###  Uutta Power BI:ssä (helmikuu 2026) - Korttivisuaalin kategoriat ja suodatustoiminnallisuus
Kategoriat toimivat korttivisuaaleissa suodattimina:

![](Kategoriat%20suodattimena.gif)

---
### Power BI -raportin esimerkkisivu
Raportissa on toistaiseksi hiukan hitautta. Taustalla on dataa > 50 M riviä. Korjaus rakentamalla mitaliarkkitehtuuriin kultatasolle aggregointitaulu.

![](Junat-raportti.gif)

---

### Uutta Power BI:ssä (maaliskuu 2026)
#### Viivakaavion selitteet ja johtoviivat
Kun selitteet asetetaan viivojen jatkeeksi, kaavio pysyy selkeänä myös tiheällä viivamäärällä. Johtoviivat taas yhdistävät itse viivan sarjan nimeen.

![](Viivakaavio%20ja%20selitteet.png)

#### Visualisointien moderni ulkoasu
Tässä uusi esiversioasetus on laitettu asetuksista päälle ja otettu käyttöön kuvan raporttisivussa.

Ennen:
![](Teema%201.png)

Jälkeen:
![](Teema%202.png)


---

### Power BI Modelling MCP Server
Testasin tätä. Mittareiden kuvausten asettaminen yhdellä kerralla onnistui hienosti, kuten esim. taulujen ja niiden välisten suhteiden listaus. 
Mihin tämä soveltuu? Microsoftin dokumentaation mukaan avainominaisuudet ovat:
-   Natural language model editing - Create, update, and manage tables, columns, measures, and relationships across Power BI Desktop and Fabric semantic models using conversational commands
- Bulk operations at scale - Execute batch operations on hundreds of objects simultaneously with transaction support and error handling
- Best practice application - Evaluate and implement modeling best practices easily
- Agentic development workflows - Work with TMDL and Power BI Project files, enabling AI agents to autonomously plan and execute complex modeling tasks
- DAX query validation - Execute and validate DAX queries to test measures, troubleshoot calculations, and explore data

![](Power%20BI%20Modelling%20MCP%20Server.gif)

![](Power%20BI%20Modelling%20MCP%20Server%202.gif)

---

### Dynaaminen ranking RANKX-funktiolla

![](Dynamic%20Ranking%20with%20RANKX.gif)
