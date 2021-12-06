---
title: "JOSM"
linkTitle: "JOSM"
weight: 20
---

Dopo aver installato [JOSM], le operazioni da compiere sono le seguenti:

- Abilitare l'autenticazione su OSM tramite la pagina preferenze (**Edit -> Preferences** o semplicemente **F12**, voce **"OSM Server"**, utilizzare la modalità OAuth token fully automated)
- Installare le etichette preimpostate CAI dalla pagina delle preferenze sezione **"Tagging presets"** e cercare "CAI". Selezionare e installare tra i preset "Active.

![Installazione dei preset CAI](/img/josm/josm_installing_cai_presets.png)

A questo punto è possibile effettuare operazioni di modifica del DB OSM.

E' possibile scaricare da OSM vari tipi di dati. Per esempio, si possono scaricare tutti i dati di una particolare area zoomando sulla stessa e quindi selezionando tramite il menù **File -> Download data...**. Esistono vari modi.

- **Download from OSM**: per scaricare tutti i dati presenti in un'area si può scegliere il tab "Download from OSM". Si apre la cartografia di OSM, è possibile selezionare un'area rettangolare e quindi effettuare l'operazione di download premendo il tasto "Download". Bisogna solo fare attenzione a non selezionare un'area troppo grande, perché OSM ritorna un errore nel caso che la mole di dati da scaricare superi una certa soglia.

![Scaricare dati direttamente da OSM](/img/josm/josm_download_from_osm.png)

- **Download from Overpass API**: da qui è possibile scaricare dati effettuando una ricerca Overpass API.

In alternativa, possono essere scaricati i dati di un singolo oggetto del DB OSM tramite la voce di menù **File -> Download Object**. Qui va scelto il tipo di oggetto e l'ID.

[JOSM]: https://josm.openstreetmap.de/
