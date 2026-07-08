# Progetto 1 - Metodi del Calcolo Scientifico

**Autori:**
- Matias Bonoli (matricola 912941)
- Ashley Chudory (matricola 935003)
- Daniele Maccagnan (matricola 945269)

Mini libreria per sistemi lineari.

Implementazione Python dei quattro metodi iterativi richiesti dal progetto:

- Jacobi
- Gauss-Seidel
- Gradiente
- Gradiente coniugato

## Dipendenze

```bash
python -m pip install -r requirements.txt
```

## Esecuzione completa

Dalla cartella del progetto:

```bash
python src/run_assignment.py
```

Questo comando usa tutti i file `.mtx` presenti nella cartella `dati` e le
tolleranze `1e-4`, `1e-6`, `1e-8`, `1e-10`.

Gli output vengono salvati in:

- `results/results.csv`
- `results/plots/relative_error.png`
- `results/plots/iterations.png`
- `results/plots/time.png`

## Esecuzione su una matrice o tolleranza specifica

```bash
python src/run_assignment.py --matrix dati/vem1.mtx --tol 1e-4
```

Si possono indicare piu' matrici o piu' tolleranze ripetendo gli argomenti:

```bash
python src/run_assignment.py --matrix dati/vem1.mtx --matrix dati/vem2.mtx --tol 1e-4 --tol 1e-6
```

Per generare solo il CSV senza grafici:

```bash
python src/run_assignment.py --no-plots
```

Per usare un solo metodo:

```bash
python src/run_assignment.py --method conjugate-gradient
```

I metodi disponibili sono `jacobi`, `gauss-seidel`, `gradient` e
`conjugate-gradient`. Si possono indicare piu' metodi ripetendo l'argomento.

## Test veloci

```bash
python src/test_assignment.py
```

I test controllano parser MatrixMarket, convergenza su matrice tridiagonale
tramite SciPy, convergenza su matrice tridiagonale SPD, e gradiente coniugato
in al piu' `n` iterazioni su un sistema piccolo.
