# ToysGroup – Analisi dei dati con Python

## Descrizione del progetto

Questo progetto analizza i dati di ToysGroup, un'azienda che distribuisce giocattoli attraverso una rete di rivenditori. L'obiettivo è esaminare le vendite, individuare eventuali problemi nei dati e utilizzare alcuni strumenti di analisi e Machine Learning per approfondire l'andamento dell'attività e il comportamento dei rivenditori.

Il lavoro è sviluppato in Python, in un unico notebook Jupyter, a partire da quattro dataset.

## Dataset

- **products.csv:** anagrafica dei prodotti, categorie e prezzi.
- **regions.xlsx:** informazioni sulle aree geografiche.
- **resellers.csv:** informazioni sui rivenditori, compresi alcuni indicatori di attività e il churn.
- **sales.json:** transazioni di vendita, con date, quantità e importi.

I file originali si trovano nella cartella `dati/`.

## Analisi svolte

Il notebook `ToysGroup_EPICODE_Build_week_3.ipynb` è organizzato nei seguenti task:

1. **Python di base:** caricamento dei file, classificazione dei prodotti per prezzo, calcolo del fatturato per categoria e utilizzo di un ciclo `while`.
2. **Esplorazione dei dati:** lettura dei dataset con Pandas, controllo di colonne e tipi di dato, statistiche descrittive e selezioni con `loc` e `iloc`.
3. **Pulizia e analisi delle vendite:** gestione dei valori mancanti, filtri, unione delle tabelle, aggregazioni e analisi dell'andamento mensile.
4. **Visualizzazione:** grafici con Matplotlib, Seaborn e Plotly per confrontare vendite, categorie, aree geografiche e variabili numeriche.
5. **Regressione lineare:** confronto tra un modello semplice e uno multiplo per stimare il fatturato mensile.
6. **Machine Learning sui rivenditori:** classificazione del churn con regressione logistica e segmentazione tramite K-Means.
7. **Debugging:** individuazione e correzione di quattro esempi di codice problematico.

## Struttura dei file

```text
Progetto_EPICODE_ToysGroup/
├── ToysGroup_EPICODE_Build_week_3.ipynb
├── README.md
├── requirements.txt
└── dati/
    ├── ESERCIZIO_M4-4-2_traccia_finale-products.csv
    ├── ESERCIZIO_M4-4-2_traccia_finale-regions.xlsx
    ├── ESERCIZIO_M4-4-2_traccia_finale-resellers.csv
    └── ESERCIZIO_M4-4-2_traccia_finale-sales.json
```

## Esecuzione

Le librerie utilizzate sono indicate nel file `requirements.txt`. Per installarle in un ambiente Python locale:

```bash
python -m pip install -r requirements.txt
```

Aprire il notebook in Jupyter oppure Google Colab ed eseguire le celle in ordine. Il codice legge i quattro dataset dal percorso relativo `dati/`. Su Colab, la cartella deve essere disponibile in `/content/dati/`, oppure va aggiornato il percorso nella variabile `DATI`.

## Risultati principali

L'analisi delle vendite comprende il periodo dal 2023 al 2025. La pulizia dei dati prevede la sostituzione dei valori mancanti di `Quantity` con la mediana e l'esclusione delle transazioni prive di `SalesAmount`.

Per la previsione del fatturato sono stati confrontati due modelli di regressione lineare. Entrambi hanno ottenuto un R² negativo sui dati di test: le previsioni dei mesi successivi sono quindi da interpretare con cautela.

Per il churn dei rivenditori è stata utilizzata la regressione logistica, confrontando due soglie di classificazione. La soglia 0,3 consente di individuare una quota maggiore di rivenditori a rischio rispetto alla soglia 0,5, a fronte di un diverso equilibrio tra precisione e falsi positivi.

Infine, K-Means è stato utilizzato per raggruppare i rivenditori in base a caratteristiche legate alla loro attività, senza utilizzare `Churn` nella creazione dei gruppi.

## Considerazioni finali

Il progetto mostra come unire più fonti di dati, controllarne la qualità e ricavare informazioni utili attraverso tabelle, grafici e modelli. I risultati dei modelli predittivi sono stati valutati anche considerando i loro limiti, senza trattare le previsioni come valori certi.
