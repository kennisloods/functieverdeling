# functieverdeling
De Functieverdeling geeft per gebied aan wat de verdeling van het functioneel grondgebruik op maaiveld is.

Zie [metadatacalogus](https://datarotterdam.dataplatform.nl/dataset/standaardgrids) voor meer informatie.

## toelichting

De functieverdeling geeft aan wat de verhouding is tussen verschillende gebruiksfuncties in een gebied. De volgende 10 functies zijn gehanteerd:

* Groen
* Bebouwing           
* Infrastructuur: Vliegverkeer
* Infrastructuur: OV
* Infrastructuur: Auto
* Infrastructuur: Parkeervak
* Infrastructuur: Voetgangers
* Infrastructuur: Fiets
* Infrastructuur :Overig
* Water

Deze classificatie is voor stedelijk gebruik geschikt. Het CBS hanteert bijvoorbeeld in het Bestand Bodemgebruik (BBG) een andere classificatie, met de volgende hoofdklassen (link):

* Verkeersterrein
* Bebouwd terrein
* Semi-bebouwd terrein
* Recreatieterrein
* Bos en open natuurlijk terrein
* Binnenwater
* Buitenwater

De functieverdeling zoals door SO gehanteerd geeft per gebied aan welk percentage door welke functie bedekt is. Daarbij is gekeken naar de functie en niet naar het fysiek voorkomen va het object. Een groene middenberm, of een groene oever telt bijvoorbeeld niet als 'groen', maar als 'Infrastructuur: weg', resp. 'Water'.

Let op dat het, door afrondingsverschillen, niet per definitie altijd optelt tot 100%.

Alleen de vlakvormige, vlakopdelende objecten op maaiveld (relatieveHoogteligging =  0) zijn beschouwd. Groene daken tellen bijvoorbeeld niet mee in het aandeel groen.  

### classificatie op basis van de BGT

De functieverdeling is als volgt gebaseerd op de Basisregistratie Grootschalige Topografie (BGT):

<table>
  <thead>
    <tr>
      <th>classificatie</th>
      <th>BGT-ojectklasse</th>
      <th>BGT-functie</th>
	  <th>opmerking</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><b>Groen</b></td><td>Begroeid terreindeel</td><td>&nbsp;</td><td>&nbsp;</td></tr>
	<tr><td rowspan=6><b>Bebouwing</b></td><td>Gebouwinstallatie</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                                       <tr><td>Pand</td><td>&nbsp;</td><td>&nbsp;</td></tr>  	 
                                       <tr><td>Overig bouwwerk</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                                       <tr><td>Scheiding</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                                       <tr><td>Onbegroeid terreindeel</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                                       <tr><td>Kunstwerkdeel</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                                       <tr><td><b>Infrastructuur: Vliegverkeer</b></td><td>Wegdeel</b></td><td>'Baan voor vliegverkeer'</td><td>&nbsp;</td></tr>
    <tr><td rowspan=2><b>Infrastructuur: OV</b></td rowspan=2><td>Wegdeel</td><td>IN ('OV-baan', 'Spoorbaan')</td><td>&nbsp;</td></tr>
                                                                          <tr><td>'Overweg'</td><td>Telt voor 50% als Auto en voor 50% als OV.</td></tr>
    <tr><td rowspan=4><b>Infrastructuur: Auto</b></td><td rowspan=3>Wegdeel</td><td>IN ('Inrit','Rijbaan autosnelweg','Rijbaan autoweg','Rijbaan regionale weg',','Rijbaan lokale weg')</td><td>&nbsp;</td></tr>
                                                                            <tr><td>'Overweg'</td><td>Telt voor 50% als Auto en voor 50% als OV.</td></tr>
                                                                            <tr><td>'Woonerf'</td><td>Telt voor 50% als Voetgangers en voor 50% als Auto.</td></tr>
                                                  <tr><td>Ondersteunend wegdeel</td><td>&nbsp;</td><td>&nbsp;</td></tr>
    <tr><td><b>Infrastructuur: Parkeervak</b></td><td>Wegdeel</td><td>'Parkeervlak'</td><td>&nbsp;</td></tr>
    <tr><td rowspan=2><b>Infrastructuur: Voetgangers</b></td><td rowspan=2>Wegdeel</td><td>IN ('Voetpad op trap', 'Voetgangersgebied', 'Voetpad')</td><td>&nbsp;</td></tr>
  	                                                                              <tr><td>'Woonerf'</td><td>Telt voor 50% als Voetgangers en voor 50% als Auto.</td></tr>
    <tr><td><b>Infrastructuur: Fiets</b></td><td>Wegdeel</td><td>'Fietspad'</td><td>&nbsp;</td></tr>
    <tr><td rowspan=2><b>Infrastructuur :Overig</b></td><td>Wegdeel</td><td>IN ('Ruiterpad','transitie')</td><td>&nbsp;</td></tr>
                                                    <tr><td>Overbruggingsdeel</td><td>&nbsp;</td><td>Dit betreffen vooral (opdelende) pilaren.</td></tr>
    <tr><td rowspan=2><b>Water</b></td><td>Waterdeel</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                                   <tr><td>Ondersteunend waterdeel</td><td>&nbsp;</td><td>Incl. oever, slootkant en slik.</td></tr>
  </tbody>
</table> 

Een spoorbaan, ondersteunend wegdeel, en ondersteunend waterdeel kan ook groen zijn, maar heeft de functie spoorbaan, wegdeel resp, waterdeel. Deze klassen worden daarom niet als groen(functie) aangemerkt.
Woonerf en Overweg hebben een dubbele functie. Een overweg heeft bijvoorbeeld tegelijkertijd de functie spoor als de functie weg. Het oppervlakte telt daarom voor 50% mee in beide functies.

De klassen 'Ongeclassificeerd object', 'Vegetatieobject', en 'Weginrichtingselement' zijn inrichtend en dus niet vlakopdelend. Deze klassen tellen daarom niet mee.

## bronnen

* (lokale) BGT
* CBS: Kerncijfers wijken en Buurten 2017 [link](http://www.nationaalgeoregister.nl/geonetwork/srv/dut/catalog.search#/metadata/dcb7f0d7-d70b-4eab-9a46-7af98de860bd?tab=contact)

## bewerking

De functieverdelingen worden berekend per CBS-gemeente, CBS-wijk, en CBS-buurt.

1.  Filteren en classificeren van de relevante objectklassen uit de BGT;
2.  Per CBS-buurt:
    1.  bepalen oppervlakte van het gebied;
    2.  bepalen van de intersectie van de naar functies geclassificeerde BGYT-objecten
    3.  bepalen van de oppervlaktes van de intersecties;
    4.  sommeren van de oppervlaktes per CBS-buurt en functie;
    5.  aggregeren en sommeren van de oppervlaktes van de functies en de buurt per CBS-wijk;
    6.  aggregeren en sommeren van de oppervlaktes van de functies en de buurt per CBS-gemeente;
3.  per gebied (CBS-gemeente, CBS-wijk, CBS-buurt):
    1. Per functie per gebied de verdelingspercentage berekenenen als `(oppervlakte(functie) / oppervlakte(gebied) * 100%`.

## entiteiten en kenmerken
### entiteiten

| entiteit | betekenis |
| -------- | --------- |
| `Functieverdeling_per_CBS_gemeente` | Functieverdeling berekend per CBS-gemeente. |
| `Functieverdeling_per_CBS_wijk` 	  | Functieverdeling berekend per CBS-wijk.     | 
| `Functieverdeling_per_CBS_buurt` 	  | Functieverdeling berekend per CBS-buurt.    |

### generieke kenmerken

Alle entiteiten kennen de volgende kenmerken:

| kenmerk | type | voorbeeld | betekenis |
| ------- | ---- | --------- | --------- | 
| **`UUID`**                      | `char(36)` | `"6d64c4c3-5955-4da5-aaae-fb3aa5886834"` | Unieke, betekenisloze identificatie. |
| **`peildatum`**                 | `smallint` | `2017`   | De datum waarop het gegeven actueel was. |
| **`ind_actueel`**               | `boolean`  | `1`      | Indicatie of dit gegeven voor het gebied de meest actueel bekende waarde is.
| **`opp_gebied_ha`**             | `float`    | `104.18` | Totale oppervlakte van het gebied in hectare. |
| **`opp_bebouwing_ha`**          | `float`    | `17.13`  | Oppervlakte van de functie Bebouwing in het gebied in hectare. |
| **`opp_groen_ha`**              | `float`    | `26.25`  | Oppervlakte van de functie Groen in het gebied in hectare. |
| **`opp_infra_auto_ha`**         | `float`    | `9.48`   | Oppervlakte van de functie Infrastructuur: Auto in het gebied in hectare. |
| **`opp_infra_fiets_ha`**        | `float`    | `1.53`   | Oppervlakte van de functie Infrastructuur: Fiets in het gebied in hectare. |
| **`opp_infra_ov_ha`**           | `float`    | `0`      | Oppervlakte van de functie Infrastructuur: OV in het gebied in hectare. |
| **`opp_infra_parkeervlak_ha`**  | `float`    | `1.86`   | Oppervlakte van de functie Infrastructuur: Parkeervlak in het gebied in hectare. |
| **`opp_infra_vliegverkeer_ha`** | `float`    | `0`      | Oppervlakte van de functie Infrastructuur: Vliegverkeer in het gebied in hectare. |
| **`opp_infra_voetgangers_ha`**  | `float`    | `11.53`  | Oppervlakte van de functie Infrastructuur: Voetgangers in het gebied in hectare. |
| **`opp_infra_overig_ha`**       | `float`    | `0.02`   | Oppervlakte van de functie Infrastructuur: Overig in het gebied in hectare. |
| **`opp_water_ha`**              | `float`    | `36.38`  | Oppervlakte van de functie Water in het gebied in hectare. |
| **`perc_bebouwing`**            | `float`    | `16.4`   | Percentage van de functie Bebouwing in het gebied. |
| **`perc_groen`**                | `float`    | `25.2`   | Percentage van de functie Groen in het gebied. |
| **`perc_infra_auto`**           | `float`    | `9.1`    | Percentage van de functie Infrastructuur: Auto in het gebied. |
| **`perc_infra_fiets`**          | `float`    | `1.5`    | Percentage van de functie Infrastructuur: Fiets in het gebied. |
| **`perc_infra_ov`**             | `float`    | `0`      | Percentage van de functie Infrastructuur: OV in het gebied. |
| **`perc_infra_parkeervlak`**    | `float`    | `1.8`    | Percentage van de functie Infrastructuur: Parkeervlak in het gebied. |
| **`perc_infra_vliegverkeer`**   | `float`    | `0`      | Percentage van de functie Infrastructuur: Vliegverkeer in het gebied. |
| **`perc_infra_voetgangers`**    | `float`    | `11.1`   | Percentage van de functie Infrastructuur: Voetgangers in het gebied. |
| **`perc_infra_overig`**         | `float`    | `0`      | Percentage van de functie Infrastructuur: Overig in het gebied. |
| **`perc_water`**                | `float`    | `34.9`  | Percentage van de functie Water in het gebied. |

### specifieke kenmerken per entiteit

Voor de specifieke entiteiten gelden de volgende kenmerken:

#### Functieverdeling_per_CBS_gemeente

| kenmerk | type | voorbeeld | betekenis |
| ------- | ---- | --------- | --------- | 
| **`CBS_gemeentecode`** | `char(6)`   | `"GM0599"`    | De gemeentecode zoals door CBS gehanteerd. |
| **`CBS_gemeentenaam`** | `char(255)` | `"Rotterdam"` | De gemeentenaam zoals door CBS gehanteerd. |

#### Functieverdeling_per_CBS_wijk

| kenmerk | type | voorbeeld | betekenis |
| ------- | ---- | --------- | --------- | 
| **`CBS_gemeentecode`** | `char(6)`   | `"GM0599"`                      | De gemeentecode zoals door CBS gehanteerd. |
| **`CBS_gemeentenaam`** | `char(255)` | `"Rotterdam"`                   | De gemeentenaam zoals door CBS gehanteerd. |
| **`CBS_wijkcode`**     | `char(8)`   | `"WK059923"`                    | De wijkcode zoals door CBS gehanteerd. |
| **`CBS_wijknaam`**     | `char(255)` | `"Botlek-Europoort-Maasvlakte"` | De wijknaam zoals door CBS gehanteerd. |

#### Functieverdeling_per_CBS_buurt

| kenmerk | type | voorbeeld | betekenis |
| ------- | ---- | --------- | --------- | 
| **`CBS_gemeentecode`** | `char(6)`   | `"GM0599"`     | De gemeentecode zoals door CBS gehanteerd. |
| **`CBS_gemeentenaam`** | `char(255)` | `"Rotterdam"`  | De gemeentenaam zoals door CBS gehanteerd. |
| **`CBS_wijkcode`**     | `char(8)`   | `"WK059923"`   | De wijkcode zoals door CBS gehanteerd. |
| **`CBS_buurtcode`**    | `char(10)`  | `"BU05992306"` | De buurtcode zoals door CBS gehanteerd. |
| **`CBS_buurtnaam`**    | `char(255)` | `"Botlek"`     | De buurtnaam zoals door CBS gehanteerd. |
