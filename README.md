# Regressione con il Machine Learning — Lezione per le scuole superiori

Materiale didattico di una lezione di **4 ore** sul problema della **regressione** affrontato con strumenti di machine learning. Pensata per studenti del **quarto anno** delle superiori con **rudimenti minimi di programmazione Python**.

Il filo rosso è una **storia**: gli studenti vestono i panni del reparto dati di una società sportiva e devono capire cosa determina il valore di mercato dei calciatori. Si parte dall'esplorazione dei dati e si arriva alla distinzione tra apprendimento e memorizzazione (overfitting).

## Struttura della lezione

| # | Notebook | Durata | Tema | Colab |
|---|---|---|---|---|
| 1 | `01_il_mistero_del_valore.ipynb` | ~1h | Esplorazione dati, correlazione | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/riccardoberta/regressione-superiori/blob/main/01_il_mistero_del_valore.ipynb) |
| 2 | `02_primo_scout_automatico.ipynb` | ~1h | Regressione lineare semplice, MSE, residui, metriche di errore | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/riccardoberta/regressione-superiori/blob/main/02_primo_scout_automatico.ipynb) |
| 3 | `03_lo_scout_migliora.ipynb` | ~1h | Regressione lineare multipla, standardizzazione, importanza delle feature | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/riccardoberta/regressione-superiori/blob/main/03_lo_scout_migliora.ipynb) |
| 4 | `04_generalizzazione_overfitting.ipynb` | ~1h | Train/test split, alberi decisionali, overfitting, bias-variance | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/riccardoberta/regressione-superiori/blob/main/04_generalizzazione_overfitting.ipynb) |

## Obiettivi di apprendimento

Al termine della lezione lo studente sarà in grado di:

- Riconoscere un problema di regressione e formularlo in modo matematico ($X$, $\mathbf{y}$, $f$).
- Interpretare grafici a dispersione e coefficienti di correlazione.
- Allenare e valutare un modello di regressione lineare con `scikit-learn`.
- Confrontare modelli diversi usando MAE, RMSE e $R^2$.
- Capire perché serve un *test set* e cosa sono *underfitting* e *overfitting*.

## Come usare i notebook in aula

1. Apri il notebook desiderato cliccando sul **badge "Open in Colab"**.
2. Vai su **Runtime → Esegui tutto** (oppure `Ctrl+F9` / `Cmd+F9`) prima di iniziare la lezione, per scaricare il dataset e popolare le celle.
3. Durante la lezione, esegui le celle una per una insieme alla classe.

I notebook usano due tipi di celle visivamente distinte:

- **Box azzurro/viola** (`concept`, `reveal`): missione, intuizione, domande aperte per la discussione.
- **Box giallo "Teoria"**: definizioni formali e formule matematiche in LaTeX.

## Dataset

I notebook usano il **FIFA 22 dataset** ([Kaggle](https://www.kaggle.com/datasets/stefanoleone992/fifa-22-complete-player-dataset), licenza CC0). Per garantire la riproducibilità in aula, ogni notebook scarica automaticamente una copia congelata da Dropbox alla prima esecuzione (~10 secondi). Non serve registrarsi a Kaggle né caricare file manualmente.

## Prerequisiti

**Per gli studenti**: minimi rudimenti di Python (variabili, chiamate a funzione). Non è richiesta esperienza con `pandas`, `numpy` o `matplotlib`: i notebook spiegano i pochi pattern usati.

**Tecnici**: solo un browser e un account Google (per Colab). Niente da installare in locale.

## Concetti matematici introdotti

I notebook introducono progressivamente:

- Notazione vettoriale e matriciale di un dataset
- Coefficiente di correlazione di Pearson
- Modello lineare $\hat{y} = wx + b$ e sua estensione multivariata $\hat{y} = \mathbf{w}^\top\mathbf{x} + b$
- Funzione di costo (errore quadratico medio) e principio dei minimi quadrati
- Metriche di valutazione: MAE, RMSE, $R^2$
- Standardizzazione delle variabili
- Errore empirico vs errore atteso, training/test split
- Curva a U dell'overfitting, equilibrio bias-varianza

## Esecuzione locale (alternativa a Colab)

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
jupyter notebook
```

## Licenza

Materiale didattico distribuito con licenza [MIT](LICENSE). Il dataset originale è di [EA Sports / Kaggle](https://www.kaggle.com/datasets/stefanoleone992/fifa-22-complete-player-dataset) (CC0).
