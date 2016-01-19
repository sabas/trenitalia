Treni Italia
========

Dati dal sito Viaggiatreno e qualche appunto.

Elenco Stazioni
---------------
La chiamata di autocompletamento è
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/autocompletaStazione/[stringa]
o anche (qual'è la differenza?)
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/autocompletaStazioneNTS/[stringa]

Risposta testuale separata dal carattere di pipe (|)

Vedi stazioni.tsv per un dump

In alternativa questa ricerca mostra informazioni più complete in json
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/cercaStazione/[stringa]

O ancora, elenco stazioni per regione
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/elencoStazioni/[idRegione]

Dettagli Stazione
-----------------
Trova la regione di appartenenza (esempio Oristano)
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/regione/S12878 (restituisce il valore 20)

Dettagli per la stazione di Oristano
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/dettaglioStazione/S12878/20
(codice_stazione/regione)

Vedi stazioni_coord.tsv per un dump contenente le coordinate, e stazioni_coord.geojson per la conversione (effettuata con geojson.io).

Stringhe varie
-------
Per ottenere stringhe in una determinata lingua che traducono le proprietà usate
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/language/{lingua}

Vedi stringsIT.tsv per l'esempio italiano.


Dettagli viaggio
----------------
Elenco stazioni con stato per ognuna
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/tratteCanvas/[codPartenza]/[codTreno]
dove:
- codPartenza è il codice trenitalia della stazione di partenza del treno
- codTreno è il codice del treno che parte dalla stazione richiesta
(se si vuole sapere lo status del treno 666 a Brignole, richiedere La Spezia Centrale (S06000) più il treno (666)

Gli orari sono in UNIX Timestamp con millisecondi (!!!), quindi basta togliere i tre zeri finali e convertirli nell'orario "normale".

Situazione treno
---------

http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/andamentoTreno/[codPartenza]/[codTreno]

Simile a tratteCanvas.

Trova stazione di partenza da codice treno
-----------
La chiamata di autocompletamento è
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/cercaNumeroTrenoTrenoAutocomplete/[codTreno]

dove codTreno è il codice del treno. Ad esempio il treno 666 restituisce una stringa del tipo
666 - LA SPEZIA CENTRALE|666-S06000
dove LA SPEZIA CENTRALE e S06000 si riferiscono alla stazione di partenza

In json invece è
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/cercaNumeroTreno/666

Varie
-------
Situazione meteo in diverse città
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/datimeteo/0

0 richiede per tutta Italia, altrimenti usare l'id della Regione (funziona solo per certe stazioni)

Notizie sulla rete
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/news/0/[lingua]
Ugualmente, 0 per tutta italia, altrimenti per regione. Lingua è il codice di due lettere (it/en/..)

Treni circolanti in un dato momento
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/statistiche/[timestamp]

Da documentare
-------------

// GET /resteasy/viaggiatreno/property/{name}

// GET /resteasy/viaggiatreno/elencoTratte/{idRegione}/{zoomlevel}/{categoriaTreni}/{catAV}/{timestamp}

// GET /resteasy/viaggiatreno/partenze/{codiceStazione}/{orario}

// GET /resteasy/viaggiatreno/arrivi/{codiceStazione}/{orario}

// GET /resteasy/viaggiatreno/elencoStazioniCitta/{stazione}

// GET /resteasy/viaggiatreno/dettagliTratta/{idRegione}/{idTrattaAB}/{idTrattaBA}/{categoriaTreni}/{catAV}

// GET /resteasy/viaggiatreno/dettaglioProgrammaOrario/{dataDa}/{dataA}/{idStazionePartenza}/{idStazioneArrivo}

// GET /resteasy/viaggiatreno/soluzioniViaggioNew/{codLocOrig}/{codLocDest}/{date}

// GET /resteasy/viaggiatreno/cercaProgrammaOrarioDestinazioneAutocomplete/{idStazionePartenza}

// GET /resteasy/viaggiatreno/cercaProgrammaOrarioOrigineAutocomplete/{idStazioneArrivo}

// GET /resteasy/viaggiatreno/dettaglioViaggio/{idStazioneDa}/{idStazioneA}

Authors
-------
@sabas
@marcobra

Nota
----
Il servizio é svolto a scopo di studio, le informazioni non sono pubblicamente accessibili nonostante l'azienda sia pubblica.
