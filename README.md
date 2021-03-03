## Introduzione alla libreria stdlist.c

**Come e' possibile notare dal titolo, all'interno 
del file sono state implementate le più importanti
funzioni sulle liste semplicemente concatenate.**

**Una lista concatenata ( o linked list ) è una struttura dati 
dinamica, tra quelle fondamentali usate nella programmazione. 
Consiste di una sequenza di nodi, ognuno contenente campi di 
dati arbitrari e uno o due riferimenti ( "link" ) che puntano 
al nodo successivo e/o precedente. Una lista concatenata è un 
tipo di dato auto-referente, in quanto contiene un puntatore 
ad un altro dato dello stesso tipo.**

**Ogni funzione dichiarata nel file e' stata studiata nel minimo
dettaglio per garantire, a chi le utilizza, prestazioni efficienti.**

**Qui di seguito, e' mostrato un esempio della funzione di inserimento
in testa.**

### Funzione push()

```markdown
   
 struct elem *push( \*struct*\ elem *top, struct elem *node ) {
           
   if( !top ) {
           top = node;
   } else {
           node->next = top;
           top = node;
   }
   return top;
 }
```

**Per maggiori dettagli visitare la repository [ library ]( https://github.com/GiandomenicoIameo/library ) su github.**
