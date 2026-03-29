# Servizi Telematici e Lotterie

# SERVIZI TELEMATICI

## 13.1 Gestione disallineamenti

Nel caso in cui si verifichi un disallineamento tra lo stato del registratore telematico risultante sul portale dell'Agenzia delle Entrate e quello sul dispositivo locale (ricevendo il codice errore 200 a seguito dell’invio del file dei corrispettivi giornalieri), il registratore telematico recupera l’informazione sullo stato del dispositivo presente sul portale e, in caso di disallineamento, non emette documenti commerciali fino all’avvenuto riallineamento degli stati.

Questa funzione è necessaria in quanto se il cambio di stato del dispositivo viene eseguito solo sul portale dell'Agenzia delle Entrate, si produce un disallineamento con lo stato locale del registratore telematico il quale non è in grado di allinearsi da solo con l’informazione presente sul portale. Il servizio quindi consente al dispositivo di conoscere il disallineamento e comportarsi di conseguenza.

In questa situazione di disallineamento il dispositivo, tramite un messaggio sul display e sulla stampante, avvisa l’esercente dello stato di blocco e della necessità di intervento di un tecnico abilitato per ripristinare il corretto funzionamento.

## 13.2 Messaggistica

Il servizio di messaggistica del registratore telematico verifica se ci sono messaggi prodotti dall’Agenzia delle Entrate ed in caso affermativo il dispositivo riceve in risposta un codice a cui è associato un messaggio di alert predefinito che viene memorizzato nella memoria permanente di riepilogo, visualizzato sul display e stampato su un documento gestionale.

Lo stesso messaggio di alert viene riproposto nel documento di chiusura giornaliera fino a quando non viene effettuato un intervento da parte di un tecnico autorizzato che lo può disattivare.

La seguente tabella offre una visione d'insieme dei codici di messaggi che possono essere ricevuti dal registratore telematico, nonché una spiegazione del messaggio di alert:

| CODICE MESSAGGIO | TESTO STAMPATO               | TESTO VISUALIZZATO | CONDIZIONE BLOCCANTE                               |
| :--------------- | :--------------------------- | :----------------- | :------------------------------------------------- |
| 1                | Firmware non conforme        | FW NON CONFORME    | No                                                 |
| 2                | Ultimo intervento tecnico effettuato da un tecnico non riconosciuto | TEC. NON RICONOSC. | No                                                 |
| 3                | Firmware non conforme        | FW NON CONFORME    | Sì (dalla data ggmmaaaa il dispositivo sarà bloccato) |

In tutti i casi sopra citati si raccomanda di rivolgersi ad un tecnico abilitato per ripristinare il corretto funzionamento del dispositivo.

## 13.3 Periodo inattivo

Dopo ogni chiusura fiscale il dispositivo effettua la trasmissione telematica dei corrispettivi all’Agenzia delle Entrate tramite l’invio di un file XML. Nei periodi di prolungata inattività, quando cioè il dispositivo rimane spento ed intercorrono più di 24 ore dall’ultima trasmissione telematica, il dispositivo impone, all’accensione, l’esecuzione di una chiusura fiscale con conseguente invio dei corrispettivi a zero del periodo compreso tra l’ultima chiusura e il momento dell’accensione.

Di seguito è indicata la sequenza completa del comportamento del dispositivo dopo un periodo di inattività, nonché la procedura di invio dei corrispettivi.

*   Accendere il dispositivo.
*   Il dispositivo rileva un lasso di tempo superiore alle 24 ore dall’ultimo invio.
*   Viene stampato il seguente documento gestionale:

    ```
    DOCUMENTO GESTIONALE
    ────────────────────────────────────
    ATTENZIONE!
    ESEGUIRE CHIUSURA
    PER SEGNALARE
    PERIODO INATTIVO
    DAL: <GG/MM/AA>
    A: <GG/MM/AA>
    <data> <ora> <#DOC. GES.>
    NUMERO DI MATRICOLA: <matr. fiscale>
    DOCUMENTO GESTIONALE
    ```
*   Sul display viene visualizzato:

    ```
    ATTESA CONFERMA...
    <TOTALE> / <FEED>
    ```
*   Premere il tasto **INVIO** per avviare la procedura di invio corrispettivi:
    *   `Invio`
*   Sul display viene visualizzato:

    ```
    INVIO CORRISPETTIVI
    IN CORSO \
    ```
    ```
    INVIO CORRISPETTIVI
    <ESITO POSITIVO> \
    ```
*   Al termine dell’invio dei corrispettivi relativi al periodo di inattività viene stampato il seguente documento gestionale:

    ```
    DOCUMENTO GESTIONALE
    ────────────────────────────────────
    TRASMISSIONE CORRISPETTIVI
    ────────────────────────────────────
    <ESITO POSITIVO>
    codice http: <#>
    codice xml: <#>
    risp: corrispettivi trasmessi
    numero Z: <#>
    idoper: <#>
    dataora http: <data> <ora>
    <data> <ora> <#DOC. GES.>
    NUMERO DI MATRICOLA: <matr. fiscale>
    DOCUMENTO GESTIONALE
    ```

**NOTE:**
Se si pensa di effettuare un periodo di inattività superiore ai 5 giorni si consiglia di comunicare all’Agenzia delle Entrate lo stato di “Fuori servizio” del dispositivo accedendo al portale Fisconline (https://telematici.agenziaentrate.gov.it) con le proprie credenziali indicando i motivi dell’inattività.
All’accensione del dispositivo verrà comunque avviata la procedura appena descritta.

La rilevazione del periodo di inattività richiede che il dispositivo venga spento e riacceso. Ovvero si presume che il periodo di inattività corrisponda al periodo durante il quale il dispositivo resta spento. In tal caso, alla riaccensione, si determina la rilevazione e viene richiesto di completare la sequenza descritta in questo paragrafo.

Nel caso in cui al periodo di inattività non corrispondesse lo spegnimento (e la successiva riaccensione), il dispositivo opera normalmente fino alla successiva chiusura disposta dall’utente, con la formazione dei corrispettivi totalizzati per tutto il periodo trascorso dall’ultima chiusura.

## 13.4 Verifica connessioni

Il registratore telematico mette a disposizione una programmazione specifica utile a testare le connessioni di rete con i server dai quali effettuare il download del firmware aggiornato. Quando l’esito della verifica connessione è positivo, i server permettono di poter usufruire di tutte le funzionalità telematiche del dispositivo.

Procedere come segue.

*   Premere ripetutamente il tasto **CHIAVE** fino a che sul display compariranno il messaggio oppure l’icona corrispondenti all’assetto “PROGRAMMAZIONE”:
    *   `Chiave`
*   Accedere alla programmazione **VERIFICA CONNESSIONI** digitando il numero corrispondente (programmazione P698, vedere [paragrafo 12.58](#_12.58_Verifica_connessioni_(P698))):
    *   `6` `9` `8` `SubTotale`
*   Sul display viene visualizzato:

    ```
    PROGRAMMAZIONE
    698 - VERIFICA CONNESSIONI
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Viene stampato il seguente documento gestionale:

    ```
    DOCUMENTO GESTIONALE
    ────────────────────────────────────
    VERIFICA CONNESSIONI
    ────────────────────────────────────
    DHCP ABILITATO
    INDIRIZZO IP <xxx.xxx.xxx.xxx>
    MASCHERA SUBNET <xxx.xxx.xxx.xxx>
    GATEWAY <xxx.xxx.xxx.xxx>
    DNS <xxx.xxx.xxx.xxx>
    -------------------------------------
    Connessioni ai server: <ESITO POSITIVO>
    -------------------------------------
    <data> <ora> <#DOC. GES.>
    NUMERO DI MATRICOLA: <matr. fiscale>
    DOCUMENTO GESTIONALE
    ```

## 13.5 Dati telematici

Il dispositivo mette a disposizione una serie di rapporti utili per monitorare lo stato del registratore telematico, i documenti emessi e le operazioni effettuate.

*   **REPORT ID GLOBALE**: rapporto dei documenti effettuati con esito positivo o esportati.
*   **REPORT ID PER NUMERO**: rapporto dei documenti effettuati per numero (da ID n. xxxx a ID n xxxx) con esito positivo.
*   **REPORT ID PER DATA**: rapporto dei documenti effettuati per data (da <ggmmaa> a <ggmmaa>) con esito positivo.
*   **REPORT FILE SOSPESI**: rapporto dei documenti in attesa di essere inviati, falliti o esportati.
*   **REPORT PRINT Z (XML)**: rapporto di tutte le chiusure effettuate con il dettaglio dei files XML e relativi files di risposta.
*   **REPORT STATO MEMORIA DI RIEPILOGO**: rapporto dello stato della memoria permanente di riepilogo.
*   **REPORT MEMORIA DI RIEPILOGO IN XML**: creazione del file XML con il riepilogo dello stato della memoria permanente di riepilogo.
*   **REPORT MEMORIA DETTAGLIO IN XML**: creazione del file XML con il riepilogo dello stato della memoria permanente di dettaglio.
*   **REPORT BACKUP Z PER NUMERO**: rapporto di tutti i backup delle chiusure effettuate in un intervallo di numeri.
*   **REPORT BACKUP Z PER DATA**: rapporto di tutti i backup delle chiusure effettuate in un intervallo di date.
*   **REPORT PDF COPIA SCONTRINO**: ristampa elettronica (non stampa cartacea) non fiscale di un documento dematerializzato.

Procedere come segue:

*   Premere ripetutamente il tasto **CHIAVE** fino a che sul display compariranno il messaggio oppure l’icona corrispondenti all’assetto “PROGRAMMAZIONE”:
    *   `Chiave`
*   Accedere alla programmazione **SERVIZI TELEMATICI** digitando il numero corrispondente (programmazione P699, vedere [paragrafo 12.59](#_12.59_Servizi_telematici_(P699))):
    *   `6` `9` `9` `SubTotale`
*   Sul display viene visualizzato:

    ```
    PROGRAMMAZIONE
    699 - SERVIZI TELEMATICI
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “MENU ESERCENTE”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [MENU ESERCENTE]
    TIPO MENU
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “REPORT”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [REPORT]
    SELEZIONA SERVIZIO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce relativa al tipo di rapporto da stampare (es. “REPORT ID GLOBALE”):
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [REPORT ID GLOBALE]
    SELEZIONA SERVIZIO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Viene stampato il seguente documento gestionale:

    ```
    DOCUMENTO GESTIONALE
    ────────────────────────────────────
    P(699) SERVIZI TELEMATICI
    ────────────────────────────────────
    TIPO MENU: [MENU ESERCENTE]
    SELEZIONA SERVIZIO: [REPORT]
    REPORT: [REPORT ID GLOBALE]
    mmc:\XML\SENT\CORR\OK
    <DATA><ORA>_Z<XXXX>.xml <ID>
    <DATA><ORA>_Z<XXXX>.xml <ID>
    mmc:\XML\SENT\FATT\OK
    <DATA><ORA>_Z<XXXX>.xml <ID>
    <DATA><ORA>_Z<XXXX>.xml <ID>
    <data> <ora> <#DOC. GES.>
    NUMERO DI MATRICOLA: <matr. fiscale>
    DOCUMENTO GESTIONALE
    ```

## 13.6 Gestione file XML sospesi

Le procedure descritte di seguito permettono la gestione dei file XML dei corrispettivi rimasti in sospeso (ad esempio per mancata connessione alla rete) forzando manualmente l’invio o esportando il file per poi poterlo inviare.

**Invio manuale**
Procedere come segue.

*   Premere ripetutamente il tasto **CHIAVE** fino a che sul display compariranno il messaggio oppure l’icona corrispondenti all’assetto “PROGRAMMAZIONE”:
    *   `Chiave`
*   Accedere alla programmazione **SERVIZI TELEMATICI** digitando il numero corrispondente (programmazione P699, vedere [paragrafo 12.59](#_12.59_Servizi_telematici_(P699))):
    *   `6` `9` `9` `SubTotale`
*   Sul display viene visualizzato:

    ```
    PROGRAMMAZIONE
    699 - SERVIZI TELEMATICI
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “FORZA INVIO Z PEND”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [FORZA INVIO Z PEND.]
    SELEZIONA SERVIZIO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    CONFERMI? [NO]
    ```
*   Selezionare “SI” utilizzando i tasti con le frecce di selezione:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    CONFERMI? [SI]
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Viene stampato il seguente documento gestionale:

    ```
    DOCUMENTO GESTIONALE
    ────────────────────────────────────
    P(699) SERVIZI TELEMATICI
    ────────────────────────────────────
    TIPO MENU: [MENU ESERCENTE]
    SELEZIONA SERVIZIO: [FORZA INVIO Z PEND.]
    <data> <ora> <#DOC. GES.>
    NUMERO DI MATRICOLA: <matr. fiscale>
    DOCUMENTO GESTIONALE
    ```
*   Il dispositivo tenta l’invio dei corrispettivi.
*   Per verificare la presenza di corrispettivi rimasti in sospeso, stampare “Report file sospesi” (vedere [paragrafo 13.5](#_13.5_Dati_telematici)); se l’invio manuale non è andato a buon fine controllare la connessione del dispositivo alla rete e riprovare la procedura.

**Esportazione file**
Gli scontrini dematerializzati vengono salvati sul dispositivo in una particolare posizione. È possibile accedervi per poter prelevare gli scontrini di proprio interesse ed eventualmente inviarli al cliente.

Procedere come segue:

*   Collegare il dispositivo ad un PC tramite cavo USB utilizzando l’opportuna porta di comunicazione USB.
    *   `PC` `Cavo USB tipo A/B`
*   Attendere il caricamento delle unità di memorizzazione del dispositivo e accedere all’unità nominata EJ DISK.
    *   `RISORSE DEL COMPUTER`
        *   `DISPOSITIVI PORTATILI (<n>)`
            *   `<DISPOSITIVO>`
            *   `RAM-DISK`
            *   `VIRTUAL DISK`
            *   `SETUP DISK`
            *   `EJ DISK`
*   Accedere al file `<DATA><ORA>_Z<XXXX>.xml` che si desidera esportare.
    *   `EJ DISK`
        *   `XML`
            *   `SENT`
            *   `CORR`
            *   `EXPORT`
                *   `<DATA>_Z<XXXX>_N<XXXX>_<MATRICOLA>.pdf`
*   È ora possibile inviare il file XML in sospeso accedendo al portale Fisconline (https://telematici.agenziaentrate.gov.it) con le proprie credenziali, nonché all’area “Servizi per gestore ed esercente”. Caricare ed inviare il file utilizzando la funzionalità “Assenza di rete” presente nelle “Procedure di emergenza”:
    *   `Fisconline` `XML`

**NOTA:**
La funzionalità “Assenza di rete” è destinata agli esercenti che non riescono a trasmettere entro 5 giorni il file XML dei corrispettivi correttamente predisposto e sigillato elettronicamente dal dispositivo.

## 13.7 Esportazione della memoria permanente di dettaglio o riepilogo su memoria esterna

Il dispositivo è in grado di esportare in formato .XML il contenuto totale o parziale delle memorie permanenti salvando i dati su una scheda di memoria (Micro SD oppure SD, a seconda del formato supportato dal dispositivo).
La scheda di memoria dovrà avere una capienza minima di almeno 4GB ed essere formattata utilizzando il file system FAT32.

Si consiglia di utilizzare questa procedura prima di qualsiasi operazione sulle memorie.

Procedere come segue:

*   Inserire la scheda di memoria vuota, precedentemente formattata con file system FAT32, nell’apposito alloggiamento:
    *   `SD card` `oppure` `Micro SD card`
*   Eseguire un azzeramento fiscale (vedere l’azzeramento Z01).
*   Premere ripetutamente il tasto **CHIAVE** fino a che sul display compariranno il messaggio oppure l’icona corrispondenti all’assetto “PROGRAMMAZIONE”:
    *   `Chiave`
*   Accedere alla programmazione **SERVIZI TELEMATICI** digitando il numero corrispondente (programmazione P699):
    *   `6` `9` `9` `SubTotale`
*   Sul display viene visualizzato:

    ```
    PROGRAMMAZIONE
    699 - SERVIZI TELEMATICI
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “MENU ESERCENTE”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [MENU ESERCENTE]
    TIPO MENU
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “REPORT”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [REPORT]
    SELEZIONA SERVIZIO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e selezionare se si desidera esportare in XML la “Memoria di dettaglio” oppure la “Memoria di riepilogo” (es. “REPORT M.DETT. IN XML”):
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [REPORT M.DETT. IN XML]
    REPORT
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e selezionare “Esportazione integrale” oppure “Esportazione per data” (es. “INTEGRALE”):
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [INTEGRALE]
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Dopo la conferma il dispositivo avvierà l’esportazione dei dati sulla scheda di memoria informando l’utente sullo stato di avanzamento della procedura mediante messaggi a display
*   Al termine dell’operazione verrà stampato uno scontrino di conferma.

## 13.8 Modalità demo

Il dispositivo possiede una modalità particolare che permette di eseguire operazioni ed emettere scontrini senza che i dati vadano ad intaccare i contenuti della memoria permanente di dettaglio e/o della memoria permanente di riepilogo.

Questa modalità si rivela utile ad esempio quando si desidera istruire l’utilizzatore del dispositivo ad eseguire particolari funzionalità ed operazioni senza la possibilità di compromettere i dati registrati nelle memorie e trasmessi all’Agenzia delle Entrate.

Per ottenere un rapporto della memoria permanente di dettaglio in modalità demo, eseguire la stampa del rapporto X73 (vedere [paragrafo 10.25](#_10.25_Rapporto_memoria_di_dettaglio_in_modo_demo_(X73))).

**Abilitazione**

*   Effettuare una chiusura fiscale.
    *   `Z Report`
*   Premere ripetutamente il tasto **CHIAVE** fino a che sul display compariranno il messaggio oppure l’icona corrispondenti all’assetto “PROGRAMMAZIONE”:
    *   `Chiave`
*   Accedere alla programmazione **SERVIZI TELEMATICI** digitando il numero corrispondente (programmazione P699, vedere [paragrafo 12.59](#_12.59_Servizi_telematici_(P699))):
    *   `6` `9` `9` `SubTotale`
*   Sul display viene visualizzato:

    ```
    PROGRAMMAZIONE
    699 - SERVIZI TELEMATICI
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “MENU ESERCENTE”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [MENU ESERCENTE]
    TIPO MENU
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “MODO DEMO”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [MODO DEMO]
    SELEZIONA SERVIZIO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    [INIZIO PROCEDURA]
    MODO DEMO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    CONFERMI? [NO]
    ```
*   Selezionare “SI” utilizzando i tasti con le frecce di selezione:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    CONFERMI? [SI]
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Se il dispositivo è in servizio, viene stampato il seguente documento gestionale:

    ```
    DOCUMENTO GESTIONALE
    ────────────────────────────────────
    SEGNALAZIONE EVENTO
    ────────────────────────────────────
    <ESITO POSITIVO>
    codice http: <#>
    codice xml: <#>
    risp: segnalazione processata
    idoper: <#>
    <data> <ora> <#DOC. GES.>
    NUMERO DI MATRICOLA: <matr. fiscale>
    DOCUMENTO GESTIONALE
    ```
*   La modalità demo è ora attiva ed è visibile dai documenti che da questo momento in poi verranno stampati. Il seguente documento mostra ad esempio una vendita effettuata in modalità demo:

    ```
    ????????????<Nome?Ditta>????????????
    ?????????????<Indirizzo>?????????????
    ??????????????<Località>?????????????
    ???????????<Telefono?-?Fax>??????????
    ????DOCUMENTO?COMMERCIALE?DI?PROVA???
    DESCRIZIONE????????????PREZZO(€)?IVA
    REPARTO?01??????????????????10.00??A
    REPARTO?03???????????????????1.00??A
    TOTALE?COMPLESSIVO??????????11.00???
    DI?CUI?IVA???????????????????1.00???
    NON?RISCOSSO????????????????11.00???
    IMPORTO?PAGATO???????????????0.00???
    A:?IVA?10.00%???????????????????????
    <data>??<ora>?????????????????<#DOC.>
    ??????????<matricola fiscale>?????????
    ?????????DETTAGLIO?PAGAMENTI?????????
    CONTANTI?????????????????????11.00???
    ```

**Disabilitazione**
La seguente procedura disabilita la modalità demo e riporta il dispositivo al suo normale funzionamento.

*   Effettuare una chiusura fiscale.
    *   `Z Report`
*   Premere ripetutamente il tasto **CHIAVE** fino a che sul display compariranno il messaggio oppure l’icona corrispondenti all’assetto “PROGRAMMAZIONE”:
    *   `Chiave`
*   Accedere alla programmazione **SERVIZI TELEMATICI** digitando il numero corrispondente (programmazione P699, vedere [paragrafo 12.59](#_12.59_Servizi_telematici_(P699))):
    *   `6` `9` `9` `SubTotale`
*   Sul display viene visualizzato:

    ```
    PROGRAMMAZIONE
    699 - SERVIZI TELEMATICI
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “MENU ESERCENTE”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [MENU ESERCENTE]
    TIPO MENU
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “MODO DEMO”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [MODO DEMO]
    SELEZIONA SERVIZIO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    [FINE PROCEDURA]
    MODO DEMO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    CONFERMI? [NO]
    ```
*   Selezionare “SI” utilizzando i tasti con le frecce di selezione:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    CONFERMI? [SI]
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`

**ATTENZIONE:**
Da questo momento il dispositivo è tornato ad operare normalmente. Tutte le operazioni che da ora in poi saranno eseguite, verranno memorizzate nella memoria permanente di dettaglio e/o nella memoria permanente di riepilogo, nonché trasmesse all’Agenzia delle Entrate.

## 13.9 Ventilazione IVA

Con il metodo della ventilazione dei corrispettivi, disciplinato dal D.M. n. 3495 del 24/02/1973, i contribuenti in possesso di determinati requisiti possono facoltativamente registrare i corrispettivi giornalieri in maniera globale senza distinzione per aliquota IVA.

La ventilazione IVA si applica solo ai beni, quindi in regime di ventilazione IVA non è possibile vendere servizi.

Se l’opzione “Ventilazione IVA” viene abilitata i corrispettivi saranno registrati globalmente in un unico importo giornaliero (IVA inclusa).

Se l’opzione “Ventilazione IVA” viene disabilitata (configurazione di fabbrica) i corrispettivi saranno registrati normalmente distinguendoli per aliquota IVA.

**NOTA:**
L’abilitazione o la disabilitazione della ventilazione IVA è possibile solo ed esclusivamente dopo aver eseguito una chiusura fiscale (vedere [paragrafo 11.3](#_11.3_Chiusura_fiscale_(Z01))).

Per abilitare il metodo “Ventilazione IVA” procedere come segue:

*   Premere ripetutamente il tasto **CHIAVE** fino a che sul display compariranno il messaggio oppure l’icona corrispondenti all’assetto “PROGRAMMAZIONE”:
    *   `Chiave`
*   Accedere alla programmazione **CONFIGURAZIONE OPERAZIONI DI CASSA** digitando il numero corrispondente (programmazione P519):
    *   `5` `1` `9` `SubTotale`
*   Sul display viene visualizzato:

    ```
    PROGRAMMAZIONE
    519 - CONFIG.OPERAZ.CASSA
    ```
*   Premere ripetutamente il tasto **SUBTOTALE** fino a visualizzare la voce “VENTILAZIONE IVA”:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    VENTILAZIONE IVA [NO]
    ```
*   Utilizzando i tasti con le frecce di selezione, abilitare la funzione selezionando “SI”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    VENTILAZIONE IVA [SI]
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Il dispositivo stampa lo scontrino della programmazione.

Per il controllo dei corrispettivi inviati accedere al portale Fisconline (https://telematici.agenziaentrate.gov.it) con le proprie credenziali.

## 13.10 Aggiornamento del firmware da remoto

L’aggiornamento del firmware fiscale da remoto può essere predisposto solo da un tecnico abilitato dall’Agenzia delle Entrate e l’installazione dello stesso deve essere autorizzato dall’esercente. Tale operazione viene effettuata senza aprire il dispositivo, in modo del tutto automatico.
In questo paragrafo viene illustrata unicamente la sequenza riservata all’esercente per installare un aggiornamento precedentemente predisposto dal tecnico.

Durante la procedura di aggiornamento non spegnere il dispositivo.

*   Quando è disponibile una nuova versione di firmware da installare, il dispositivo ne effettua il download.
*   Il dispositivo emette un segnale acustico e stampa il seguente scontrino, come richiesta di aggiornamento firmware:

    ```
    DOCUMENTO GESTIONALE
    ────────────────────────────────────
    ATTENZIONE!
    RICHIESTO AGGIORNAMENTO
    DEL DISPOSITIVO!
    (CONFERMARE O POSTICIPARE)
    ────────────────────────────────────
    DA TASTIERA
    ────────────────────────────────────
    TASTO [1]: per CONFERMARE
    TASTO [0]: per POSTICIPARE
    ────────────────────────────────────
    DA UNITA’ STAMPANTE
    ────────────────────────────────────
    PRESSIONE LUNGA [FEED]: per CONFERMARE
    PRESSIONE BREVE [FEED]: per POSTICIPARE
    <data> <ora> <#DOC. GES.>
    NUMERO DI MATRICOLA: <matr. fiscale>
    DOCUMENTO GESTIONALE
    ```
*   Contemporaneamente, il dispositivo proporrà l’aggiornamento del firmware attraverso il seguente messaggio a display:

    ```
    AGGIORNA DISPOSITIVO
    ATTESA CONFERMA...
    ```
*   Premere il tasto **0** se non si intende aggiornare nell’immediato il firmware del dispositivo oppure scegliere il tasto **1** se si vuole procedere subito con l’aggiornamento.
    *   `0` `oppure` `1`

Se non si dispone di una tastiera collegata al dispositivo:

*   premere brevemente il tasto **FEED** se non si intende aggiornare nell’immediato il firmware del dispositivo, oppure
*   mantenere premuto (per almeno 3 secondi) il tasto **FEED** se si vuole procedere con l’aggiornamento.

**NOTA:**
Se si sceglie di non aggiornare nell’immediato il firmware del dispositivo, in occasione della prossima chiusura il dispositivo riproporrà la scelta dell’installazione del firmware.

*   Dopo aver scelto di eseguire l’aggiornamento firmware (tasto **1** o **FEED**), sul display comparirà la dicitura

    ```
    ATTENDERE RISPOSTA
    NON SPEGNERE \
    ```
*   Il dispositivo si riavvierà autonomamente ed eseguirà una procedura di inizializzazione (RESET 3). Sul display vengono visualizzati in sequenza i messaggi:

    ```
    RESET? 1,3
    ```
    ```
    RESET 3...
    ```
*   Il dispositivo emetterà uno scontrino di conferma ad avvenuta operazione e visualizzerà a display il seguente messaggio:

    ```
    -------------------
    CASSA CHIUSA
    ```
*   Sul display comparirà la dicitura

    ```
    CARICAMENTO
    CONFIGURAZIONE ...
    ```
    ```
    ATTENDI ...
    \
    ```
*   Il dispositivo emetterà uno scontrino di conferma ad avvenuta operazione e visualizzerà a display i seguenti messaggi:

    ```
    INVIO CORRISPETTIVI
    IN CORSO \
    ```
    ```
    INVIO CORRISPETTIVI
    <ESITO POSITIVO> \
    ```
*   Al termine della procedura, il dispositivo stamperà il seguente scontrino:

    ```
    DOCUMENTO GESTIONALE
    ------------------------------------
    TRASMISSIONE CORRISPETTIVI
    ------------------------------------
    <ESITO POSITIVO>
    codice http: <#>
    codice xml: <#>
    risp:
    numero Z: <#>
    idoper: <#>
    dataora http: <aaaa-mm-gg hh.mm.ss>
    <data> <ora> <#DOC. GES.>
    NUMERO DI MATRICOLA: <matr. fiscale>
    DOCUMENTO GESTIONALE
    ```

# LOTTERIE

## 14.1 Lotteria degli scontrini

La lotteria nazionale degli scontrini è un concorso a premi gratuito, collegato allo scontrino elettronico (e al registratore telematico) ed è una vera e propria lotteria con premi in denaro, i cui biglietti sono gli stessi scontrini della spesa sostenuta. A partire dal 1° gennaio 2021 infatti, tutti i cittadini maggiorenni e residenti in Italia che acquistano beni e servizi, di importo pari o superiore a 1.00 EURO con pagamento elettronico (carta di credito o bancomat), possono partecipare alle estrazioni.

Ogni acquisto genera un numero di biglietti “virtuali” che consentono la partecipazione alla lotteria: ogni EURO speso dà diritto a 1 biglietto virtuale, fino ad un massimo di 1.000 biglietti per un acquisto pari o superiore a 1.000 EURO.
Se l’importo speso è superiore ad un EURO, l’eventuale cifra decimale superiore a 49 centesimi produrrà comunque un altro biglietto virtuale.

Non saranno validi ai fini della lotteria gli scontrini corrispondenti ad acquisti effettuati online o nell’esercizio di attività di impresa, arte o professione. Non partecipano alla lotteria, inoltre, gli acquisti per i quali il consumatore richieda all’esercente l’acquisizione del proprio codice fiscale a fini di detrazione o deduzione fiscale.

Nella fase di avvio della lotteria faranno eccezione anche gli acquisti documentati mediante fatture elettroniche e gli acquisti per i quali i dati dei corrispettivi sono trasmessi al sistema Tessera Sanitaria (per esempio gli acquisti effettuati presso farmacie, parafarmacie, ottici, laboratori di analisi, ambulatori veterinari, ecc.).

Il Portale Lotteria (https://www.lotteriadegliscontrini.gov.it) è composto da un’area pubblica e da un’area riservata, descritte in dettaglio di seguito.
Per avere il codice lotteria non serve registrarsi all’area riservata del Portale. Basta infatti inserire il codice fiscale nell’area pubblica.

**Area pubblica**
L’area pubblica contiene una serie di informazioni relative alla lotteria, quali ad esempio:
*   il calendario delle estrazioni
*   il codice degli scontrini vincenti
*   le informazioni sulle modalità di partecipazione e di riscossione dei premi.

Nell’area pubblica, alla quale si accede liberamente, senza autenticazione, sarà inoltre possibile generare il codice lotteria necessario per partecipare all’estrazione.

**Area riservata**
Nell’area riservata, accessibile tramite SPID, credenziali Fisconline/Entratel o CNS (Carta Nazionale dei Servizi), sarà possibile invece:
*   controllare il numero di biglietti virtuali associati al singolo scontrino elettronico ricevuto
*   verificare le eventuali vincite
*   tenere sotto controllo i termini per reclamare i premi.

Inoltre nell’area riservata è possibile attivare SMS e altri avvisi per ricevere le comunicazioni.

Sempre nell’area riservata è possibile esercitare i propri diritti nei confronti del titolare del trattamento dei dati come, per esempio, opporsi al trattamento (ad es. inibire la generazione di ulteriori nuovi codici lotteria oltre a quelli già generati) e chiedere la cancellazione dei dati (per esempio, eliminare l’associazione tra il codice lotteria e i documenti commerciali).

Infine è possibile consultare i codici lotteria associati al proprio codice fiscale, con la relativa data di generazione.

I dati relativi al singolo documento rilasciato e al numero dei biglietti virtuali della lotteria associati, come pure le vincite (se presenti) sono disponibili sul Portale per il tempo strettamente necessario e, in ogni caso, per un tempo non superiore a 24 mesi dalla loro acquisizione.

Per abilitare o meno la funzionalità lotteria degli scontrini vedere il [paragrafo 12.59](#_12.59_Servizi_telematici_(P699)).

## 14.2 Codice lotteria degli scontrini

Per ottenere il codice lotteria occorre accedere all’area pubblica del Portale Lotteria messo a disposizione dall’Agenzia delle Dogane e dei Monopoli (https://www.lotteriadegliscontrini.gov.it).

Non occorre alcuna registrazione: è sufficiente digitare il proprio codice fiscale sul portale ed il servizio online produce un codice lotteria alfanumerico (in formato codice a barre).

Una volta ottenuto, è sufficiente stampare il proprio codice lotteria o memorizzarlo sul proprio dispositivo mobile (telefono cellulare, smartphone, tablet, ecc.), presentandolo all’esercente al momento dell’acquisto di beni o servizi.

*   `Lotteria degli scontrini`
*   `Codice lotteria identificativo`
    *   `N B 7 A 1 2 3 5`
*   `Utilizzare il codice lotteria al momento dell’acquisto`

Per maggiori informazioni consultare il Portale Lotteria (https://www.lotteriadegliscontrini.gov.it).

## 14.3 Funzionamento lotteria degli scontrini

Il calendario delle estrazioni è pubblicato sul sito dell’Agenzia delle Dogane e dei Monopoli e sul Portale Lotteria (https://www.lotteriadegliscontrini.gov.it/portale).

Una volta generato il codice lotteria (vedere [paragrafo 14.2](#_14.2_Codice_lotteria_degli_scontrini)), potrà essere stampato su carta o salvato su dispositivo mobile (telefono cellulare, smartphone, tablet, ecc.) e presentato all’esercente al momento dell’acquisto di beni o servizi.

**NOTA:**
Il codice lotteria è un codice alfanumerico, composto da 8 caratteri, che viene associato al codice fiscale del consumatore in maniera univoca e casuale (random), senza alcun obbligo di identificarsi. Ogni consumatore può generare più codici, tutti ugualmente validi per partecipare alla lotteria.

Per ogni scontrino elettronico trasmesso all’Agenzia delle Entrate il sistema lotteria genererà un determinato numero di biglietti virtuali. Ogni scontrino genera un numero di “biglietti virtuali” della lotteria pari a un biglietto per ogni EURO di spesa, con un arrotondamento se la cifra decimale supera i 49 centesimi (ad es. con 1.50 EURO di spesa si ottengono due biglietti virtuali).

L’esercente, attraverso un lettore di codici a barre collegato al registratore telematico, effettua il collegamento tra lo scontrino e il codice lotteria del contribuente e trasmette i dati all’Agenzia delle Entrate.

*   `Acquisizione codice lotteria`
*   `trasmissione codice lotteria`
*   `Agenzia delle Entrate`

I vincitori verranno informati immediatamente tramite SMS, e-mail o instant messaging se i relativi dettagli sono stati forniti dal consumatore nell’area riservata del Portale Lotteria.
In ogni caso, chi vince riceve anche una comunicazione formale che può avvenire in due modi:
1.  tramite una PEC (Posta Elettronica Certificata) inviata all’indirizzo che il consumatore ha indicato sul Portale Lotteria
2.  tramite una raccomandata con ricevuta di ritorno che viene recapitata all’ultimo domicilio fiscale conosciuto dall’Agenzia delle Entrate.

**ATTENZIONE:**
Non occorre conservare gli scontrini sia per partecipare alla lotteria sia per riscuotere i premi (occorre custodire gli scontrini solo a fini di garanzia, cambio merce, ecc.).

Non partecipano alla lotteria degli scontrini i dati dei corrispettivi riferiti alle operazioni di cessioni di beni o prestazioni di servizi per le quali il cliente consumatore finale richiede all’esercente l’acquisizione del proprio codice fiscale.

## 14.4 Lotteria istantanea

La lotteria istantanea non sostituisce il concorso della lotteria degli scontrini con codice lotteria descritto nei precedenti paragrafi ma è un concorso attivo parallelamente ad esso.

Mentre per la lotteria degli scontrini è necessario un codice lotteria alfanumerico (vedere [paragrafo 14.2](#_14.2_Codice_lotteria_degli_scontrini)) per la lotteria istantanea ciò non è necessario. Il dispositivo (registratore di cassa o stampante fiscale) genera autonomamente il codice bidimensionale che viene stampato sullo scontrino emesso.
Tale codice conterrà tutte le informazioni necessarie alla partecipazione del concorso.

Per fare ciò sono necessarie due condizioni: la prima è che l’importo dello scontrino sia pari o superiore ad 1.00 EURO; la seconda è che il pagamento di tale importo avvenga in modalità elettronica (carta di credito o di debito).

Per abilitare o meno la funzionalità lotteria istantanea vedere il [paragrafo 12.59](#_12.59_Servizi_telematici_(P699)).

**ATTENZIONE:**
Non partecipano alla lotteria degli scontrini i dati dei corrispettivi riferiti alle operazioni di cessioni di beni o prestazioni di servizi per le quali il cliente consumatore finale richiede all’esercente l’acquisizione del proprio codice fiscale.

## 14.5 Attivazione lotterie

Per poter usufruire delle funzionalità di una o entrambe le lotterie (vedere [paragrafo 12.59](#_12.59_Servizi_telematici_(P699))), potrebbe essere necessario attivarle come descritto di seguito.

*   Effettuare una chiusura fiscale.
    *   `Z Report`
*   Premere ripetutamente il tasto **CHIAVE** fino a che sul display compariranno il messaggio oppure l’icona corrispondenti all’assetto “PROGRAMMAZIONE”:
    *   `Chiave`
*   Accedere alla programmazione **SERVIZI TELEMATICI** digitando il numero corrispondente (programmazione P699, vedere [paragrafo 12.59](#_12.59_Servizi_telematici_(P699))):
    *   `6` `9` `9` `SubTotale`
*   Sul display viene visualizzato:

    ```
    PROGRAMMAZIONE
    699 - SERVIZI TELEMATICI
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “MENU TECNICO”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [MENU TECNICO]
    TIPO MENU
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “LOTTERIA”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [LOTTERIA]
    SELEZIONA SERVIZIO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Utilizzando i tasti con le frecce di selezione, navigare all’interno dei menù e visualizzare la voce “ATTIVAZIONE”:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    [ATTIVAZIONE]
    SELEZIONA SERVIZIO
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    DATA LOTTERIA ggmmaa 000000
    ```
*   Per attivare nell’immediato la lotteria degli scontrini, inserire **000000** (6 volte zero) altrimenti inserire la data futura di attivazione.
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    DATA LOTT.IST ggmmaa 000000
    ```
*   Per attivare nell’immediato la lotteria istantanea, inserire **000000** (6 volte zero) altrimenti inserire la data futura di attivazione.
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Sul display viene visualizzato:

    ```
    CONFERMI? [NO]
    ```
*   Selezionare “SI” utilizzando i tasti con le frecce di selezione:
    *   `←` `oppure` `→`
*   Sul display viene visualizzato:

    ```
    CONFERMI? [SI]
    ```
*   Premere il tasto **SUBTOTALE** per confermare:
    *   `SubTotale`
*   Per un esempio di vendita con la lotteria degli scontrini o con la lotteria istantanea, vedere [paragrafo 20.14](#_20.14_Esempio_di_vendita_con_lotteria_degli_scontrini) e [paragrafo 20.15](#_20.15_Esempio_di_vendita_con_lotteria_istantanea).

**NOTA:**
Dopo aver attivato la lotteria istantanea, il dispositivo scaricherà dal server le chiavi per tale servizio e visualizzerà a display per diversi secondi il seguente messaggio:

```
LOAD CHIAVI LOTTERIA
IN CORSO \
```
