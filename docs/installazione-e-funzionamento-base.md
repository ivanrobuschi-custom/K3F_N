# Installazione e Funzionamento Base

## 4 INSTALLAZIONE

### 4.1 Fissaggio a parete

**K3-N STD**

Il dispositivo è dotato di doppia predisposizione per il fissaggio verticale della macchina:
* Predisposizione 1: tre fori filettati per il fissaggio mediante viti M4.
* Predisposizione 2: tre asole per il montaggio su perni.

Entrambe le predisposizioni sono posizionate nella parte inferiore della macchina (vedere figura seguente). Le dimensioni riportate nell’immagine sono espresse in millimetri.

**Indicazioni per il fissaggio a parete mediante viti M4**

Forare il pannello di fissaggio rispettando le misure indicate nella pagina precedente. Prestare attenzione alla lunghezza delle viti utilizzate.

La lunghezza della vite (L) dovrà essere calcolata in base allo spessore del pannello (SP) su cui viene fissato il dispositivo nel seguente modo:
`L ≤ 6 mm + SP`

Ad esempio, se lo spessore del pannello è 10 mm (SP = 10 mm), la lunghezza massima della vite sarà 16 mm.

**Indicazioni per il fissaggio a parete su perni**

Fissare alla parete 3 perni di fissaggio rispettando le misure indicate nella pagina precedente. Le dimensioni dei perni di fissaggio sono fornite di seguito. Le dimensioni riportate nell’immagine sono espresse in millimetri.
* Perni con diametro Ø4 (tolleranza 0 / -0.5) e Ø7 (tolleranza 0 / -1), con una sporgenza di 2.5mm (tolleranza +1 / 0).

**Montaggio**

1.  Premere il pulsante di sgancio e rimuovere il coperchio frontale.
2.  Capovolgere il dispositivo e svitare le 2 viti di fissaggio A. Rimuovere la base B del dispositivo sfilandola dalle sedi nella direzione indicata in figura.
3.  Premere il pulsante di servizio C e aprire il coperchio del dispositivo D.
4.  Tirare la parte inferiore della paratia E. Ruotare la parte posteriore per sganciarla dalle sedi sul telaio.
5.  Rimuovere la colla dal cablaggio del sensore quasi fine carta con un cacciavite, facendo attenzione a non danneggiare il cavo.
6.  Tirare la parte inferiore della paratia F. Ruotare la parte posteriore per sganciarla dalle sedi sul telaio.
7.  Ruotare il selettore che regola il carico sulla molla di richiamo del coperchio nella posizione G servendosi di una moneta.
8.  Svitare la vite di fissaggio e rimuovere il sensore quasi fine carta dalla posizione di montaggio P1.
9.  Posizionare il sensore quasi fine carta nella posizione di montaggio P2 e avvitare la vite di fissaggio.
10. Inclinare la paratia F e inserire la prima spina nella sua sede sul telaio. Premere nel punto indicato per agganciare la spina.
11. Ruotare la paratia F per agganciare le altre spine al telaio.
12. Allo stesso modo, agganciare la paratia E.
13. Chiudere il coperchio del dispositivo.
14. Capovolgere il dispositivo e inserire la base B del dispositivo infilandola nelle sedi nella direzione indicata in figura. Avvitare le 2 viti di fissaggio A.
15. Rimontare il coperchio frontale.
16. Fissare il dispositivo a parete.

## 5 FUNZIONAMENTO

### 5.1 Collegamenti

La figura seguente illustra i possibili collegamenti del dispositivo.
Per configurare correttamente le porte di comunicazione utilizzare le programmazioni P902 e P910.
Per il pinout dei connettori fare riferimento al manuale assistenza.
Per sapere quali cavi sono inclusi nell’imballo del dispositivo, fare riferimento al paragrafo 3.1 mentre per sapere quali cavi sono previsti come accessori fare riferimento al capitolo 8.
Quando i cavi di comunicazione seriale e USB sono collegati al dispositivo contemporaneamente (escluso il collegamento al cassetto rendiresto), la comunicazione avviene attraverso la porta USB.

**Connessioni illustrate nel diagramma:**
*   **DISPLAY ESTERNO**: Cavo collegamento in dotazione con il display
*   **HUB**: Cavo Ethernet UTP standard (pin-to-pin)
*   **TERMINALE EFT/POS**: Cavo collegamento terminale EFT/POS RJ45/DB9 (opzionale)
*   **ALIMENTAZIONE**: Cavo collegamento in dotazione con il cassetto rendiresto
*   **CASSETTO RENDIRESTO**: Cavo collegamento in dotazione con il cassetto rendiresto
*   **PC**: Cavo collegamento PC RJ45/DB9, Cavo USB tipo A/B, Cavo Ethernet CrossOver standard

### 5.2 Collegamento del lettore di codici a barre SCANMATIC

Al dispositivo è possibile collegare un lettore di codici a barre (lettore barcode) fornito come accessorio (vedere capitolo 8) in grado di leggere svariati tipi di codici a barre.

**NOTA:**
I lettori di codici a barre SCANMATIC non necessitano di particolari impostazioni per poter funzionare con il dispositivo.

Per i cavi di collegamento del lettore di codici a barre, fare riferimento alla lista accessori (vedere capitolo 8).
Per installare il lettore di codici a barre procedere come segue:
*   Collegare il lettore di codici a barre alla porta seriale RS232 (è possibile utilizzare un cavo adattatore seriale, vedere la figura seguente).
*   Configurare la porta di comunicazione attraverso la programmazione P902.
*   Selezionare la voce “DEVICE” ed impostare “BARCODE SCANNER” e confermare la selezione.
*   Configurare i parametri di comunicazione del dispositivo attraverso la programmazione P910 come indicato nella tabella seguente.

| IMPOSTAZIONI CONSIGLIATE DISPOSITIVO | |
| :----------------------------------- | :--- |
| Baudrate:                            | 9600 |
| Bit number:                          | 8, NONE, 1 |

### 5.3 Preparazione del sistema pilotato da PC

Per pilotare il sistema attraverso un PC, procedere come illustrato di seguito.
Per sapere quali cavi sono inclusi nell’imballo del dispositivo, fare riferimento al paragrafo 3.1.

1.  **Collegare il dispositivo ad un PC** mediante una delle porte disponibili (RS232, USB, Ethernet).
2.  **Configurare opportunamente i parametri di comunicazione.**
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "PROGRAMMAZIONE".
    *   Accedere alla programmazione `PARAMETRI DI COMUNICAZIONE` digitando `910` e premere `SUBTOTALE`.
    *   Configurare i parametri di comunicazione.
3.  **Abilitare la modalità FPU (controllo da PC).**
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "REGISTRAZIONE".
    *   Digitare `222` e premere `CHIAVE`.
    *   Selezionare `FPU` e confermare.

**NOTA:**
È possibile attivare la funzione “Modo FPU” attraverso la programmazione P910. Disabilitando questa funzione il dispositivo potrà passare dal funzionamento con tastiera a quello mediante protocollo di comunicazione (o viceversa) automaticamente.

### 5.4 Preparazione del sistema pilotato con tastiera e display

**K3-N STD**

Se si intende utilizzare il dispositivo unitamente ad una tastiera e ad un display, seguire le istruzioni fornite nel foglio di montaggio presente nell’imballo della tastiera altrimenti seguire lo schema illustrato di seguito.
Gli accessori descritti in questo paragrafo (display e tastiere) sono componenti da ordinare separatamente (vedere anche capitolo 8).

**Connessioni illustrate nel diagramma:**
*   La tastiera si collega alla porta `DK`.
*   I display esterni (QD, QD2, XD) si collegano alla porta `Display` tramite cavi adattatori (opzionali).

### 5.5 Servizi via Ethernet

Il dispositivo può essere collegato direttamente ad un PC oppure ad un hub di rete mediante cavo Ethernet (vedere paragrafo 5.3) per sfruttare gli esclusivi servizi di cui è dotato.
Per utilizzare uno dei servizi disponibili è necessario configurare correttamente le impostazioni di rete del dispositivo.

**Servizi via Ethernet:**
*   **HTTP**: Web server locale contenente le informazioni principali relative al dispositivo.
*   **HTTPS**: Aggiornamento da remoto e servizi telematici.
*   **TCP**: Gestione del dispositivo mediante protocollo di comunicazione (Assetto Programmazione (P911)).
*   **WEB SERVICES**: Utilizzo del dispositivo mediante POST XML REQUEST.

### 5.6 Accensione e spegnimento

Per accendere o spegnere il dispositivo procedere come segue:

1.  **Collegare l’adattatore di rete** in dotazione al dispositivo e alla presa di rete. Utilizzare il tipo di alimentazione elettrica indicato sull’etichetta del dispositivo.
2.  **Accendere il dispositivo** premendo il tasto **ON/OFF**, gli indicatori luminosi si accendono ed il dispositivo è pronto.
    **Spegnere il dispositivo** premendo il tasto **ON/OFF**.

**NOTA:**
Per poter variare i parametri relativi alle caratteristiche del dispositivo, vedere la programmazione P018.

### 5.7 Apertura coperchio

Mantenere premuto il tasto **OPEN** per aprire il coperchio del dispositivo, oppure in caso di anomalie premere il pulsante di servizio.

### 5.8 Caricamento del rotolo carta

Per il caricamento della carta procedere seguendo le istruzioni fornite di seguito. Ad ogni cambio carta ispezionare l’interno del dispositivo.

**ATTENZIONE:**
Utilizzare solo rotoli di carta omologati.

1.  Dopo l’accensione del dispositivo, la condizione di carta mancante viene evidenziata mediante un segnale acustico ed un messaggio sul visore.
2.  Aprire il coperchio del dispositivo, inserire il rotolo nel vano carta e far uscire la carta per alcuni centimetri.
3.  Chiudere il coperchio del dispositivo ed attendere il caricamento automatico ed il taglio della carta.

### 5.9 Abbinamento con dispositivi Bluetooth

**K3-N BT**

Per le impostazioni della programmazione P913, nonché delle programmazioni P902, e P912, fare riferimento ai paragrafi successivi.

**NOTA:**
Le immagini delle finestre utilizzate in questo paragrafo potrebbero essere differenti dalle schermate che compaiono sui dispositivi utilizzati per la stampa, in quanto dipendenti dalla versione di sistema operativo.

**Windows**

1.  Premere il tasto di accensione del dispositivo.
2.  Accedere alla programmazione P913.
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "PROGRAMMAZIONE".
    *   Digitare `913` e premere `SUBTOTALE`.
3.  Abilitare il Bluetooth usando le frecce di selezione.
4.  Confermare la selezione premendo `SUBTOTALE`.
5.  Sulla barra di stato del PC cliccare sull’icona Bluetooth.
6.  Accedere nuovamente alla programmazione P913 affinché il dispositivo sia visibile.
7.  Nella finestra visualizzata cliccare su “Aggiungi dispositivo”.
8.  Cliccare sul tasto “Avanti”.
9.  Nell'elenco dei dispositivi proposti individuare il vostro dispositivo (`<dispositivo_BT ADDRESS>`), selezionarlo con un click e cliccare sul tasto “Avanti”.
10. Nel messaggio di conferma che viene visualizzato cliccare “Dispositivi e stampanti”.
11. Verificare che il vostro dispositivo figuri nell'elenco dei dispositivi abbinati.
12. Uscire dalla programmazione P913 premendo `CONTANTE`.

**NOTA:**
Una volta che è avvenuto l’abbinamento (pairing) tra host e dispositivo, questo rimane attivo anche in caso di spegnimento, interruzione della comunicazione, ecc.

**macOS**

1.  Premere il tasto di accensione del dispositivo.
2.  Accedere alla programmazione P913.
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "PROGRAMMAZIONE".
    *   Digitare `913` e premere `SUBTOTALE`.
3.  Abilitare il Bluetooth usando le frecce di selezione.
4.  Confermare la selezione premendo `SUBTOTALE`.
5.  Accedere nuovamente alla programmazione P913 affinché il dispositivo sia visibile.
6.  Sulla barra di stato del PC cliccare sull’icona Bluetooth.
7.  Nel menù a tendina cliccare “Apri preferenze Bluetooth”.
8.  Cliccare il tasto “Abbina” per confermare.
9.  Verificare che il vostro dispositivo figuri nell'elenco dei dispositivi abbinati.
10. Uscire dalla programmazione P913 premendo `CONTANTE`.

**NOTA:**
Una volta che è avvenuto l’abbinamento (pairing) tra host e dispositivo, questo rimane attivo anche in caso di spegnimento, interruzione della comunicazione, ecc.

**Linux**

1.  Premere il tasto di accensione del dispositivo.
2.  Accedere alla programmazione P913.
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "PROGRAMMAZIONE".
    *   Digitare `913` e premere `SUBTOTALE`.
3.  Abilitare il Bluetooth usando le frecce di selezione.
4.  Confermare la selezione premendo `SUBTOTALE`.
5.  Accedere nuovamente alla programmazione P913 affinché il dispositivo sia visibile.
6.  Sulla barra di stato del PC cliccare sull’icona Bluetooth.
7.  Nel menù a tendina cliccare “Dispositivi”.
8.  Nell'elenco dei dispositivi proposti individuare il vostro dispositivo (`<dispositivo_BT ADDRESS>`) e selezionarlo con un click.
9.  Nel menù a tendina cliccare “Associa”.
10. Verificare che il vostro dispositivo figuri nell'elenco dei dispositivi abbinati.
11. Uscire dalla programmazione P913 premendo `CONTANTE`.

**NOTA:**
Una volta che è avvenuto l’abbinamento (pairing) tra host e dispositivo, questo rimane attivo anche in caso di spegnimento, interruzione della comunicazione, ecc.

**Android**

1.  Premere il tasto di accensione del dispositivo.
2.  Accedere alla programmazione P913.
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "PROGRAMMAZIONE".
    *   Digitare `913` e premere `SUBTOTALE`.
3.  Abilitare il Bluetooth usando le frecce di selezione.
4.  Confermare la selezione premendo `SUBTOTALE`.
5.  Accedere nuovamente alla programmazione P913 affinché il dispositivo sia visibile.
6.  Sul dispositivo Android premere l’icona “Impostazioni” per aprire il menù.
7.  Premere sull’icona “Bluetooth”.
8.  Spostare lo switch su ON per attivare la comunicazione Bluetooth e avviare la ricerca dei dispositivi disponibili.
9.  Nell'elenco dei dispositivi proposti individuare il vostro dispositivo (`<dispositivo_BT ADDRESS>`) e selezionarlo con un click.
10. Una volta eseguita l’associazione non disattivare la comunicazione Bluetooth. In quel caso la comunicazione viene interrotta.
11. Uscire dalla programmazione P913 premendo `CONTANTE`.

**iOS**

1.  Premere il tasto di accensione del dispositivo.
2.  Accedere alla programmazione P913.
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "PROGRAMMAZIONE".
    *   Digitare `913` e premere `SUBTOTALE`.
3.  Abilitare il Bluetooth usando le frecce di selezione.
4.  Confermare la selezione premendo `SUBTOTALE`.
5.  Accedere nuovamente alla programmazione P913 affinché il dispositivo sia visibile.
6.  Sul dispositivo iOS premere l’icona “Impostazioni” per aprire il menù.
7.  Premere sull’icona “Bluetooth”.
8.  Spostare lo switch su ON per attivare la comunicazione Bluetooth e avviare la ricerca dei dispositivi disponibili.
9.  Nell'elenco dei dispositivi proposti individuare il vostro dispositivo (`<dispositivo_BT ADDRESS>`) e selezionarlo con un click.
10. Una volta eseguita l’associazione non disattivare la comunicazione Bluetooth. In quel caso la comunicazione viene interrotta.
11. Uscire dalla programmazione P913 premendo `CONTANTE`.

**Windows Phone**

1.  Premere il tasto di accensione del dispositivo.
2.  Accedere alla programmazione P913.
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "PROGRAMMAZIONE".
    *   Digitare `913` e premere `SUBTOTALE`.
3.  Abilitare il Bluetooth usando le frecce di selezione.
4.  Confermare la selezione premendo `SUBTOTALE`.
5.  Accedere nuovamente alla programmazione P913 affinché il dispositivo sia visibile.
6.  Sul dispositivo Windows premere l’icona “Impostazioni” per aprire il menù.
7.  Premere sull’icona “Bluetooth”.
8.  Spostare lo switch su ON per attivare la comunicazione Bluetooth e avviare la ricerca dei dispositivi disponibili.
9.  Nell'elenco dei dispositivi proposti individuare il vostro dispositivo (`<dispositivo_BT ADDRESS>`) e selezionarlo con un click.
10. Una volta eseguita l’associazione non disattivare la comunicazione Bluetooth. In quel caso la comunicazione viene interrotta.
11. Uscire dalla programmazione P913 premendo `CONTANTE`.

### 5.10 Abbinamento con dispositivi Wi-Fi

**K3-N WI-FI**

Per le impostazioni della programmazione P912, nonché delle programmazioni P902, e P913, fare riferimento ai paragrafi successivi.

1.  Premere il tasto di accensione del dispositivo.
2.  Accedere alla programmazione P912.
    *   Premere ripetutamente il tasto `CHIAVE` fino a che sul display comparirà il messaggio o l'icona corrispondente all'assetto "PROGRAMMAZIONE".
    *   Digitare `912` e premere `SUBTOTALE`.
3.  Abilitare il Wi-Fi usando le frecce di selezione.
4.  Confermare la selezione premendo `SUBTOTALE`.
5.  Configurare opportunamente i parametri di comunicazione.
    *   Utilizzare le frecce di selezione per navigare tra i parametri e `SUBTOTALE` per confermare le modifiche.
