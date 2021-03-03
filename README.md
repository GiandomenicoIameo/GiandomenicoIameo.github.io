Introduzione alla libreria stdlist.c
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

Qui di seguito, e' mostrato un esempio della funzione di inserimento
di un elemento in testa a una lista.

Funzione push()
-------------

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

 >**Nota :** 
 >
 >Ogni funzione dichiarata in stdlist.c non fa parte della **libreria standard del C**. Essa e'
 >stata distribuita nella speranza di essere utile ma **senza alcuna garanzia**.

 Per maggiori dettagli visitare la repository **[ library ]( https://github.com/GiandomenicoIameo/library )** su **github**.
