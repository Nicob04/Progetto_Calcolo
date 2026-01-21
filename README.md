# PROGETTO Interpolazione Polinomiale con Nodi di Leja Approssimati

## Contesto

Questo progetto implementa l'interpolazione polinomiale usando **nodi di Leja approssimati** su un intervallo (I = [a, b]). I nodi di Leja offrono ottime proprietà di **stabilità e convergenza** rispetto ai nodi equispaziati, ma la loro estrazione diretta è computazionalmente costosa.
Per ovviare a questo, si calcolano nodi di Leja su una **mesh discreta** dell’intervallo, approssimando il massimo del determinante della matrice di Vandermonde tramite algoritmi efficienti.

## Funzionalità principali

1. **Calcolo dei punti di Leja approssimati**

   * **DLP(x, d)**: Estrae (d+1) punti di Leja da un vettore di punti `x` massimizzando la produttoria (\prod_{i=0}^{s-1} |x_s - \xi_i|).
   * **DLP2(x, d)**: Versione efficiente che utilizza la **fattorizzazione LU** della matrice di Vandermonde costruita con polinomi di Chebyshev.

2. **Calcolo della costante di Lebesgue**

   * **leb_con(z, x)**: Calcola la costante di Lebesgue per un insieme di nodi `z` valutando la funzione di Lebesgue sui punti `x`.
   * Valuta la **stabilità dell’interpolante** senza cicli annidati, usando il massimo dei valori assoluti dei polinomi di Lagrange.

## Sperimentazioni

* Si confrontano i due algoritmi di calcolo dei nodi di Leja in termini di **tempi computazionali** al variare del grado (d = 1, \dots, 50).
* Si verifica la **stabilità dell’interpolante** tracciando la costante di Lebesgue in scala semilogaritmica.
* Si confronta l’interpolante sui nodi di Leja con quello sui nodi equispaziati usando la funzione (f(x) = \frac{1}{x - 1.3}), costruendo la matrice di Vandermonde con polinomi di Chebyshev e risolvendo il sistema lineare delle condizioni di interpolazione.

## Tecnologie

* **Matlab** per implementazione numerica e visualizzazione dei risultati.
* Algoritmi ottimizzati per gestire elevati gradi di polinomi e ridurre il costo computazionale.

#AUTORI
Beltrame Nicolò
Biba Giovanni


