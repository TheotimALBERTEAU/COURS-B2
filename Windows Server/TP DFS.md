# Installation de DFS

Dans le gestionnaire de serveur -> Gérer -> **Ajouter des rôles et fonctionnalités**
![[Pasted image 20251215103557.png]]

Appuyer sur **suivant** 
![[Pasted image 20251215103806.png]]

Garder l'installation basée sur un rôle ou une fonctionnalité -> **suivant**
![[Pasted image 20251215103829.png]]

Garder sur *Sélectionner un serveur du pool de serveurs* -> **suivant**
![[Pasted image 20251215103905.png]]

Aller dans *Services de fichiers et de stockage* -> Services de fichiers et iSCSI -> Cocher **Espaces de noms DFS**
![[Pasted image 20251215103955.png]]

Une fenêtre s'ouvre -> **Ajouter de fonctionnalités**
![[Pasted image 20251215104009.png]]

Appuyer sur **Installer**
![[Pasted image 20251215104059.png]]

A la fin de l'installation -> **Fermer**
![[Pasted image 20251215104901.png]]

# Configuration du Serveur DFS

## Créer une racine DFS

Dans le Gestionnaire de serveur -> Outils -> **Gestion du système de fichiers distribués DFS**
![[Pasted image 20251215110244.png]]

Clic droit sur les Espaces de noms -> **Nouvel espace de noms...**
![[Pasted image 20251215110250.png]]

Dans l'input -> NOM_DE_LA_MACHINE.domain.local -> **Suivant >**
![[Pasted image 20251215110507.png]]

Dans l'input du Nom -> **Nom de votre espace** -> Suivant 
![[Pasted image 20251215110543.png]]

Garder les paramètres de base -> **Suivant**
![[Pasted image 20251215110604.png]]

Puis **Créer**
![[Pasted image 20251215110617.png]]

