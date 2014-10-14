Treni Italia
========

Dati dal sito Viaggiatreno e qualche appunto.

Elenco Stazioni
---------------
GET all'url
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/autocompletaStazione/[stringa]

Risposta testuale separata dal carattere di pipe (|)

Vedi stazioni.tsv per un dump

Dettagli Stazione
-----------------
Trova la regione di appartenenza (esempio Oristano)
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/regione/S12878 (risultato = 20)

Dettagli per la stazione di Oristano
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/dettaglioStazione/S12878/20
(codice_stazione/regione)

Vedi stazioni_coord.tsv per un dump contenente le coordinate, e stazioni_coord.geojson per la conversione (effettuata con geojson.io).

Dettagli viaggio
----------------
Elenco stazioni con stato per ognuna
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/tratteCanvas/[codPartenza]/[codTreno]
dove:
- codPartenza è il codice trenitalia della stazione di partenza del treno
- codTreno è il codice del treno che parte dalla stazione richiesta
(se si vuole sapere lo status del treno 666 a Brignole, richiedere La Spezia Centrale (S06000) più il treno (666)

Meteo
-------
http://www.viaggiatreno.it/viaggiatrenonew/resteasy/viaggiatreno/datimeteo/0

0 richiede per tutta Italia, altrimenti usare l'id della Regione (funziona solo per certe stazioni)


Authors
-------
@sabas
@marcobra

Nota
----
Il servizio é svolto a scopo di studio, le informazioni sono riservate nonostante l'azienda sia pubblica.