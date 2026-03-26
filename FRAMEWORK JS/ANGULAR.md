## 1. Qu'est-ce qu'Angular ?

Angular est un framework **SPA** (_Single Page Application_). Contrairement à un site classique, il ne recharge pas la page entière à chaque clic ; il modifie dynamiquement le contenu.

### Les piliers d'Angular :

- **TypeScript** : Le langage de base (une surcouche de JavaScript qui ajoute du typage).
    
- **Composants** : Les briques de construction de l'interface.
    
- **Modularité** : Le code est organisé en blocs réutilisables.
    

---

## 2. L'Architecture : Le Composant

Tout dans Angular est un **Component**. Un composant est composé de quatre fichiers :

1. **`.html`** : La structure (le template).
    
2. **`.css`** : Le style.
    
3. **`.ts`** : La logique (données et fonctions).
    
4. **`.spec.ts`** : Les tests unitaires.
    

---

## 3. Le Data Binding (Liaison de données)

C'est la façon dont le code TypeScript communique avec le HTML.

- **Interpolation `{{ }}`** : Afficher une variable du TS dans le HTML.
    
    - _Ex: `<h1>{{ title }}</h1>`_
        
- **Property Binding `[ ]`** : Modifier un attribut HTML depuis le TS.
    
    - _Ex: `<img [src]="userImageUrl">`_
        
- **Event Binding `( )`** : Déclencher une fonction TS depuis un clic HTML.
    
    - _Ex: `<button (click)="onSave()">Enregistrer</button>`_
        
- **Two-way Binding `[( )]`** : Synchronisation en temps réel (souvent pour les formulaires).
    

---

## 4. Les Directives de base

Les directives modifient le comportement ou l'affichage du DOM (le HTML).

- **`*ngIf`** : Affiche un élément seulement si une condition est vraie.
    
    HTML
    
    ```
    <p *ngIf="isLoggedIn">Bienvenue, utilisateur !</p>
    ```
    
- **`*ngFor`** : Répète un élément pour chaque item d'une liste.
    
    HTML
    
    ```
    <ul>
      <li *ngFor="let item of items">{{ item }}</li>
    </ul>
    ```
    

---

## 5. Les Services et l'Injection de Dépendances

Un **Service** est une classe dédiée à la gestion des données (ex: appels API). On ne met jamais la logique de récupération de données directement dans un composant pour garder le code propre et partageable.

L'**Injection de Dépendances** permet à Angular de fournir automatiquement une instance du service à n'importe quel composant qui en a besoin.

---

## 6. Créer son premier projet

Pour commencer, vous devez installer l'interface de ligne de commande (CLI) :

1. **Installation** : `npm install -g @angular/cli`
    
2. **Nouveau projet** : `ng new mon-projet`
    
3. **Lancer le serveur** : `ng serve` (disponible sur `http://localhost:4200`)
    
4. **Créer un composant** : `ng generate component mon-composant`