---
title: "S&I - Corso SOSEC"
linkTitle: "S&I - Corso SOSEC"
weight: 10
mermaid: false
---

Le informazioni contenute in questa pagina sono state ottenute durante lo svolgimento del corso CAI sul catasto digitale dei sentieri: <https://formazione.cai.it/cai/course/view.php?id=6>.

Il corso è attivabile dai soci CAI interessati facendo richiesta sul sito di supporto del CAI (<https://supporto.cai.it/>). Come esempio vedere: <https://supporto.cai.it/issues/9523>.

Il corso è suddiviso in livello Base, Intermedio e Avanzato.

## Introduzione

![SOSEC logo](/img/corsososec/sosec.png)

Il lavoro sul catasto nazionale dei sentieri è portato avanti dal SOSEC (Struttura Operativa Sentieri e Cartografia). Tra gli obiettivi di questa struttura c'è quello di costruire in collaborazione con la rete dei circoli CAI il "Catasto Nazionale dei Sentieri". Un acronimo spesso utilizzato è quello della "Rete Escursionistica Italiana" (REI).

E' stato stipulato un protocollo d'intesa "Per un turismo montano sostenibile e responsabile" tra CAI e MiBACT (Ministero per i Beni e le Attività Culturali e il Turismo), con l'obiettivo, tra gli altri, di valorizzare la rete sentieristica.

Successivamente CAI e Wikimedia Italia hanno stipulato una convenzione "...per promuovere e migliorare le modalità di fruizione da parte del pubblico dei dati geografici relativi all'ambiente montano".

L'idea di base è che il CAI, attraverso il SOSEC, fornisce dentro OpenStreetMap (OSM) le informazioni sulla sentieristica e i rifugi all'interno del DB OSM, rendendoli così consultabili da tutti in forma libera.

Le linee guida CAI per l'inserimento dei percorsi escursionistici all'interno del DB OSM sono contenute in una pagina dedicata sul Wiki OSM: <https://wiki.openstreetmap.org/wiki/IT:CAI>

Il CAI si sta contestualmente dotato di un proprio sito per la visualizzazione della sentieristica e delle relative informazioni. Questo sito, **[Infomont]**, estrae le informazioni da OSM in una sola direzione. Non è previsto di riportare le informazioni sui sentieri direttamente in Infomont. Le informazioni vanno inserite su OSM e, attraverso un meccanismo automatico [? da chiarire] vengono riportate e visualizzate in Infomont.

Alcune definizioni:

- **Percorso**: tracciato escursionistico, costrituito da tratte, inserito nel catasto dei sentieri
- **Tratta**: parte di percorso identificato da un punto iniziale, uno finale e dall'omogeneità in ogni suo punto di elementi che lo caratterizzano (p.e. la tipologia di tracciato).

## Siti e strumenti principali per iniziare

In questa sezione vediamo i principali siti e le App che possono essere utilizzare per l'inserimento e la fruizione della sentieristica REI.

**[OpenStreetMap] (OSM)**

<https://www.openstreetmap.org/>: Sito principale per la consultazione e l'editing del DB Openstreetmap (a.k.a. OSM). Effettuando il login con il proprio account è possibile da subito modificare i contenuti, fare upload di tracce, ecc.

**[WayMarked Trails] (WMT)**

<https://waymarkedtrails.org/>: qui è possibile aprire varie mappe dove visualizzare i sentieri di interesse per l'hiking, MTB, ecc. Si possono vedere informazioni e scaricare tracciati GPX. E' di fatto un esempio di come potrebbe essere fatto Infomont. Il codice è liberamente disponibile su GitHub (<https://github.com/waymarkedtrails>).

Per esempio aprendo la pagina dedicata all'hiking (<https://hiking.waymarkedtrails.org/>) si possono osservare e ottenere dettagli e tracciati GPX di molti sentieri del mondo e in particolare per l'Italia si possono visualizzare e ottenere informazioni su SI e REI.

Se si effettua uno zoom su una zona e si clicca sul tasto "Routes" in basso a destra, si apre una finestra con tutte i percorsi disponibili su quella zona.

Si cominciano a capire alcuni concetti base di OSM.

Ogni percorso completo, per esempio un sentiero numerato CAI, viene definito su OSM tramite una “Relazione” (Relation). Questo porta ai quattro tipi di elementi geometrici definiti su OSM:

- **[Nodo]**: un punto sulla superficie terrestre
- **[Linea]**: un percorso costituito da una sequenza di nodi collegati tra loro
- **[Area]**: superficie chiusa poligonale, p.e. un edificio
- **[Relazione]**: Un insieme di elementi relazionati tra loro. Può essere per esempio utilizzato per un percorso escursionistico costituito da più linee (highway). Per esempio è possibile trovare le relazioni su WMT

[WayMarked Trails] è il sito migliore per prendere confidenza con il concetto di "[Relazione]" che è fondamentale per l'inserimento e la caratterizzazione dei sentieri CAI in OSM. Infatti su questo sito è estremamente semplice trovare i percorsi e agganciarsi alla relativa relazione su OSM. Una volta aperta la relazione su OSM si possono osservare i segmenti (elementi [Linea] di OSM) che la compongono ed è anche possibile consultare la cronologia delle modifiche che sono state fatte alla relazione nel corso del tempo (cliccare su "Visualizza Cronologia" (View History)).

**[Sentiero Italia] (SI)**

Il sito ufficiale con tutte le informazioni sul Sentiero Italia. La sottosezione con le mappe è reperibile al seguente link: <https://sentieroitaliamappe.cai.it/>

**[GeoResQ]**

App e Sito che costituistono un servizio a pagamento, gratuito per i Soci CAI, che è possibile utilizzare per registrare e analizzare tracce. Offre inoltre un servizio per la gestione di allarmi in casi di incidenti in montagna.

Tramite la app si possono registrare tracce con possibilità di inserire waypoint anche fotografici. Le tracce sono poi consultabili e scaricabili dal sito GeoResQ

**[OsmAnd]**

L'app ufficiale di OpenStreetMap per navigazione e visualizzazione di mappe online e offline per Android e IOS. Offre alcune funzionalità gratuite e altre a pagamento.

**[OverPass Turbo]** (OPT)

un sito tramite il quale è possibile fare query sul DB OSM. Con un wizard è possibile interrogare per tag. Il sito utilizza la [OverPass API] (_“A Database engine to query the OSM data”_) per la costruzione delle query. Per ulteriori dettagli:

- Pagina su Wiki OSM: <https://wiki.openstreetmap.org/wiki/Overpass_API>
- Documentazione completa: <https://dev.overpass-api.de/overpass-doc/en/>

## Concetti utili per mappare: i tag

Definire gli elementi geometrici dentro OSM è solo il primo passo. Il lavoro veramente importante è definire le **etichette** (tag) associate all'elemento.

Tramite i tag, che non sono altro che una coppia `chiave=valore`, si forniscono informazioni addizionali sull'elemento geometrico. Per esempio a un punto che rappresenta la posizione di una fontanella di acqua potabile viene associato il tag `amenity=drinking_water`.

Curiosità: ricercando per esempio i pali di segnaletica su Monte Morello, facendo la query `tourism=information and information=guidepost` su OPT, si vede che questi non sono riportati. Si può invece vedere che sulla Calvana gli stessi sono disponibili.

La guida completa sui tag disponibili su OSM è disponibile al seguente link: <https://wiki.openstreetmap.org/wiki/IT:Map_Features>. Questa è anche la pagina fondamentale per capire come rappresentare oggetti sulle mappe.

Per cercare tutti gli elementi associati al CAI di Sesto Fiorentino (codice sezione CAI = 9226011) si può fare la seguente query su OPT: `source:ref=9226011`. Il risultato è visibile nell’immagine sotto. Si nota che trattasi sostanzialmente di sentieri (definiti come "Relation") più un nodo dove è localizzata la sede CAI di Sesto Fiorentino (pallino giallo in basso a sinistra).

![Rete escursionistica CAI Sesto Fiorentino](/img/corsososec/rete_sentieristica_CAI_SF.png)

Il codice OverPass API relativo è il seguente:

```json
/*
This has been generated by the overpass-turbo wizard.
The original search was:
“source:ref=9226011”
*/
[out:json][timeout:25];
// gather results
(
  // query part for: “"source:ref"=9226011”
  node["source:ref"="9226011"]({{bbox}});
  way["source:ref"="9226011"]({{bbox}});
  relation["source:ref"="9226011"]({{bbox}});
);
// print results
out body;
>;
out skel qt;
```

Per l'elenco delle relazioni sotto la responsabilità della sezione di Sesto Fiorentino, vedere la [pagina dedicata](({{< ref "censimento_sentieri_sesto_fiorentino/_index.md" >}} "Censimento Sentieri CAI Sesto Fiorentino"))

Altri codici di sezioni CAI:

- Prato: 9226008
- Firenze: 9226001
- Porretta Terme: 9224018. Per esempio, questa sezione oltre a sentieri identifica con il tag `source:ref` anche altri tipi di elementi.
- Bologna: 9224002
- Reggio Emilia: 9224008

NOTA: +Non sono riuscito a trovare un sito/documento dove ottenere tutti i codici delle sezioni CAI nazionali utilizzati per il tag `source:ref`.

## Concetti utili per mappare: informazioni sulle relazioni

Abbiamo visto che ogni sentiero/percorso CAI è inserito dentro OSM come [Relazione]. Analizzando le relazioni disponbili utilizzando tool come [WayMarked Trails] o [OverPass Turbo] è possibile analizzare le relazioni e dividerli nei loro costituenti elementari OSM che possono essere semplicemente Linee o anche Nodi che contraddistinguono punti notevoli.

Un sito interessante per valutare la bontà della relazione è **[OSM Relation Analyzer]**. Il sito valuta la qualità della relazione e ne riassume le caratteristiche principali come il profilo altimetrico e caratteristiche del terreno.

Un altro sito utile è **[TagInfo]**, un’applicazione web che permette di trovare ed aggregare informazioni sulle etichette (tags) di OSM e rendere queste informazioni consultabili e ricercabili. È molto utile per capire quanto è usato un tag, inoltre può essere sfruttato quando si è indecisi quale tag applicare agli oggetti in caso di dubbio.

Per esempio collegandosi al sito si può cercare il tag `cai_scale`, ottenendo informazioni di vario tipo sul tag stesso. Per esempio, net tab "Overview" si può vedere su che tipi di elementi OSM il tag è utilizzato:

![TagInfo: risultato ricerca cai_scale (overview)](/img/corsososec/taginfo_caiscale.png)

Un altro tab molto utile è "Combinations" che permette di vedere a quali altri tag il tag in questione è associato. Per esempio, dallo screenshot sotto si può vedere come gli item che hanno il tag `cai_scale` hanno pressoché sempre anche il tag `type` (99.15%), così come che gli elementi che hanno il tag `ref:REI` hanno praticamente sempre anche il tag `cai_scale`.

![TagInfo: risultato ricerca cai_scale (combinations)](/img/corsososec/taginfo_caiscale_combo.png)

## Concetti utili per mappare: gli editor

Per lavorare sul DB OSM bisogna dotarsi per prima cosa di un di un **editor**. Ne esistono molti (vedere <https://wiki.openstreetmap.org/wiki/Comparison_of_editors>), ma la formazione SOSEC si concentra su due principali:

- [iD]: Editor online integrato nel sito OSM. Si attiva cliccando sul tasto "Edit" in alto a sinistra del sito OSM. Una volta attivato è possibile effettuare modifiche (inserire nuovi elementi o modificare elementi esistenti) e salvarle.

![OSM Edit](/img/corsososec/osm_edit_button.png)

- Il software [JOSM]. Trattasi di un software desktop molto più complesso e potente di [iD]. Per approfondimenti vedere la [pagina dedicata]({{< ref "josm.md" >}} "JOSM").

[OpenStreetMap]: https://www.openstreetmap.org/
[Infomont]: https://infomont.cai.it/
[WayMarked Trails]: https://waymarkedtrails.org/
[Nodo]: https://wiki.openstreetmap.org/wiki/Node
[Linea]: https://wiki.openstreetmap.org/wiki/Way
[Area]: https://wiki.openstreetmap.org/wiki/Area
[Relazione]: https://wiki.openstreetmap.org/wiki/Relation
[Sentiero Italia]: https://sentieroitalia.cai.it/
[GeoResQ]: https://www.georesq.it/
[OsmAnd]: https://osmand.net/
[OverPass Turbo]: https://overpass-turbo.eu/
[OverPass API]: https://dev.overpass-api.de/overpass-doc/en/
[iD]: https://wiki.openstreetmap.org/wiki/ID
[JOSM]: https://josm.openstreetmap.de/
[OSM Relation Analyzer]: http://ra.osmsurround.org/
[taginfo]: https://taginfo.openstreetmap.org/
