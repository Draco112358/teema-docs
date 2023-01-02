# ESymIA Docs <!-- omit in toc -->

- [**Scopo**](#scopo)
- [**Panoramica dell'architettura**](#panoramica-dellarchitettura)
- [**Funzionalità**](#funzionalità)
  - [**Progetti di simulazione**](#progetti-di-simulazione)
    - [**Modeler**](#modeler)
    - [**Physics**](#physics)
      - [**Porte**](#porte)
      - [**Segnali**](#segnali)
    - [**Simulator**](#simulator)
      - [**Meshing**](#meshing)
    - [**Results**](#results)
  - [**Storage utente**](#storage-utente)
    - [**Condivisione progetti e cartelle**](#condivisione-progetti-e-cartelle)


## **Scopo**
ESymIA è un'applicazione per la simulazione delle caratteristiche elettriche/elettroniche di modelli 3D, basandosi su metodologie FEM.

## **Panoramica dell'architettura**

Vediamo innanzitutto uno schema di massima dell'architettura di CADmIA, con esempi di relazioni tra i vari strati per alcune funzionalità specifiche.<br>
![esymia_architecture](imgs/esymia_arch.png)<br>
L'applicazione è basata su due tecnologie prinicipali lato client:
- *ReactJS*, per lo sviluppo dell'interfaccia;
- *ThreeJS*, per la rappresentazione dei modelli 3D.

Per quanto riguarda la parte server, invece, ne sfrutta essenzialmente tre:
- *Auth0*, per le procedure di autenticazione e gestione degli utenti;
- *Fauna*, per la gestione dei dati dell'app, con le relative politiche di accesso ad essi da parte degli utenti;
- *AWS*, utilizzato come storage per i modelli salvati, che possono arrivare a dimensioni considerevoli, non gestibili direttamente tramite Fauna.<br>

## **Funzionalità**

ESymIA è tutta incentrata sulla simulazione delle caratteristiche elettriche/elettroniche di modelli 3D. Tutte le sue funzionalità ruotano essenzialmente attorno a questo.
In particolare il flusso di esecuzione di una simulazione si sviluppa in 4 step consecutivi:
- *Modeler*, dove andiamo ad importare il modello da testare;
- *Physics*, nel quale aggiungiamo al modello le informazioni necessarie alla simulazione;
- *Simulator*, nel quale andiamo ad eseguire l'operazione di meshing.
- *Results*, dove visualizzeremo i risultati dei calcoli di simulazione.

Torneremo in dettaglio su ognuno di essi nelle prossime sezioni.

### **Progetti di simulazione**

Il processo di simulazione è interamente racchiuso all'interno di un progetto. Per cui la prima cosa da fare un volta autenticati, sarà quella di aprirne uno.<br>
Per far questo, a partire dalla dashboard (vedi la figura sottostante), abbiamo tre opzioni disponibili:
- creare un nuovo progetto tramite la voce *New Project*: ci verrà chiesto di inserire un nome per esso, oltre ad una descrizione opzionale;
- proseguire con un progetto salvato in locale, importandolo tramite *Import Project*;
- proseguire con un progetto esistente tra quelli salvati sul database, che possiamo vedere in parte listati nella sezione *My Recent Projects*, oppure in forma completa nella scheda *Projects* del menu principale della dashboard.

![dashboard](imgs/dashboard.png)

Sempre nella dashboard, inoltre, si ha a disposizione una lista delle ultime simulazioni effettuate, dalla quale è possibile andare a visualizzarne direttamente i risultati.
Per una lista completa delle simulazioni effettuate, si può invece far riferimento alla voce *Simulations* del menu principale della dashboard.

#### **Modeler**

![modeler](imgs/modeler.png)

#### **Physics**

![physics](imgs/physics.png)

##### **Porte**

##### **Segnali**

![signal_details](imgs/signal_details.png)

#### **Simulator**

![meshing](imgs/mesh_sim.png)

##### **Meshing**

#### **Results**

![results](imgs/results.png)

### **Storage utente**

![drive](imgs/drive.png)

#### **Condivisione progetti e cartelle**
