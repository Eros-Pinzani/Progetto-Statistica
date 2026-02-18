# Analisi Statistica del Contenuto Alcolico nel Vino

[![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)](https://www.r-project.org/)
[![RMarkdown](https://img.shields.io/badge/RMarkdown-FF6600?style=flat&logo=r&logoColor=white)](https://rmarkdown.rstudio.com/)

## 📊 Descrizione del Progetto

Questo progetto presenta un'analisi statistica approfondita della composizione chimica di campioni di vino italiano, con particolare focus sul **contenuto alcolico** come variabile target. L'analisi integra tecniche avanzate di modellazione statistica per comprendere le relazioni tra le variabili chimiche e il ruolo della cultivar (tipo di coltivazione) nella determinazione del grado alcolico.

## 🎯 Obiettivi

L'analisi si articola in **due fasi principali**:

### Fase 1: Analisi della Popolazione Globale
- Identificare le **dipendenze condizionali** tra variabili chimiche tramite modelli grafici gaussiani (Gaussian Graphical Models)
- Esplorare le **relazioni causali** mediante grafi aciclici diretti (DAG)
- Costruire **modelli predittivi** del contenuto alcolico basati esclusivamente su fattori chimici

### Fase 2: Analisi con Cultivar
- Valutare l'impatto del tipo di **cultivar** sulle relazioni tra variabili chimiche
- Determinare se il tipo di coltivazione ha un effetto diretto sul contenuto alcolico
- Confrontare i modelli con e senza cultivar per valutare il contributo informativo di questa variabile categorica

## 📁 Dataset

Il progetto utilizza il **Wine Dataset**, un dataset classico disponibile nel pacchetto R `gRbase`, contenente:

- **178 osservazioni** (campioni di vino italiano)
- **13 variabili chimiche continue**:
  - `Alch` - Contenuto alcolico (variabile target)
  - `Mlca` - Acido malico
  - `Ash` - Ceneri
  - `Aloa` - Alcalinità delle ceneri
  - `Mgns` - Magnesio
  - `Ttlp` - Fenoli totali
  - `Flvn` - Flavonoidi
  - `Nnfp` - Fenoli non flavonoidi
  - `Prnt` - Proantocianidine
  - `Clri` - Intensità del colore
  - `Hue` - Tonalità
  - `Oodw` - Rapporto OD280/OD315 di vini diluiti
  - `Prln` - Prolina
- **1 variabile categorica**: `Cult` (Cultivar: 3 livelli corrispondenti a 3 diversi coltivatori)

## 🔬 Metodologia

Il progetto impiega tre approcci statistici complementari:

### 1. Modelli Grafici Indiretti (Gaussian Graphical Models)
Identificazione delle dipendenze condizionali tra variabili attraverso l'analisi della matrice di concentrazione (inversa della matrice di covarianza).

### 2. Modelli Grafici Diretti (DAG - Directed Acyclic Graphs)
Esplorazione di possibili relazioni causali tra le variabili chimiche e il contenuto alcolico mediante:
- Algoritmo Hill-Climbing per l'apprendimento della struttura del DAG
- Analisi con e senza vincoli sulla variabile target
- Confronto tra scenario popolazione globale e scenario con cultivar

### 3. Regressione Lineare Multipla
Quantificazione dell'effetto dei predittori chimici sul contenuto alcolico e valutazione della capacità predittiva dei modelli inferiti dai DAG.

## 🛠️ Requisiti e Dipendenze

### Software Richiesto
- **R** (versione ≥ 4.0.0)
- **RStudio** (opzionale ma consigliato)

### Pacchetti R Necessari

```r
install.packages(c(
  "gRbase",      # Dataset Wine e modelli grafici
  "gRim",        # Modelli di indipendenza grafica
  "igraph",      # Visualizzazione grafi
  "ggplot2",     # Grafici
  "dplyr",       # Manipolazione dati
  "gridExtra",   # Disposizione multipla grafici
  "GGally",      # Matrici di scatterplot
  "corrplot",    # Matrici di correlazione
  "knitr",       # Knitting documento R Markdown
  "tidyr",       # Data tidying
  "pheatmap",    # Heatmap
  "bnlearn"      # Apprendimento struttura DAG
))
```

## 🚀 Come Riprodurre l'Analisi

### Metodo 1: Knitr (Consigliato)
1. Apri il file `Analisi Statistica-del-Contenuto-Alcolico-nel-Vino.Rmd` in RStudio
2. Clicca sul pulsante **"Knit"** nella toolbar
3. Scegli il formato di output desiderato (PDF preferibilmente)

### Metodo 2: Linea di Comando R
```r
# Da R o RStudio console
rmarkdown::render("Analisi Statistica-del-Contenuto-Alcolico-nel-Vino.Rmd",
                  output_format = "pdf_document")
```

**Nota**: Per generare output PDF è necessario avere installato LaTeX (es. TinyTeX, MiKTeX o TeXLive).

## 📈 Risultati Principali

L'analisi produce i seguenti output:

- **Analisi esplorativa completa**: statistiche descrittive, grafici di densità, boxplot, scatterplot matrices, matrici di correlazione
- **Modelli grafici indiretti**: grafi di indipendenza condizionale con e senza cultivar
- **DAG inferiti**: grafi causali per scenario popolazione globale e scenario con cultivar, sia liberi che vincolati sulla variabile target
- **Modelli di regressione**: quantificazione degli effetti predittivi sul contenuto alcolico
- **Confronti**: valutazione del contributo della variabile cultivar nelle diverse analisi

## 📝 Contenuto del Report

Il documento R Markdown è organizzato nelle seguenti sezioni:

1. **Abstract**: Sintesi obiettivi e metodologia
2. **Introduzione**: Descrizione dataset, variabile target e obiettivi dello studio
3. **Osservazioni e Preprocessing dei Dati**: Caricamento e preparazione dei dati
4. **Analisi Esplorativa**: Statistiche descrittive e visualizzazioni
5. **Modelli Grafici**: Costruzione e interpretazione di modelli grafici gaussiani e DAG
6. **Regressione Lineare Multipla**: Modelli predittivi basati sui DAG inferiti
7. **Conclusioni**: Sintesi dei risultati e implicazioni

## 🔗 Riferimenti

- UCI Machine Learning Repository - [Wine Dataset](https://archive.ics.uci.edu/ml/datasets/wine)

---

<div align="center">

**Se questo progetto ti è stato utile, lascia una ⭐!**

</div>
