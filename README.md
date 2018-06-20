# Mapping 101 - The very basics every data journalist should know about mapping

A workshop held at German investigative journalist conference [Netzwerk Recherche 18](https://nr18.sched.com/event/E4vf) by Hannes Kröger, Patrick Stotz, Achim Tack and Marie-Louise Timcke.

**This document is very much work in progress - come back at the end of June to see the finished version**

*Interne Notiz: Die grobe Struktur stammt aus unserem Brainstorming. Lasst uns wie geplant versuchen, alles in diesem Repository zu sammeln. Sammlung auf englisch, Workshop dann auf deutsch. Die deutschen Texte zwischendrin sind die Umschreibungen was wir in den Kapiteln grob vor haben. Sollten dann nach und nach verschwinden, wenn wir das hier mit Inhalt füllen.*


## Quickstart QGIS (10 min)
*Wir zeigen die absoluten QGIS basics: Bedienelemente, File-Browser, Plugin-Installation, Info-I, Print composer,...*


## File formats (15 min)
*Wir sollten ganz kurz erklären, was der Unterschied zwischen Raster- und Vektordaten ist. Am besten anhand von Beispielen/Beispielabbildungen*

*Datentypen, die einem als Datenjournalist häufiger begegnen und wie man sie in QGIS einlädt. Beispiele in einen Repository-Unterordner packen und dann live vorführen*
- shapefile
- basemap
- WMS
- WFS
- xls(x) / csv with coordinates
- geotiff


## Data sources (10 min)
*Hier die häufigsten / nützlichsten Quellen für Datenjournalisten (in Deutschland) aufführen und im Workshop ausschnittsweise zeigen. Am besten thematisch sortiert à la: administrative Grenzen, Luftbilder,OSM...*

- Natural Earth http://www.naturalearthdata.com/
- BKG
- TPHH http://suche.transparenz.hamburg.de/ & http://suche.transparenz.hamburg.de/?extras_registerobject_type=geodat
- OSM
  - Einzelne Features (via Query auf osm.org)
  - Regionale Extrakte
  - Overpass(-Turbo)
  - QuickOSM
- Copernicus, Landsat https://remotepixel.ca/, https://search.remotepixel.ca/, https://github.com/ungarj/awesome-sentinel-2, https://github.com/attibalazs/awesome-remote-sensing


## Handling geodata properly (10 min)
*Projektionen, Generalisierung, Dateiformate konvertieren, Geodaten editieren ohne Originaldaten zu zerschießen*
### Projections
Earth is not flat, it's quite spherical. Our maps are usually flat. Projections try to somehow map earth's geography onto a plane (such as a piece of paper or a computer display).
- https://mapschool.io/#latitude--amp--longitude
- https://mapschool.io/projections.html

- Depending on the software used, you might be limited in your choices.

#### EPSG Codes
TODO

#### Map of the whole world?
- Do you need to preserve a certain property (like area or direction)?
Try to avoid the Mercator or Galls-Peters projections, their distortions are quite extreme and politically loaded.
- Do you want a nice looking compromise?
  - https://en.wikipedia.org/wiki/Robinson_projection
  - https://en.wikipedia.org/wiki/Natural_Earth_projection
  - https://en.wikipedia.org/wiki/Winkel_tripel_projection
    
#### Map of a specific state or country (or a part of it)
- Use the state/country's official projection. If in doubt, use the local UTM cell/zone.

#### Map of the whole of Europe (or DACH)?
- Use the LAEA projection EPSG:3035
- https://gis.stackexchange.com/questions/209019/what-is-the-ideal-equal-area-projection-to-map-germany-switzerland-and-austria/209020

#### Map of a specific region
- http://projectionwizard.org/ -> Then add as custom projection in QGIS

## Answering spatial questions (15 min)
*Table join, spatial join, buffer*

Beispiele könnten sein:
- Zensus Raster -> wie viele Menschen sind von X betroffen
- Wieviele Ärzte in irgendeinem Bereich
- Objekte finden auf die “etwas “ zutrifft
