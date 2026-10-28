# Simulazione di un esperimento di computazione quantistica fotonica

Codice a corredo della tesina omonima, svolta nell'ambito di un progetto di ricerca con il
prof. Fabio Sciarrino e Francesco Hoch, Quantum Lab, Dipartimento di Fisica, Sapienza
Università di Roma.

Il repository raccoglie tre notebook Jupyter, uno per ciascuna delle parti della trattazione
che comportano un calcolo. Il criterio seguito in tutto il lavoro è che a ogni risultato
analitico corrisponda una verifica numerica indipendente: ciascun notebook, oltre a produrre
le figure, **stampa il confronto fra la formula ricavata a mano e il valore restituito dalla
simulazione**.

## Corrispondenza con la tesina

| Notebook | Sezioni | Che cosa contiene |
|---|---|---|
| `01_circuiti_universali.ipynb` | 3, 6 | Permutazione dei modi; beam splitter regolabile e verifica della legge $\sin^2(\theta/2)$; corrispondenza fra la convenzione della tesina e quella di `BS(theta=...)`; reti universali a tre e a quattro modi con il relativo conteggio dei parametri |
| `02_ottimizzazione.ipynb` | 6 | Ricerca numerica delle fasi che massimizzano una transizione assegnata: ingresso $\lvert 1,1,1,0\rangle$, uscita $\lvert 0,0,0,3\rangle$, confronto con il massimo teorico $3!\,(1/3)^3 = 2/9$ |
| `03_interferometro_ciclico.ipynb` | 7, 8 | Le quattro coincidenze al variare della fase e della visibilità; campionamento poissoniano con barre d'errore e verifica della copertura a una deviazione standard; stima della visibilità da un campione finito e decadimento dell'incertezza come $1/\sqrt{N}$ |

## Risultati delle verifiche

Valori ottenuti nell'ultima esecuzione, riportati per esteso dentro i notebook:

| Verifica | Scarto |
|---|---|
| Unitarietà delle reti a tre e quattro modi | $1.1\cdot10^{-16}$ |
| Convenzione della tesina contro `BS(theta=...)`, con $\Theta = \pi - \theta$ | esatta su tutti i valori saggiati |
| Massimo di $\lvert 1,1,1,0\rangle \to \lvert 0,0,0,3\rangle$ contro $2/9$ | $2.6\cdot10^{-13}$ |
| Coincidenze del ciclico contro $(1 \mp \cos\varphi)/8$ | $8.3\cdot10^{-17}$ |
| Copertura della barra d'errore a una deviazione standard | 67.7 % contro il 68 % atteso |

## Requisiti ed esecuzione

```bash
pip install -r requirements.txt
jupyter lab
```

I notebook sono autonomi e vanno eseguiti dall'alto verso il basso. Nel codice i modi sono
numerati a partire da zero, come richiede Perceval; nel testo della tesina e nelle figure la
numerazione parte da uno.

Versioni impiegate nell'ultima esecuzione: Python 3.13, Perceval 1.3.1, NumPy 2.5, SciPy,
Matplotlib 3.11.
