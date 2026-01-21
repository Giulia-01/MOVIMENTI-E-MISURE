# MOVIMENTI-E-MISURE

## DOI: 

## Descrizione: 
Il progetto analizza un dataset storico-artistico utilizzando Pandas, propone un'analisi esplorativa del dataset **VAPOD**, per pulire e strutturare i dati. L’obiettivo è esplorare relazioni tra generi, movimenti e dimensioni delle opere, evidenziando pattern storici e stilistici. In particolare, il progetto indaga come le interazioni tra variabili temporali, tematiche e dimensionali possono far emergere tendenze nelle scelte  stilistiche. 

## Domande di Ricerca
L'indagine si articola su due assi principali:
1. **RQ1 - Generi e Movimenti nel Tempo**: Qual è la distribuzione dei generi nelle diverse epoche e come si riflette la differenza tra movimenti artistici (es. dal Rinascimento al Romanticismo) nei soggetti rappresentati?
2. **RQ2 - Relazione tra Dimensioni e Genere**: Esiste una correlazione sistematica tra le misure dell'opera (altezza \times larghezza) e la sua tipologia tematica?

##Fonte dei dati 
| Variabile       | Tipo di dato       | Definizione                                                   | Esempio |
|-----------------|------------------|---------------------------------------------------------------|---------|
| `id`            | Stringa/URL      | Identificativo univoco dell’opera, spesso link a Wikidata o altra fonte esterna | `http://www.wikidata.org/entity/Q428274` |
| `titolo`        | Stringa          | Titolo dell’opera d’arte                                      | *Ritratto di Fedra Inghirami, detto Fedra* |
| `artisti`       | Stringa          | Nome dell’artista autore dell’opera                           | *Raffaello Sanzio (maschio)* |
| `data_creazione`| Intero/Stringa   | Anno di creazione dell’opera                                   | `1510` |
| `generi`        | Stringa          | Genere artistico o descrittivo dell’opera                     | *ritratto* |
| `luoghi`        | Stringa          | Luogo o museo in cui l’opera è conservata                     | *Galleria Palatina* |
| `collezioni`    | Stringa          | Collezione o contesto espositivo                               | *Galleria Palatina* |
| `contenuti`     | Stringa          | Elementi semantici/temi presenti nell’opera                   | *libro; carta; scrittura; strabismo; …* |
| `movimenti`     | Stringa          | Movimento artistico a cui l’opera è associata                 | *Alto Rinascimento* |
| `soggetti`      | Stringa          | Principali figure o soggetti rappresentati                    | *Tommaso Inghirami* |
| `altezza`       | Float            | Altezza dell’opera in centimetri                               | `91.0` |
| `larghezza`     | Float            | Larghezza dell’opera in centimetri                             | `61.0` |

I dati originali sono stati estratti dal dataset storico artistico al seguente link: [https://raw.githubusercontent.com/dhdmch/2025-2026/refs/heads/main/data/vapod/data.csv]

## Metodi e strumenti 	
Il progetto è stato sviluppato tramite Google Colab usando il linguaggio di programmazione Python. Lo strumento principale per la manipolazione, l'analisi e la visualizzazione dei dati è la libreria Pandas. Inoltre, per il calcolo scientifico è stata importata la libreria NumPy. Infine, per la visualizzazione dei risultati sotto forma di grafico è stata utilizzata la libreria matplotlib.pyplot. 
Per garantire la coerenza dell'analisi, sono state eseguite le seguenti operazioni di trattamento dati:
* **Caricamento e ispezione dei dati**: *p.read_csv, df.head(), df.info(), df.describe()*
* **Creazione di nuove variabili**: *top5_per_secolo, df_generi*
* **Normalizzazione dei datie**: Estrazione dell'anno di creazione e aggregazione in secoli per facilitare l'analisi di lungo periodo.
* **Gestione Campi Multivalore**: Trattamento delle colonne `generi` e `movimenti` tramite le funzioni ".split()" ed ".explode()" dei dati, necessarie per gestire le opere associate a più categorie.
* **Analisi esplorativa tramite aggregazioni**: *value_counts(), groupby()*
* **Standardizzazione Dimensionale**: Conversione delle misure in metri e calcolo della superficie in $m^2$ per un confronto oggettivo delle aree.
* **Visualizzazione dei risultati**: tramite grafici a barre *.plot()*

## Analisi dei Risultati
Verificare la predilezione di determinati generi nelle singole epoche per poi ipotizzare un legame tra genere e movimento. 
- 
### Evoluzione dei Generi (RQ1)
L'analisi evidenzia una chiara transizione tematica:
* **Rinascimento e Barocco**: Risultano dominati dall'**arte religiosa** (con oltre 100 occorrenze nel solo Rinascimento), a testimonianza della committenza ecclesiastica prevalente.
* **Romanticismo**: Si osserva un significativo mutamento verso soggetti laici; il **ritratto** emerge come genere principale, affiancato da un crescente interesse per la pittura di paesaggio e la pittura storica.

### Morfologia e Funzione (RQ2)
I dati confermano che la dimensione dell'opera è spesso funzione della sua destinazione d'uso:
* I generi destinati a contesti pubblici o monumentali (**pittura mitologica** e **arte religiosa**) presentano le aree mediane più elevate (circa 2 $m^2$).
* I generi legati alla fruizione privata o individuale (**ritratto** e **autoritratto**) presentano invece dimensioni sensibilmente più ridotte, con mediane inferiori a 1 $m^2$.

## Dataset e Strumenti
* **Fonte Dati**: Dataset VAPOD (formato CSV) disponibile al link: [https://raw.githubusercontent.com/dhdmch/2025-2026/refs/heads/main/data/vapod/data.csv](https://raw.githubusercontent.com/dhdmch/2025-2026/refs/heads/main/data/vapod/data.csv).
* **Strumenti**: Python (Pandas, NumPy, Matplotlib) tramite ambiente Google Colab.

## DOI e Citazione
* **DOI**: (Inserire il DOI dopo l'archiviazione su Zenodo).
* **Licenza**: CC0-1.0.

---
*Relazione prodotta per il corso di Informatica per i Beni Culturali (2025/2026).*
