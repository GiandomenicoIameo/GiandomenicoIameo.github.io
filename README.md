Libreria stdlist.c
===================

----------

Ogni programma scritto nel linguaggio C contiene tipicamente
riferimenti a funzioni definite altrove, come le librerie standard
o nelle librerie private. Un esempio e' stdlist.c.

Insieme alla libreria vengono inoltre forniti gli **header 
file**, file di testo che permettono al programmatore di utilizzare 
lo specifico insieme di funzioni della libreria ad esse associate.

Il file contiene alcune delle piu' importanti funzioni riguardo
alle **liste semplicemente concatenate**. Ogni funzione dichiarata e' 
stata studiata nel minimo dettaglio per garantire, a chi le utilizza, 
prestazioni efficienti in relazione al **tempo** e allo **spazio** utilizzato.

Funzione allocate :
----------

```
struct elem *allocate( int key ) {

  struct elem *node;

  node = ( struct elem* )malloc( sizeof( struct elem ) );
  if( !node ) return node;

  node->data = key;
  node->next = NULL;

  return node;
}
```

Descrizione :
----------

Creare e mantenere strutture dinamiche di dati che possono crescere e ridursi durante
l'esecuzione del programma richiede l'**allocazione dinamica della memoria**, ossia la 
capacita', da parte del programma, di _ottenere un maggiore spazio di memoria in run-time_,
così da contenere nuovi nodi. 
La funzione ha lo scopo proprio di allocare memoria per i nuovi nodi e inizializzare i membri
della struttura.

 Per maggiori dettagli visitare la repository **[ library ]( https://github.com/GiandomenicoIameo/library )** su **github**.
