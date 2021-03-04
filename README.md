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
  vengono fatte _solo all'inizio_ ( indicato con **head** ) di una coda.

Ricordate che una _struttura autoreferenziale_ contiene un membro puntatore
che punta a una struttura dello stesso tipo. La definizione delle strutture
e' la seguente :

```
// Struttura del nodo
struct elem {
    int data;
    struct elem *next;
};

// Struttura coda
struct equeue {
    struct elem *top;
    struct elem *end;
};
```

E' possibile notare che la definizione della struttura dati coda anziché
memorizzare un solo puntatore ne' memorizza due.
In questo modo la struttura sarà in grado di conservare sia
un puntatore alla testa che al nodo terminale.
Di conseguenza, questo comporterà un enorme vantaggio per quanto riguarda
l'inserimento e la cancellazione di un nodo.

Le liste collegate :
----------

Una **lista** è una **struttura dati ricorsiva**
(formata da elementi dello stesso tipo e collegati insieme) la
cui lunghezza può variare dinamicamente.

I suoi elementi sono variabili dinamiche e vengono creati e/o
distrutti a tempo di esecuzione producendo una struttura
dati che cresce o diminuisce a seconda delle esigenze del
programma in esecuzione.

È possibile implementare liste anche tramite array, ma ciò
può avvenire solo quando si conoscono esattamente le
dimensioni della lista.

La definizione di una struttura concatenata è di solito accompagnata da
un certo numero di funzioni, che hanno il compito di gestirla, cioè
eseguire le operazioni di **inserimento**, di **eliminazione** e di **ricerca** di
oggetti.

Ogni lista è definita da una variabile puntatore
che punta al primo elemento della lista.
Nel caso di assenza di elementi (lista vuota) tale
variabile puntatore assume valore **NULL**.
In una lista il campo puntatore dell’ultimo elemento
assume sempre valore **NULL**, per convenzione, per
segnare la _fine_ della lista.

Allocazione dinamica di liste :
----------

La creazione di un nuovo nodo ( in qualunque fase dell’esistenza
di una lista ) avviene creando una nuova istanza della struttura
tramite allocazione dinamica, ossia la capacità da parte di un
programma, di _ottenere maggior spazio in memoria al tempo
dell'esecuzione_.
Le funzioni **malloc** e **free** e **sizeof** sono essenziali
per l'allocazione dinamica.

Creazione della lista :
----------

Per creare una lista, basta definirla, ovvero è sufficiente
creare il modo di riferirsi ad essa.



`$$\forall  a \big(  \space \big\{ a, a \big\} =  \big\{a\big\} \space \big )$$`

> E' bene ricordare che una lista e' un insieme e quindi per
> definizione $$ \forall  a \big(  \space \big\{ a, a \big\} =  \big\{a\big\} \space \big) $$,
> dunque ogni elemento $$ a \in L $$, dove $$ L $$ e' la nostra lista, sarà
> distinto da ogni altro.

La coda :
----------

Esistono due approcci per implementare una struttura dati di tipo coda in C :

- Code con **capacita illimitata** – struttura dati di tipo lista concatenata.
- Code con **capacita limitata** – implementazione ad-hoc tramite array.

Come abbiamo fatto notare in precedenza attraverso le due definizioni, una
struttura dati di tipo coda può essere vista come una struttura dati di tipo
lista che supporta un numero limitato di operazioni :

- **Enqueue** – inserimento in coda.
- **Dequeue** – rimozione in testa.

Creazione della coda :
----------

Per creare una coda, basta definirla, ovvero è sufficiente
creare il modo di riferirsi a essa.
L’unica cosa che esiste sempre della coda è il suo **punto di
accesso** ( o radice ).
Questa è l’unica componente **allocata staticamente** e
all’inizio i puntatori **top** e **end** sono inizializzati a **NULL**, in
quanto non ci sono elementi.

```
int main( void ) {

  struct equeue coda;

  coda.top = NULL;
  coda.end = NULL;

  ...

  return 0;
}
```

Inserimento e cancellazione di un nodo :
----------

L'operazione di inserimento di un elemento nella struttura dati
coda viene gestita come un inserimento in coda ad una lista.

Come fase preliminare, il nodo viene creato attraverso la funzione
allocate(), vengono inizializzati i vari campi della struttura e infine
viene restituito un puntatore al nodo.

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


Per maggiori dettagli visitare la repository **[ library ]( https://github.com/GiandomenicoIameo/library )** su **github**.
