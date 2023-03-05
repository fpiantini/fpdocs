---
title: "Come gestire la sentieristica con OSM"
linkTitle: "Come gestire la sentieristica con OSM"
weight: 30
---

Questa pagina contiene una FAQ con indicazioni di come gestire una rete di sentieristica (per esempio come quella del CAI) tramite OSM. Alcune delle cose scritte si applicano in generale ai sentieri, altre più specificatamente alla sentieristica CAI. La FAQ è stata costruita nel tempo seguendo la discussione sul [gruppo Telegram OpenStreetMap Italia] o tramite esperienza diretta dello scrivente con OSM (per esempio delle attività svolte vedere la pagina dedicata al [censimento dei sentieri CAI](({{< ref "censimento_sentieri_sesto_fiorentino/_index.md" >}} "Censimento Sentieri CAI Sesto Fiorentino")).

## Domanda: Come indicare un sentiero impraticabile per crescita di vegetazione?

Risposta letta sui forum OSM [domanda sui sentieri impraticabili].

Per indicare che un sentiero non è transitabile ci sono diversi modi, uno potrebbe essere mettere un tag `access=no`. Questo si applica se il sentiero è chiuso (ad esempio il Comune ha messo una sbarra e lo ha dichiarato non accessibile) oppure interrotto (esempio: una parte è franata)

Un altro modo è usare il tag `smoothness` : se non è più transitabile puoi mettere `smoothness=impassable`.

Il primo caso viene sicuramente riconosciuto dai router, il secondo dovrebbe, ma non ci metto la mano sul fuoco.

In entrambi i casi, puoi spezzare il sentiero in più parti (contigue) ed applicare i tag solo nelle sezioni interessate, senza necessariamente estendere la proprietà a tutta la way quando invece vale solo per un tratto.

Trovi maggiori dettagli nella Wiki, ti giro un po’ di link:

- https://wiki.openstreetmap.org/wiki/IT:Glossario_OSM
- https://wiki.openstreetmap.org/wiki/Tag:highway%3Dtrack
- https://wiki.openstreetmap.org/wiki/Key:access
- https://wiki.openstreetmap.org/wiki/Key:smoothness

[gruppo Telegram OpenStreetMap Italia]:https://t.me/OpenStreetMapItalia
[domanda sui sentieri impraticabili]:https://community.openstreetmap.org/t/come-indicare-un-sentiero-impraticabile-per-crescita-di-vegetazione/9489/1
