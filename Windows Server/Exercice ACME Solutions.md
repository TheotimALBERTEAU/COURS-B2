
# Mission 1 : Analyse des besoins & rédaction d'un mini cahier des charges

## Risques actuels sur les postes clients

#### - Sécurité : 
	- Logiciels non contrôlés
	- Manque de contrôle des navigateurs
	- Accès au CMD / à PowerShell
	- USB activé donc possibilité d'installation de virus

#### - Configuration et Productivité
	- Maintenance difficile et longue
	- Incidents techniques

## Objectifs techniques 

#### - Renforcer la sécurité :
	- Désactiver les ports USB, le CMD, le PowerShell
	- Verrouiller automatiquement les sessions inactives
	- Réduire l'accès aux navigateurs
#### - Homogénéité :
	- Imposer un environnement de travail identique pour tous les employés (Fond d'écran, applications)

## Plan de déploiement des GPO

| OU             | Users                                         | GPO                                                                            |
| -------------- | --------------------------------------------- | ------------------------------------------------------------------------------ |
| Administrateur | Postes des Administrateurs Systèmes           | Possibilité de faire ce qu'il veut,<br>Aucune restriction                      |
| DSI            | Postes de l'équipe DSI                        | Peux de restrictions pour plus de<br>flexibilité                               |
| Personnel      | La majorité des postes, <br>pour les employés | Beaucoup de restrictions, <br>que ce soit pour l'homogénéité<br>ou la sécurité |

# Mission 2 : Recherche & sélection des GPO pertinentes

## Sécurité des postes 

| GPO                                 | Objectif                                                                              | Cible            | Explication                                                                                                       |
| ----------------------------------- | ------------------------------------------------------------------------------------- | ---------------- | ----------------------------------------------------------------------------------------------------------------- |
| Sécurité du Navigateur              | Forcer l'utilisation d'un seul navigateur sécurisé                                    | Personnel        | Sécuriser la navigation et les recherches sur des sites web possiblement dangereuses                              |
| Blocage d'outils avancés            | Empêche le Personnel d'utiliser des outils comme le CMD ou PowerShell                 | Personnel        | Réduit le risque d'exécution de scripts dangereux                                                                 |
| Interdiction des clés USB           | Bloque l'accès en écriture/lecture à toute clés USB                                   | Tout les  postes | Empêcher le transfert de virus ou exécutable dangereux avec des disques durs amovibles                            |
| Verrouillage automatique des postes | Impose un écran de veille après un certain temps d'inactivité                         | Tout les  postes | Assure la confidentialité des données sensibles pendant l'absence d'un utilisateur                                |
| Antivirus quotidien forcé           | S'assure que Windows defender est actif et effectue bien les vérifications            | Tout les  postes | Maintien un niveau élevé de sécurité de base des postes                                                           |
| Restriction paramètres système      | Empêche l'utilisateur d'accéder aux paramètres Windows et au panneau de configuration | Personnel        | Garantit l'homogénéité des postes de tout le personnel et limite les incidents liés à des mauvaises manipulations |
## Corporatisme & identité visuelle

| GPO                                   | Objectif                                                                                     | Cible            | Explication                                                                    |
| ------------------------------------- | -------------------------------------------------------------------------------------------- | ---------------- | ------------------------------------------------------------------------------ |
| Fond d'écran de l'entreprise          | Impose un fond d'écran ACME Solutions                                                        | Tout les  postes | Renforce l'identité visuelle de l'entreprise et le professionnalisme           |
| Message légal au démarrage            | Affiche un avertissement légal sur l'utilisation du matériel avant l'ouverture de la session | Tout les  postes | Conformité légale et sensibiliser sur la propriété du matériel                 |
| Blocage du store d'applications       | Désactive complètement l'accès au Microsoft store                                            | Tout les  postes | Empêche l'installation d'applications non autorisés                            |
| Installation automatique de logiciels | Déploie les logiciels métiers essentiels au démarrage du poste                               | Tout les  postes | Assure que chaque poste possède bien tous les logiciels requis pour travailler |

# Mission 3 : Déploiement concret du POC

 > [!WARNING]  Avant de créer des groupes ou des GPO, vous devez avoir un Active Directory actif, pour en faire un, allez sur ce [GitHub](https://github.com/Yndral-c/ActiveDirectory)
 > Pour notre cas, nous allons utiliser un Windows Server et un Windows Client

## Comment créer une GPO 

Voila un exemple de création de GPO, notamment celle-ci, pour empêcher le Personnel d'accéder au terminal.

Aller dans le **tableau de bord** du gestionnaire de serveur -> Outils -> Gestion des stratégies de groupe (Vos groupes auront été créés préalablement sinon voir [[#Créer des groupes d'administration]])
![[Pasted image 20251205131824.png]]

Dans la **Gestion de stratégie de groupe** ouvrir Forêt : *domaine* -> Domaines -> *domaine* -> Clic droit sur le groupe dans lequel vous voulez ajouter la GPO -> **Créer un objet GPO...**
![[Pasted image 20251205131937.png]]

Une fenêtre s'ouvre et vous y mettez le nom de votre **GPO** -> OK
![[Pasted image 20251205131944.png]]

Après la création de la GPO -> Objets de stratégie -> Clic droit sur la GPO -> **Modifier**
![[Pasted image 20251205132122.png]]

Une fenêtre s'ouvre -> Configuration Utilisateur -> Stratégies -> Modèles d'administration -> Système -> Clic droit sur **Désactiver l'accès à l'invite de commandes** -> Modifier
![[Pasted image 20251205132253.png]]

Cliquer sur **Activer** -> Appliquer -> OK
![[Pasted image 20251205132345.png]]


# Créer des groupes d'administration

Aller dans le **Gestionnaire de Serveur** -> Tableau de bord -> Outils -> **Utilisateurs et Ordinateurs Active Directory**
![[Pasted image 20251205140049.png]]

Choisir **votre domaine** -> Clic droit -> Nouveau -> Unité d'Organisation
!![[Pasted image 20251205144003.png]]

Nouvelle Fenêtre -> Choisir le nom de l'OU -> OK
![[Pasted image 20251205144615.png]]

## 1 - Créer une OU POC-GPO 

Je crée l'OU
![[Pasted image 20251205144339.png]]

## Ajouter un poste et un utilisateur de test

J'ajoute un poste *POC_GPO_POSTE*
![[Pasted image 20251205144905.png]]

Et un Utilisateur *test*
![[Pasted image 20251205145021.png]]

Je définie le *mdp* et je décide que cet utilisateur ne pourra jamais le changer
![[Pasted image 20251205145104.png]]

Je clique sur **Terminer**
![[Pasted image 20251205145122.png]]

Le poste et l'utilisateur ont bien été instaurés à l'OU
![[Pasted image 20251205145142.png]]

