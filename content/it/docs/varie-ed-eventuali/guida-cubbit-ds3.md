---
title: "Guida a Cubbit DS3"
linkTitle: "Guida a Cubbit DS3"
weight: 30
---

# CUBBIT DS3

Cubbit Docs: https://docs.cubbit.io/it/getting-started/what-is-cubbit-ds3

Console Cubbit DS3: https://console.cubbit.eu/


## Creare progetti e bucket su Cubbit DS3 utilizzando la console web

TO BE COMPLETED

Al momento (2023-10) su Cubbit DS3 per utente francesco.piantini@gmail.com esiste un progetto chiamato "norstrilia". All'interno del progetto Norstrilia esiste un bucket "shayol".

### Users

All'interno dei progetti è possibile creare utenti con diversi livelli di permesso. Ne ho creato uno per fpiantales@norstrilia.net, ma non è ancora chiaro a cosa potrebbe servire.

### API keys

Per interagire con Cubbit DS3 da un PC client, occorre creare delle API Key. Questo si fa dalla Console Cubbit.

Una chiave è costituita da due informazioni:

- Access Key ID: viene creata al momento, può essere recuperata collegandosi alla console e andando alla lista delle chiavi
- Secret: questo è invece disponibile solo al momento della creazione della chiave e quindi va salvato in un luogo sicuro

## Istruzioni per impostare un ambiente CUBBIT DS3 su PC

Una volta disponibile un bucket su Cubbit DS3 è possibile usarlo per varie operazioni da client. Qui proviamo a vedere come farci upload/download dati a scopo di backup. Per effettuare le operazioni è possibile utilizzare vari tool, come descritto sulla Cubbit Docs. Qui via via ne vedremo alcuni. L'uso dei tool in alcuni casi dipende dal sistema operativo in altri no.

### Utilizzare AWS-CLI (Linux)

https://docs.cubbit.io/it/integrations/aws-cli

Anche se questo sistema è probabilmente indipendente dall'o.s. per il momento è stato provato solo su Linux.

Per configurare la connessione con il progetto tramite la CLI AW dare i seguenti comandi:

```bash
$ aws configure --profile cubbit
AWS Access Key ID [None]:       <your Cubbit access key>
AWS Secret Access Key [None]:   <your Cubbit secret key>
Default region name [None]:     eu-west-1
Default output format [None]:   <enter>

$ aws configure set cubbit.s3.max_concurrent_requests 20

```

Dopo la configurazione, con la CLI AWS è possibile fare varie operazioni sul progetto collegato sul Cubbit DS3. Per esempio un buon comando per verificare che tutto stia funzionando, è quello che permette di elencare i bucket presenti nel progetto:

```bash
aws s3 --profile cubbit --endpoint https://s3.cubbit.eu ls
```

Altro esempio: se è presente un bucket by nome `mybucket` per elencarne il contenuto dare il seguente comando:

```bash
aws s3 --profile cubbit --endpoint https://s3.cubbit.eu ls s3://mybucket
```

Creare un bucket di nome `example-bucket`:

```bash
aws s3 --profile cubbit --endpoint https://s3.cubbit.eu mb s3://example-bucket
```

**NOTA:** Come si vede i comandi AWS CLI per Cubbit DS3 prevedono costantemente i due parametri `--profile` e `--endpoint`, per cui conviene crearsi un alias, p.e. su `zsh`:

```bash
alias awsc="aws s3 --profile cubbit --endpoint https://s3.cubbit.eu"
```

Negli ulteriori esempi presenti in questo tutorial si suppone che tale alias sia definito.

### Altri esempi AWS CLI

Si rimanda alla [Pagina per la CLI AWS] sulla documentazione ufficiale Cubbit per ulteriori esempi, qui sono riportati alcuni comandi di uso comune come referenza:

- Caricare un file all'interno di un bucket in una particolare sotto directory:

```bash
awsc cp filename s3://example-bucket/subdir/
```

- Scaricare lo stesso file dal bucket al PC locale:

```bash
awsc cp s3://example-bucket/subdir/filename .
```

- Cancellare un file all'interno di una subdir in un bucket:

```bash
awsc rm s3://example-bucket/subdir/filename
```

- Caricare ricorsivamente una cartella all'interno di un bucket:

```bash
awsc sync foldername s3://example-bucket/foldername/
```

- Scaricare la stessa dir dal bucket al PC locale in una directory con lo stesso nome:

```bash
awsc cp --recursive s3://example-bucket/foldername foldername
```

- Come esempio derivato dal precedente, per scaricare completamente un bucket in una directory locale con lo stesso nome, il comando da dare è:

```bash
awsc cp --recursive s3://example-bucket example-bucket
```

- Rimuovere completamente una sotto directory da un bucket:

```bash
awsc rm --recursive s3://example-bucket/foldername
```

### Mantenere sincronizzata una directory locale con un bucket

Un esempio di caso d'uso di Cubbit DS3 che può risultare utile, consiste nel mantenere una directory locale sincronizzata con un bucket. Supponendo di avere un primo PC (PC1) correttamente configurato per parlare con un progetto su Cubbit DS3 (vedere sezione sopra) e una directory locale inizialmente popolata con la seguente alberatura:

```
.
├── dir1
│   └── file1.txt
├── dir2
│   └── picture.png
└── README.md
```

#### Creazione e popolamento iniziale del bucket

Per caricare tale struttura in un bucket di nome `examplebucket` su Cubbit DS3, va per prima cosa creato un bucket con tale nome:

```bash
awsc mb s3://examplebucket
```

Verificare la corretta creazione del bucket:

```bash
awsc ls
awsc ls examplebucket
```

Il primo comando deve dare `examplebucket` nell'elenco dei bucket esistenti, il secondo non deve restituire errori, limitandosi a non presentare nessun messaggio sullo standard output poiché il bucket è al momento vuoto.

Si può a questo punto effettuare la simulazione dell'upload del contenuto della directory locale nel bucket `examplebucket` tramite un'operazione di `sync` con opzione `--dryrun`. Questa operazione non esegue alcuna operazione reale, ma elenca le operazioni che verrebbero eseguite se si omettesse l'opzione `--dryrun`:

```bash
awsc sync --dryrun . s3://examplebucket
```

Il comando deve generare i seguenti messaggi su `stdout`:

```
(dryrun) upload: ./README.md to s3://examplebucket/README.md
(dryrun) upload: dir1/file1.txt to s3://examplebucket/dir1/file1.txt
(dryrun) upload: dir2/picture.png to s3://examplebucket/dir2/picture.png
```

L'upload reale dei file su bucket si effettua usando il comando precedente senza l'opzione `--dryrun`

```bash
awsc sync . s3://examplebucket
```

Il comando deve generare i seguenti messaggi su `stdout`:

```
upload: ./README.md to s3://examplebucket/README.md
upload: dir1/file1.txt to s3://examplebucket/dir1/file1.txt
upload: dir2/picture.png to s3://examplebucket/dir2/picture.png
```

Si può verificare la presenza dei file nel bucket su Cubbit DS3:

```bash
awsc ls --recursive examplebucket
```

tale comando deve generare il seguente output:

```
2023-11-01 11:50:01       4315 README.md
2023-11-01 11:50:02       4340 dir1/file1.txt
2023-11-01 11:50:01      36669 dir2/picture.png
```

#### Download del bucket su un altro PC (PC2)

Il bucket appena creato e popolato può essere a questo punto scaricato su un altro PC client (o in un'altra directory dello stesso client), tramite il comando:

```bash
awsc sync s3://examplebucket .
```

Che deve generare i seguenti messaggi su  `stdout` (non necessariamente nello stesso ordine):

```
download: s3://examplebucket/dir1/file1.txt to dir1/file1.txt
download: s3://examplebucket/README.md to ./README.md
download: s3://examplebucket/dir2/picture.png to dir2/picture.png
```

A questo punto nella directory devono essere presenti tutti i file del bucket posizionati con la corretta alberatura (utilizzare p.e. il comando `tree` per verificare), e i due PC (PC1 e PC2) risultano sincronizzati.

#### Modifica locale e sincronizzazione su bucket

A questo punto, su uno qualsiasi dei due PC, modifichiamo il file `dir1/file1.txt`. Nel nostro esempio supponiamo di farlo su PC2. Dopo la modifica, se su PC2 si da il comando `sync` in modalità dryrun:

```bash
awsc sync --dryrun . s3://examplebucket
```

Si deve ottenere il seguente output:

```
(dryrun) upload: dir1/file1.txt to s3://examplebucket/dir1/file1.txt
```

Se 



[Pagina per la CLI AWS]:https://docs.cubbit.io/it/integrations/aws-cli

