
# Utilisations :

#### Administration 
serveur : installation, backup, update, synchronisation

#### Services récurrents 
Tâche à exécuter toutes les X heures

#### DevOps
CI/CD

#### Automatisation

#### Adaptation


# Syntaxe :

Variables bash = *bizarres et problématiques*

```
MY_VAR1="toto"           # Valeur fixe
MY_VAR2=$(my_command)    # Récupère le résultat de 'my_command'
MY_VAR3=                 # Valeur vide totallement acceptée
MY_VAR4="tutu $(MY_VAR2) TOTO" 
export MY_VAR5="titi"    # Valeur disponible pour tout processus créé par le shell courant
```


```
if my_command; then     # si la commande s'éxecute sans erreur
	echo "toto";        # afficher toto
fi

if ! my_command; then   # si la commande retourne une erreur
	exit 1;             # Exit: la commande quitte le shell actuel
fi
```

Chaque commande se termine par ";" SAUF si on passe une ligne  à la fin

La syntaxe ``` echo "toto" ; if [ -f /tmp/test]; then echo "tutu";``` 
