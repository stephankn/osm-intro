---
marp: true
theme: gaia
width: 1920px
height: 1080px
---

<!-- _class: lead -->
# Einführung OpenStreetMap

Stephan Knauß
November 2020

<!-- 

Kurze Einführung zu meiner Person:
- Softwareentwickler im Automotive-Umfeld
- Aktiv bei OSM seit 2008
  - Aktive Datenerfassung
  - Tile-Server, Qualitätssicherung, weitere Dienste
  - Software, wenn ich etwas selbst brauche

-->

---

<!-- paginate: true -->
<!-- footer: '![height:1em](https://licensebuttons.net/l/by-sa/3.0/88x31.png) Stephan Knauß' -->

# Was ist OpenStreetMap

* OpenStreetMap ist eine freie Datenbank von Geodaten unter der ODbL
* OpenStreetMap ist ein Ökosystem rund um Geodaten
* OpenStreetMap ist eine Gemeinschaft von Mappern

- OpenStreetMap Foundation verwaltet die Server und bietet rechtlichen Rahmen

---

# Wie alles begann

* OpenStreetMap wurde 2004 von Steve Coast gegründet
* Begann als Antwort auf nicht verfügbare freie Karten
* Basiert auf eigener Open-Source Software und eigenem Datenmodell

---

# Das Projekt wächst

Jedes Jahr registrieren sich mehr Mitglieder bei OpenStreetMap

Stand November 2020 sind es über 7,1 Millionen registrierte Mitglieder

* ca. 8,3 Milliarden GPS Datenpunkte
* ca. 6,5 Milliarden _Nodes_
* ca. 715 Millionen _Ways_

<!-- 

Aktuelle Statistik:
https://www.openstreetmap.org/stats/data_stats.html

Ich erzähle auf den folgenden Slides etwas mehr zu GPS, Nodes und Ways

-->

---

# Freie Daten

* Die Daten können frei gemäß der Open Database License (ODbL) verwendet werden
* Immer unter Angabe der Quelle, z. B. bei daraus produzierten Karten
  * © OpenStreetMap contributors
* Share-Alike, wenn abgeleitete Daten aus OSM erzeugt werden

<!-- -

https://www.openstreetmap.org/copyright

-->

---

# Die Datenstruktur

OpenStreetMap definiert seine eigene Datenstruktur für Geometrie und Attributierung

---

![drop-shadow height:15em](edit_nodes.png)
**Nodes** (Punkte) tragen Koordinaten, z. B. POI

---

![drop-shadow height:15em](edit_way.png)
Mehrere Nodes in einer Reihenfolge definieren einen **Way**

---

![drop-shadow height:15em](edit_closed_way.png)
Ein geschlossener Weg definiert ggf. eine Fläche, abhängig von Tags

---

![drop-shadow height:15em](edit_network.png)
Sieht schon fast aus wie eine Karte

---

![drop-shadow height:15em](edit_tagged.png)
Tags geben den geometrischen Details eine Bedeutung

---

# Die Datenstruktur

**Nodes** (Punkte) tragen Koordinaten

Mehrere Nodes in einer Reihenfolge definieren einen **Way**

Ein geschlossener Weg definiert ggf. eine Fläche, abhängig von Tags

Mit einer **Relation** verbindet man Nodes und Ways zu komplexen Strukturen wie Multipolygonen (z. B. See mit einer Insel) oder Beschreibung von Buslinien

---

# Tags

* Tags geben den geometrischen Details eine Bedeutung
* Straße: `highway=residential` 
* Teich: `natural=water`
* Siedlung: `place=neighbourhood`
* Tags sind key/value Paare
* Tags werden von der Community entwickelt, keine zentrale Vorgabe
* Wichtige Dokumentation ist das Wiki

---

# Datenerfassung per GPS

* Ursprünglich rein mittels GPS
  * Genauigkeit GPS nur einige Meter. Ionosphäre, Reflexion
  * Viele GPS Tracks sammeln und dann mitteln

![image height:6em](EK_iBlue747Logger2.jpg) ![image height:6em](Garmin_oregon.jpg) ![image height:6em](GPS_Receivers_2007.jpg)

---

![drop-shadow height:15em](map_gps_tracks.png)
GPS Spuren in München

<!-- 

Viele GPS Spuren lassen das Straßennetz erahnen.
Im Detail fallen aber Ungenauigkeiten auf. Ebenfalls ist die Genauigkeit relativ beschränkt.

-->

---

# Datenerfassung per Luftbild
  * Wenn gut ausgerichtet, in flachem Gelände gute Lagegenauigkeit. 50 cm oder besser
  * Probleme bei bergigem Gelände, da Höhenmodell benötigt
  * Fehlerquellen
    * Parallaxe z. B. bei hohen Gebäuden
    * Offset des Luftbilds wenn nicht genau georeferenziert
    * Konkrete Geometrie beim Abmalen ignoriert

<!-- 

Früher nur Satellittenbilder von Landsat. Später in ausgewählten
Gebieten bessere Auflösung durch Yahoo.
Seit Ende 2010 Bing Luftbilder verfügbar, seit 2017 DigitalGlobe/Maxar

-->

---

![drop-shadow height:15em](map_erlangen_5cm.jpg)
5 cm Bodenauflösung in Erlangen

---

![drop-shadow height:15em](map_parallaxe.jpg)
Parallaxe bei hohen Gebäuden

---

![drop-shadow height:15em](map_bad_buildings.jpg)
Offset des Luftbilds, falsche Geometrie, Überlappung

---

# Datenerfassung durch Import

* Importe nicht so gerne gesehen
  * Daten oft veraltet oder bereits vorhanden
  * Keine Community, die aktuell hält
* Grenzrelationen typisches Beispiel für Import

---

# Editoren

* iD ist ein web-basierter Editor, gut für schnelle Edits
* JOSM mächtiger Desktop Editor

---

![drop-shadow height:15em](editor_id.jpg)
Browser Editor iD

---

![drop-shadow height:15em](editor_josm.jpg)
Profi-Editor JOSM auf dem Desktop

---

![drop-shadow height:15em](editor_mapillary.jpg)
Mapillary: Crowdsoured Street-Level Imagery

---

# Mobile Spezialeditoren/Apps

* Vespucci, https://play.google.com/store/apps/details?id=de.blau.android
* StreetComplete, https://play.google.com/store/apps/details?id=de.westnordost.streetcomplete
* Maps.me
* OsmAnd

---

![drop-shadow height:15em](editor_vespucci1.jpg) ![drop-shadow height:15em](editor_vespucci2.jpg) ![drop-shadow height:15em](editor_vespucci3.jpg)
Vespucci Smartphone Editor

---

![drop-shadow height:15em](editor_streetcomplete1.jpg) ![drop-shadow height:15em](editor_streetcomplete2.jpg) ![drop-shadow height:15em](editor_streetcomplete3.png)
StreetComplete mobiler Spezialeditor

---

# OSM Anwendungen

* Karten (Facebook, Apple, Microsoft, Mapbox, …)
  * verschiedene Spezialkarten mit Fokus auf speziellen Details
  * Statische Karten als Bitmap
  * Dynamische Vektorkarten im Browser oder auf Handy

---

![drop-shadow height:12em](map_osm_carto.png)
OpenStreetMap „Standard“ Layer
https://www.openstreetmap.org/#map=17/48.13715/11.57318

---

![drop-shadow height:12em](map_cyclosm.png)
CyclOSM
https://www.cyclosm.org/#map=16/48.1371/11.5731/cyclosm

---

![drop-shadow height:12em](map_öpnv.png)
ÖPNVKarte
https://www.openstreetmap.org/#map=16/48.1372/11.5732&layers=O

---

![drop-shadow height:12em](map_thunderforest_transport.png)
Thunderforest Transport Map
https://www.openstreetmap.org/#map=16/48.1372/11.5732&layers=T

---

![drop-shadow height:12em](map_stamen_watercolor.png)
Stamen Design Watercolor
http://maps.stamen.com/watercolor/#12/37.7706/-122.3782

---

# Weitere Anwendungen

* Routing
* Garminkarten
* GIS Anwendungen, z. B. ArcGIS oder QGIS
* Overpass (mit overpass-turbo.eu)

---

# Wie kann man beitragen?

* Anmelden und loslegen, Übung 🗺️ macht den Meister👨‍🎓
* Im wiki.openstreetmap.org gibt es Anleitung für erste Schritte
* Erst langsam herantasten, nicht gleich alles neu machen
* Details in der näheren Umgebung prüfen/ergänzen
* OSM Notes überprüfen

---

# Fehler finden mit Osmose

* Osmose wendet verschiedene Regeln an, um mögliche Fehler zu finden
* Nicht alles was gemeldet wird, ist auch wirklich ein Fehler!
* Mit *eindeutigen* Problemen Erfahrung sammeln

---

![drop-shadow height:15em](editor_osmose.jpg)
Mögliche Verbesserungen in Gärtringen

---

# Community

* Stammtische
  * https://usergroups.openstreetmap.de/
* Mailingliste
* Forum
* Wochennotiz
* IRC, Facebook, Telegram

---

![drop-shadow height:15em](map_usergroup.png)
Ein weißer Fleck auf der Community-Karte

---

# Noch Fragen? Live Demo!
<!-- _class: lead -->

---
<!-- _class: lead -->

# Vielen Dank für die Aufmerksamkeit

https://github.com/stephankn/osm-intro

&copy; 2020 Stephan Knauß, CC-BY-SA
Created with https://marp.app/

---

# Quellen

GPS Logger
https://wiki.openstreetmap.org/wiki/File:Garmin_oregon.jpg
https://wiki.openstreetmap.org/wiki/File:EK_iBlue747Logger2.jpg
https://wiki.openstreetmap.org/wiki/File:GPS_Receivers_2007.jpg
