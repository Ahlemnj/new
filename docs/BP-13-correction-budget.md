# BP-13 – Correction : recalcul du budget restant après suppression d'une dépense

- Incident support : BPS-1
- Story concernée : BP-4 (critère d'acceptation n°2)

## Analyse
Le recalcul du restant n'était déclenché qu'à l'ajout d'une dépense.

## Correction (pseudo-code)
```
onDepenseSupprimee(depense):
    categorie.restant += depense.montant
    budget.restantGlobal += depense.montant
    rafraichirTableauDeBord()
```

## Test de non-régression
Budget Traiteur 8 000 TND → ajout 2 500 → restant 5 500 → suppression → restant 8 000.
