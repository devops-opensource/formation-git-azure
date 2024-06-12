# Contexte
## But du laboratoire
### Quoi

Éditer l'historique de notre dépôt pour retirer des modifications.

### Pourquoi

Pouvoir corriger des erreurs et supprimer des données qui ne devraient pas apparaitre dans le dépôt.

### Remarque

Nous ne passerons ici que par des lignes de commandes. En effet, l'édition de l'historique avec des commandes comme reset pouvant être dangereux, nous préférons avoir un contrôle total sur ce que nous faisons.

# Instructions

## Corriger notre commit précédent

Nous allons commencer par ajouter une nouvelle ligne dans index.html, pour l'exemple ajoutons "Toto n'aime pas l'école".
Commitons ce changement comme d'habitude.
Mais finalement nous ne voulons pas commiter cette ligne, mais plutôt "Toto aime l'école".
Éditez la ligne dans index.html puis ajouter ce changement à la staging area avec la commande add mais ne le commitez pas!
Nous allons éditer le commit précédent avec la commande suivant:
```bash
git commit --amend -m "Toto aime l'école"
```	

## Effacer totalement une information

Dans certains cas on a besoin de pouvoir totalement supprimer une information de l'historique de git, comme par exemple un mot de passe ou une information confidentielle.
Pour cela on peut utiliser git reset --hard. C'est une commande dangereuse, à n'utiliser qu'en cas d'urgence.

Pour l'exercice nous allons ajouter un nouveau fichier qui contient un faux mot de passe.
Commitez ce fichier et pousser le vers le repo distant.

Nous allons maintenant faire un autre commit où nous allons ajouter une ligne dans index.html.

Nous allons retirer le fichier avec le mot de passe de l'historique:
- on commence par faire git log pour chercher le numéro du commit juste avant qu'on ajoute le mot de passe
- on utilise alors:
```bash
git reset --hard <commit>
```	
- Si on regarde maintenant dans notre espace de travail, le fichier à disparu, mais la modification à index.html aussi
- Si on refait un git log, on remarquera aussi que les commits associés à l'ajout du mot de passe et la modification à index.html ont disparu


# Conclusion
### État du laboratoire
A la fin de ce laboratoire vous devriez savoir:
- Modifier le dernier commit effectué
- Supprimer des commits de l'historique