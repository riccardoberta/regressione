# Regressione con il Machine Learning

Materiale didattico per una introduzione al **machine learning** tramite un problema di **regressione**. Pensata per studenti delle scuole superiori con rudimenti minimi di programmazione Python.

Il filo conduttore è una **storia**: gli studenti vestono i panni del reparto dati di una società sportiva e devono capire cosa determina il valore di mercato di un calciatore. Partendo dall'esplorazione dei dati arrivano, in quattro tappe, a costruire e valutare i propri modelli predittivi e a riconoscere il fenomeno dell'overfitting.

## Struttura della lezione

Quattro notebook progressivi. Ogni notebook è autonomo: scarica il dataset, applica la pulizia e introduce i concetti necessari.

| # | Notebook | Tema | Colab |
|---|---|---|---|
| 1 | `01_il_mistero_del_valore.ipynb` | Esplorazione dei dati, intuizioni visive, coefficiente di correlazione di Pearson | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/riccardoberta/regressione/blob/main/01_il_mistero_del_valore.ipynb) |
| 2 | `02_primo_scout_automatico.ipynb` | Regressione lineare semplice, funzione costo, discesa del gradiente, residui, metriche di errore | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/riccardoberta/regressione/blob/main/02_primo_scout_automatico.ipynb) |
| 3 | `03_lo_scout_migliora.ipynb` | Regressione lineare multipla, standardizzazione, importanza delle feature | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/riccardoberta/regressione/blob/main/03_lo_scout_migliora.ipynb) |
| 4 | `04_generalizzazione_overfitting.ipynb` | Train/test split, alberi decisionali, overfitting, equilibrio bias–varianza | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/riccardoberta/regressione/blob/main/04_generalizzazione_overfitting.ipynb) |

## Obiettivi di apprendimento

Al termine della lezione lo studente sarà in grado di:

- riconoscere un problema di regressione e formularlo in modo matematico;
- interpretare grafici a dispersione e coefficienti di correlazione;
- distinguere correlazione, importanza e causalità;
- allenare e valutare un modello di regressione lineare con `scikit-learn`;
- spiegare a parole come funziona la discesa del gradiente;
- confrontare modelli diversi usando MAE, RMSE e $R^2$;
- comprendere perché serve un *test set* e cosa sono *underfitting* e *overfitting*.

## Approccio didattico

Ogni notebook segue lo stesso schema: prima di ogni cella di codice c'è una **cella di testo** che spiega *cosa* stiamo per fare e *perché*, ricollegandolo alla storia. Il codice è generosamente commentato: nessuna riga è "magica", e i pochi pattern di `pandas`, `numpy` e `matplotlib` usati sono introdotti gradualmente.

Le **sezioni di teoria matematica** (formule, derivazioni, definizioni) sono raccolte in blocchi dedicati con titolo `###`, in modo che il docente possa scegliere se affrontarle in profondità o passare oltre a seconda del livello della classe. Le formule sono in LaTeX e renderizzate da Colab.

Alla fine di ogni notebook ci sono due celle di chiusura:

- **Cosa dovremmo aver capito** — sintesi dei concetti chiave dell'episodio;
- **Cosa faremo adesso** — ponte narrativo verso il notebook successivo.

## Concetti matematici introdotti

I notebook introducono progressivamente:

- notazione vettoriale e matriciale di un dataset ($X \in \mathbb{R}^{n \times p}$, $\mathbf{y} \in \mathbb{R}^n$);
- coefficiente di correlazione di Pearson;
- modello lineare $\hat{y} = wx + b$ e sua estensione multivariata $\hat{y} = \mathbf{w}^\top\mathbf{x} + b$;
- funzione di costo (errore quadratico medio) e principio dei minimi quadrati;
- discesa del gradiente come algoritmo iterativo di ottimizzazione, ruolo del *learning rate*;
- metriche di valutazione: MAE, RMSE, $R^2$;
- standardizzazione delle variabili e confronto dei coefficienti;
- errore empirico vs errore atteso, separazione *train/test*;
- curva a U dell'overfitting, equilibrio *bias–varianza*.

## Come usare i notebook in aula

1. Apri il notebook desiderato cliccando sul badge **"Open in Colab"** della tabella sopra.
2. Prima dell'inizio della lezione, esegui *Runtime → Esegui tutto* (`Ctrl+F9` / `Cmd+F9`) per scaricare il dataset e popolare le celle: alla prima esecuzione l'archivio FIFA viene scaricato da Dropbox (~10 secondi), poi tutto è in cache.
3. Durante la lezione, riazzera con *Runtime → Riavvia* e poi esegui le celle una per una insieme alla classe, leggendo prima la cella di testo e poi mostrando il risultato della cella di codice.

Suggerimento: ai punti più densi (le sezioni di teoria) può aiutare alternare codice e lavagna — i grafici 3D della funzione costo, in particolare, sono molto più efficaci se accompagnati da uno schizzo dal vivo.

## Dataset

I notebook usano il **FIFA 22 dataset** ([Kaggle](https://www.kaggle.com/datasets/stefanoleone992/fifa-22-complete-player-dataset), licenza CC0). Per garantire la riproducibilità in aula, ogni notebook scarica automaticamente una copia congelata da Dropbox alla prima esecuzione: non serve registrarsi a Kaggle né caricare file manualmente.

In tutti i notebook viene applicata la stessa pulizia: si tengono solo le colonne utili (identità, età, overall, potential, salario, valore), si rimuovono i giocatori senza valore di mercato e si esclude l'1% di giocatori più costosi (i fuoriclasse) per non far esplodere la scala dei grafici. Questa scelta è dichiarata esplicitamente: gli studenti capiscono che ogni *preprocessing* è una decisione interpretativa, non un trucco.

## Prerequisiti

**Per gli studenti**: minimi rudimenti di Python (variabili, funzioni, liste, cicli `for`). Non è richiesta esperienza pregressa con `pandas`, `numpy`, `matplotlib` o `scikit-learn`: i pattern usati sono pochi e introdotti man mano.

**Setup**: serve solo un browser e un account Google per accedere a Colab. Nessuna installazione locale.

## Esecuzione locale (alternativa a Colab)

Se preferisci eseguire i notebook in locale:

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
jupyter notebook
```

## Licenza

Materiale didattico distribuito con licenza [MIT](LICENSE).

Il dataset originale è di [EA Sports](https://www.ea.com/games/fifa) ed è pubblicato su [Kaggle](https://www.kaggle.com/datasets/stefanoleone992/fifa-22-complete-player-dataset) con licenza CC0.
