# Power BI Tricks
## Sisällysluettelo
- [Dynaaminen PBI matriisin rivien ja sarakkeiden suodatus](#dynaaminen-pbi-matriisin-rivien-ja-sarakkeiden-suodatus)
- [User Defined Functions, käyttäjän määrittelemät funktiot](#user-defined-functions-käyttäjän-määrittelemät-funktiot)
  - [Toinen esimerkki UDF:n käytöstä](#Toinen-esimerkki-udfn-käytöstä)
  - [Käyttäjän valinta UDF-parametrina](#käyttäjän-valinta-udf-parametrina)
 
 
### Dynaaminen PBI matriisin rivien ja sarakkeiden suodatus
Esimerkki lopputuloksesta miten PBI matriisin rivejä ja sarakkeita voi raportin käyttäjän toimesta suodattaa dynaamisesti.

Esimerkissä oleva data on peräisin Microsoftin Contoso demodataa.

![GIF, joka näyttää miten raportin slicer muuttaa näkymää](Demotiedosto.gif)

<br>

### User Defined Functions, käyttäjän määrittelemät funktiot
Esimerkkinä numeron muotoilu. Perinteinen tapa vaatii muotoilumerkkijonon tai DAX-koodia jokaiseen mittariin, johon muotoilu halutaan kohdistaa. Käyttäjän määrittelemällä funktiolla toki vaatii saman toimenpiteen, mutta koodia ei tarvitse kirjoittaa toisteisesti ja ylläpito helpottuu. Muutokset voidaan tehdä pelkästään funktioon.

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

