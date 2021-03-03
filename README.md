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


Strutture dati :
----------

Il file header ( stdlist.h ) introduce le **strutture dati dinamiche** che
possono crescere e ridursi al momento dell'esecuzione.

- Le **liste collegate** sono collezioni di dati "allineati in una riga".
 In una lista collegata le inserzioni e le cancellazioni vengono fatte
 ovunque.

- Lo **stack** e' un tipo di lista collegata molto importante nei sistemi
 operativi e compilatori. Le inserzioni e cancellazioni vengono fatte
 _solo a un estremo_, ovvero la sua **cima**.

- Le **code** rappresentano le linee di attesa; le inserzioni vengono fatte
  _solo alla fine_ ( indicata con **tail** ) di una coda e le rimozioni
  vengono fatte _solo all'inizio_( indicato con **head** ) di una coda.

Ricordate che una _struttura autoreferenziale_ contiene un membro puntatore
che punta a una struttura dello stesso tipo. La definizione delle strutture
e' la seguente :

```
// lista collegata
struct elem {
    int data;
    struct elem *next;
};

// coda
struct equeue {
    struct elem *top;
    struct elem *end;
};
```


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

Funzione push :
----------

```
struct elem *push( struct elem *top, struct elem *node ) {

  if( !top ) {
          top = node;
  } else {
          node->next = top;
          top = node;
  }
  return top;
}
```

Descrizione :
----------

 Per maggiori dettagli visitare la repository **[ library ]( https://github.com/GiandomenicoIameo/library )** su **github**.
