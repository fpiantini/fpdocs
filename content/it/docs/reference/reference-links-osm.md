---
title: "Links - Openstreetmap"
linkTitle: "Links - Openstreetmap"
weight: 15
mermaid: false
---

## Openstreetmap: sito e tool principali

Openstreetmap:

- [OpenStreetMap]: il sito principale dove visualizzaze ed editare (con l'editor [iD]) il contenuto del DB OSM.
- [Wiki OpenStreetMap]: contiene tutta la documentazione OSM. Alcune pagine particolarmente importanti:
  - [OSM Map features]: pagina fondamentale con la classificazione di tutti i tag principali

- Per l'interazione con la comunità OSM esistono vari canali, alcuni globali, altri specifici italiani:
  - Forum: <https://forum.openstreetmap.org/>
  - Elenco di tutte le mailing list: <https://wiki.openstreetmap.org/wiki/Mailing_lists>
  - Mailing list di OSM italia: <https://lists.openstreetmap.org/listinfo/talk-it>
  - Canale Telegram OSM Italia: <https://t.me/OpenStreetMapItalia>. In realtà questo canale è quello antispam da cui passare per essere messi nel canale vero

Altri siti principali:

- [Osmose-QA]: _"Osmose-QA è uno strumento per il controllo della qualità che individua i problemi nei dati OpenStreetMap."_

- [OverPass API]: le specifiche dell'API per estrarre dati dal DB OSM. Vedere anche il [manuale](https://dev.overpass-api.de/overpass-doc/en/index.html).
- [OverPass Turbo]: pagina web dove provare l'[OverPass API] costruendo e modificando query con un semplice wizard
- [TagInfo]: _"OpenStreetMap uses tags of the form key=value to add meaning to geographic objects. Taginfo collects information about these tags from several sources to help you understand what they mean and how they are used."_
- [Relation Analyzer]: _"analyzes OSM relations for gaps"_. Utile per analizzare i sentieri (che sono relazioni che uniscono way)


## Openstreetmap & sentieristica

### Interrogazione e visualizzazione sentieristica

- [WayMarked Trails]: _"[...] website that shows recreational routes from OpenStreetMap and lets you inspect the routes and selected details"_. Utilissimo per visualizzare percorsi e segnavia. Codice disponibile su [GitHub](https://github.com/waymarkedtrails).
- [Destination Signs]: _"shows the content of relations with `type=destination_sign`, `direction_*` tags on guideposts as well as `destination` tags on highways and guideposts."_. Utile per visualizzare i segnavia. Codice disponibile su [GitHub](https://github.com/mueschel/OsmDestinationSigns).

### Pianificazione itinerari

Tramite questi siti che hanno funzionalità di Routing, è possibile costruire itinerari escursionistici e salvare le relative tracce GPX. Molto utili in fase di pianificazione delle escursioni.

- [AllTrails]: Occorre registrarsi, ma permette di fare tutto gratis
- [Komoot]: Per usarlo bene occorre fare un abbonamento a pagamento
- [Outdoor Active]: Per usarlo bene occorre fare un abbonamento a pagamento

### Visualizzazione ed editing GPX

Siti che permettono la visualizzazione di file GPX su cartografia. In alcuni casi permettono l'editing.

- [GPX Studio]: visualizza i GPX su basemaps di cartografia e layer overlay addizionali. Molto interessante per esempio la possibilità di visualizzare come overlay [WayMarked Trails].
- [UMAP]: Permette di creare mappe personalizzate, anche caricando GPX
- [GPS Visualizer]: _"GPS Visualizer is an online utility that creates maps and profiles from geographic data"_

### OSM & CAI - Catasto digitale dei sentieri

Si rimanda anche alla pagina dedicata al [Corso SOSEC]({{< ref "corsososec.md" >}} "JOSM").

- [Pagina CAI] su OSM: riporta per esempio i tag da utilizzare quando si modificano oggetti OSM che riguardano sentieri, rifugi e altri oggetti CAI su OSM.
- [Pagina REI] su OSM: informazioni sulla Rete Escursionistica Italiana gestita dal CAI.
- [GeoResQ]: Sito collegato all'app GeoresQ, dove si possono visualizzare e scaricare le tracce registrate con l'app.

## Cartografia online

- [Geoscopio Regione Toscana]: strumento webgis con cui è possibile visualizzare ed interrogare i dati geografici della Regione Toscana.
- [Geoscopio Toscana - Sentieristica]: visualizzazione della sentieristica CAI della regione Toscana.

## Cartografia offline

Per applicazioni su smartphone (e.g. OruxMaps):

 - [OpenAndroMaps]: Le migliori per l'escursionismo tra quelle provate al momento. Hanno il formato pronto per OruxMaps
 - [FreizeitKarte]: Mappe per Android smartphone/tablet o per ricevitori GNSS Garmin. Hanno il formato pronto per OruxMaps

## Altri siti / Applicazioni basati su OSM

### Applicazioni per visualizzazione mappe e percorsi

Posso essere utilizzate per pianificazione itinerari ed editing GPX su PC o Smartphone.

#### PC

Compatibili Linux:

- [QMapShack]: "_Use QMapShack to plan your next outdoor trip or to visualize and archive all the GPS recordings of your past exciting adventures. QMapShack is the next generation of the famous QLandkarte GT application. And of course it's even better and easier to use._"
- [GpsPrune]: "_GpsPrune is an application for viewing, editing and converting coordinate data from GPS systems. Basically it's a tool to let you play with your GPS data after you get home from your trip._"
- [Viking]: "_Viking is a free/open source program to manage GPS data. You can import, plot and create tracks, routes and waypoints, show OSM, Bing Aerial and other maps, geotag images, create routes using OSRM, see real-time GPS position (not in Windows), make maps using Mapnik (not in Windows), control items, etc._"

Solo Windows:

- [OkMap]: "_A GPS cartographic software for Windows. Project and walk along your trails!_" (Versione Full a pagamento)

#### Smartphone

- [Organic maps]: "_Organic Maps is a free Android & iOS offline maps app for travelers, tourists, hikers, and cyclists based on top of crowd-sourced OpenStreetMap data and curated with love by MapsWithMe ([Maps.Me](https://maps.me/)) founders."_

### Mappamondi (tipo google earth)

- <https://ge-map-overlays.appspot.com/>: _"a Google Earth KML network link that displays a big variety of tile based online maps (road maps, terrain and contour maps, alternative satellite image sets, etc) in the area you are currently viewing"_. Da usare con Google Earth
- [Marble](https://marble.kde.org/): _"a virtual globe and world atlas"_. KDE based, esiste sia per Desktop che per Mobile
- [WorldWind Explorer](https://worldwind.earth/explorer/)
- [Web GL Earth](https://www.webglearth.com/)

## Applicazioni per Smartphone

### Per tracciare e seguire percorsi (orientati all'escursionismo)

[OruxMaps]: Il meglio del meglio... Solo per Android.

[OpenStreetMap]:https://www.openstreetmap.org/
[iD]:https://wiki.openstreetmap.org/wiki/ID
[Wiki OpenStreetMap]:https://wiki.openstreetmap.org/wiki/Main_Page
[OSM Map features]:https://wiki.openstreetmap.org/wiki/Map_features
[Osmose-QA]:http://osmose.openstreetmap.fr/
[OverPass API]: https://dev.overpass-api.de/overpass-doc/en/
[OverPass Turbo]: https://overpass-turbo.eu/
[TagInfo]: https://taginfo.openstreetmap.org/
[Relation Analyzer]:http://ra.osmsurround.org/index

[WayMarked Trails]: https://waymarkedtrails.org/
[Destination Signs]:http://osm.mueschelsoft.de/destinationsign/example/index.htm

[AllTrails]:https://www.alltrails.com/
[Komoot]:https://www.komoot.com/
[Outdoor Active]:https://www.outdooractive.com/it/mypage/

[GPX Studio]:https://gpx.studio/
[UMAP]:https://umap.openstreetmap.fr/it/
[GPS Visualizer]:https://www.gpsvisualizer.com/

[GeoResQ]: https://www.georesq.it/
[Pagina CAI]:https://wiki.openstreetmap.org/wiki/IT:CAI
[Pagina REI]:https://wiki.openstreetmap.org/wiki/REI

[Geoscopio Regione Toscana]:https://www.regione.toscana.it/-/geoscopio
[Geoscopio Toscana - Sentieristica]:http://www502.regione.toscana.it/geoscopio/sentieristica.html
[OpenAndroMaps]:https://www.openandromaps.org/en
[FreizeitKarte]:https://www.freizeitkarte-osm.de/

[GpsPrune]:https://activityworkshop.net/software/gpsprune/index.html
[QMapShack]:https://github.com/Maproom/qmapshack/wiki
[Viking]:https://sourceforge.net/projects/viking/
[OkMap]:https://www.okmap.org/default.aspx

[Organic maps]:https://organicmaps.app/

[OruxMaps]:https://www.oruxmaps.com/cs/en/

