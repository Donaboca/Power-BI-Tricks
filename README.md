# Power BI Tricks
## Sisällysluettelo
- [Dynaaminen Power BI matriisin rivien ja sarakkeiden suodatus](#dynaaminen-power-bi-matriisin-rivien-ja-sarakkeiden-suodatus)
- [User Defined Functions - Käyttäjän määrittelemät funktiot](#user-defined-functions---käyttäjän-määrittelemät-funktiot)
  - [Toinen esimerkki UDF:n käytöstä](#Toinen-esimerkki-udfn-käytöstä)
  - [Käyttäjän valinta UDF-parametrina](#käyttäjän-valinta-udf-parametrina)
- [Calculation Groups - Laskentaryhmät ](#calculation-groups---laskentaryhmät)
- [Uutta Power BI:ssä (tammikuu 2026) - Porautuminen suoraan työkaluvihjeestä](#uutta-power-bissa-tammikuu-2026---porautuminen-suoraan-tyokaluvihjeesta)
 
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
Huom! Lievä hitaus porautumisessa johtuu tietomallista ja siinä olevista lukuisista kaksisuuntaisista suhteista.
![](DrillThrough%20from%20Tooltip.gif)
