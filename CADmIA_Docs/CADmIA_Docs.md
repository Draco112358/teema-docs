# CADmIA Docs <!-- omit in toc -->
### Versione 0.0.1 <!-- omit in toc -->
- [**Scopo**](#scopo)
- [**Panoramica dell'architettura**](#panoramica-dellarchitettura)
- [**Funzionalità**](#funzionalità)
  - [**Modelli base**](#modelli-base)
  - [**Movimenti**](#movimenti)
    - [**Spostamenti di precisione tramite SideBar**](#spostamenti-di-precisione-tramite-sidebar)
  - [**Composizione con operazioni binarie**](#composizione-con-operazioni-binarie)
  - [**Clone**](#clone)
  - [**Materiali**](#materiali)
  - [**Import**](#import)
  - [**Export**](#export)

## **Scopo**
CADmIA è un'applicazione per la creazione di modelli 3D.
Nata inizialmente per la modellazione in ambito elettrico/elettronico, ha acquisito poi una sua indipendenza, slegandosi da specifici domini applicativi.
Tramite una serie di componenti base (in futuro estendibili) componibili, si può arrivare a creare modelli anche di elevata complessità.

## **Panoramica dell'architettura**

## **Funzionalità**
### **Modelli base**
Allo stato attuale, sono disponibili 5 modelli di base (vedi immagine seguente), ognuno con caratteristiche specifiche regolabili dalla SideBar:
- *cubo*, con altezza, larghezza, profondità.
- *sfera*, caratterizzata dal suo raggio.
- *cilindro*, con altezza e raggi di base regolabili singolarmente. In tal modo è molto semplice ottenere ad esempio dei tronchi di cono.
- *toro*, definito da un raggio del toro che va dal centro dell'oggetto fino al centro del tubo, un raggio del tubo, che determina lo spessore della ciambella.
- *cono*, con altezza e raggio di base.

![modelli_base](imgs/base_components.png)
Ognuno di essi ha poi degli attributi riguardanti il numero di segmenti da utilizzare per rappresentare le varie superfici che lo compongono. Questi non riguardano le proprietà geometriche degli oggetti, ma la loro rappresentazione in ThreeJS, che li vede come Mesh, quindi composizioni di unità più piccole. Quanto più grande è il numero di segmenti impostato per le superfici di un oggetto, tanto maggiiore sarà il suo livello di dettaglio, tanto più onerosa sarà la sua rappresentazione.
Sta quindi all'utente scegliere il giusto compromesso tra prestazioni e precisione richiesta.

#### *Esempio* <!-- omit in toc -->
il cilindro in ThreeJS è in realtà un prisma di cui è possibile regolare il numero di segmenti radiali. In sostanza, il profilo curvo è approssimato con delle spezzate, pertanto più è alto il numero di segmenti radiali, migliore sarà l'approssimazione del prisma verso un cilindro.

Dall'esempio si intuisce anche come, tramite questi attributi aggiuntivi, sia possibile ottenere altre forme geometriche: se infatti volessimo un prisma a base pentagonale, ci baseterebbe prendere il cilindro come elemento base ed impostargli un numero di segmenti radiali pari a 5.
Allo stesso modo se volessimo una piramide a base quadrata, potremmo partire da un cono ed impostare il numero di segmenti radiali a 4.
### **Movimenti**
![movimenti](imgs/movements.png)
#### **Spostamenti di precisione tramite SideBar**
![spostamenti_accurati](imgs/accurate_movements.png)
### **Composizione con operazioni binarie**
![bynary_ops](imgs/bynary_ops.png)
### **Clone**
### **Materiali**
### **Import**
### **Export**