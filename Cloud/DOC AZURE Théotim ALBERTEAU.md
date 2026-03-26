# Créer une ressource
![[Pasted image 20260227134405.png]]

# Créer une VM
![[Pasted image 20260227133249.png]]

# Se connecter en SSH
![[Pasted image 20260227134555.png]]
![[Pasted image 20260227133340.png]]

# Installer GIT sur la VM apache2 php php-mysql default-mysql-client
![[Pasted image 20260227134745.png]]

# Vérifier et ajouter le port http sur votre VM
![[Pasted image 20260227134819.png]]

# Créer un projet
![[Pasted image 20260227134845.png]]

# Pousser votre code dans le dépot
## Pousser votre code dans le dépot
```
git init
git config --global user.email "youenn@mail.com"
git config --global user.name "YDU"
git add .
git commit -m "first commit"
git remote add origin git@ssh.dev.azure.com:v3/TPAzureMRO/websiteMRO/websiteMRO
git push -u origin --all
```
![[Pasted image 20260227135400.png]]
# Remplir le docker file
![[Pasted image 20260227135420.png]]

# Pousser le docker file
```bash
git add .
git commit -m "Add Dockerfile"
git push
```

#  Créer une container registries
![[Pasted image 20260227135747.png]]

# Créer une pipeline
![[Pasted image 20260227135833.png]]

# Configurer une pipeline
![[Pasted image 20260227135848.png]]
![[Pasted image 20260227135901.png]]
![[Pasted image 20260227135909.png]]
![[Pasted image 20260227135919.png]]
![[Pasted image 20260227135939.png]]

# Build une image docker

Pour ça il faut avoir au préalablement installer docker.
J'ai utilisé cette doc : https://docs.docker.com/engine/install/debian/
```bash
docker build -t nom_de_l_image:version .
```

# Débuggé une image Docker
```bash
docker exec -it nom_du_container /bin/sh
```

# Creer un docker compose (votre image + un bdd)
![[Pasted image 20260227144108.png]]

# Que le site web soit en ligne, avec acces a la DB, ke tout avec Docker
![[Pasted image 20260227144133.png]]

# Utiliser des variables d'environnement
![[Pasted image 20260227144203.png]]