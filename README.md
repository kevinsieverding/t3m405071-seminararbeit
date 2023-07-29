# T3M405071 Semniararbeit

Titel: Optimierung von Lieferantenwahl zur Maximierung von Resilienz in Lieferketten

## Notizen

- Zielfunktion
- Encodierung der Daten

  - n-Vektor mit rationalen zahlen
  - optimierungsfunktion polynom n-ter ordnung
  - Ziel ist es die passenden gewichte zu finden

- Optimierungsverfahren
  - Lokale Suche
    - Deterministisch
      - Hill Climbing
      - Gradient Descent
  - Probabilistisch
    - Iterated Local Search
  - Globale Suche
    - Deterministisch
      - Branch and Bound
      - Linear Optimization
    - Probabilistisch
      - Genetische Algorithmen
- Lokale Optimierung

Lieferant A:
Preis bis 1000 Stück: 10€
Preis von 1000 Stück bis 2000 Stück: 9€
Preis ab 2000 Stück: 8€
Maximale Kapazität: 4000 Stück
Beziehungsindex: 0 - 1
Risiko:

- Qualitätsrisiko
- Mengenrisiko
- Terminrisiko

Ziel: Minimierung der Kosten unter Berücksichtigung von Beziehungs- und Qualitätsindex

```text
selection = []                  # list of selected suppliers
x = []                          # list of ordered quantities per supplier
sum = 0                         # sum of ordered quantities      
inc = X / a                     # increment for each iteration
best = 0                        # best value so far

function addToSupplier(inc):
  i = random(1, n)              # pick random supplier
  if S_i not in selection:      # add supplier to current selection if not already present
    add S_i to selection
  if x_i + inc > M_i:           # check if increment would exceed capacity
    inc = inc - (M_i - x_i)     # reduce increment by delta
    x_i = M_i                   # set capacity to maximum
    addToSupplier(inc)          # add remaining increment to another supplier
  else:
    x_i = x_i + inc             # add increment to supplier

while (sum < X):
  addToSupplier(inc)
  current = Z(selection)
  if (current < best):
    reset(selection, x)
  else:
    best = current
    sum = sum + inc
```

## Features

- Pre-configured to comply with the design guidelines for academic papers in the Wirtschaftsinformatik course of study at DHBW CAS.
- GitHub Template Repository to easily jumpstart a new document.
- GitHub Actions Workflow to build the document and attach the PDF as a realease to the repository when new tags are pushed.

  **Example**:

  ```bash
  # do some changes...
  git commit          # commit your changes
  git tag 1.0         # set a tag
  git push            # push your changes
  git push origin 1.0 # push the tag
  ```
  
  When the tag is pushed a new workflow is triggered that will build the document and create a new release with the PDF as an attached asset using the tag that you have set.
- The LaTeX package [`minted`](https://ctan.org/pkg/minted) for beautifully colored code listings.

  - `python` and the package `Pygments` are required.
  - The PDF needs to be build with the `--shell-escape` flag.
  
  Check the package documentation for further details.
