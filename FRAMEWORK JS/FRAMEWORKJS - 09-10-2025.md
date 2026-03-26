## 1. Pourquoi utiliser un Framework ?

En JS natif (Vanilla), manipuler le DOM (le HTML) est lourd et peu performant dès que l'application grandit. Un framework permet de :

- **Gérer l'état (State)** : Quand une donnée change, l'interface se met à jour toute seule.
    
- **Réutiliser du code** : On crée des composants (boutons, barres de navigation) utilisables partout.
    
- **Organiser le projet** : Structure stricte pour travailler en équipe.
    

---

## 2. Le concept de Composant

Un framework découpe l'interface en une **hiérarchie de composants**. Chaque composant est autonome et possède sa propre logique.

---

## 3. Le DOM Virtuel (Virtual DOM)

C'est la technologie clé de frameworks comme React ou Vue pour la performance :

1. Le framework crée une copie "légère" du HTML en mémoire (le Virtual DOM).
    
2. Lors d'une modification, il compare cette copie avec le vrai HTML.
    
3. Il ne met à jour **que l'élément qui a changé**, au lieu de recharger toute la page.
    

---

## 4. Les concepts techniques communs

### A. Le State (L'état)

C'est la "mémoire" du composant. Si `compteur = 0` et qu'une fonction fait `compteur++`, le framework détecte le changement et réaffiche le chiffre à l'écran instantanément.

### B. Les Props (Propriétés)

C'est la manière de faire passer des données d'un composant parent à un composant enfant.

> _Exemple : Un composant `Liste` envoie le nom d'un article à un composant `Produit`._

### C. Le Cycle de vie (Lifecycle)

Chaque composant passe par des étapes :

1. **Mounting** : Création et apparition à l'écran.
    
2. **Updating** : Mise à jour suite à un changement de donnée.
    
3. **Unmounting** : Destruction (quand on change de page).
    

---

## 5. Comparaison rapide

|**Framework**|**Créateur**|**Courbe d'apprentissage**|**Points forts**|
|---|---|---|---|
|**React**|Meta (Facebook)|Moyenne|Écosystème immense, très flexible.|
|**Vue.js**|Communauté|Facile|Très intuitif, documentation excellente.|
|**Angular**|Google|Difficile|Complet, structuré pour les très gros projets.|
