<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&pause=1000&color=00C2FF&center=true&vCenter=true&width=700&lines=Apprentissage+Docker" alt="Typing SVG" />
</div>
<p align="center">
  <img src="../img/docker_img.png" >  
</p>

# 🐳 Apprentissage Docker 
    
![Docker](https://img.shields.io/badge/Docker-🐳-blue) 
    
Ce document présente les commandes et concepts Docker que j’ai explorés et testés aujourd’hui sous Windows, avec des bonnes pratiques et observations pour un usage professionnel.
    
---
    
## 🎯 Objectifs de la session
 - Lancer et interagir avec des conteneurs Ubuntu  
 - Comprendre la gestion des conteneurs (`start`, `stop`, `rm`, `exec`)  
 - Installer et tester des logiciels dans un conteneur  
 - Se familiariser avec les options `-it` et `--rm`  
    
---
    
## 1️⃣ Lancer et interagir avec des conteneurs
```bash
    # Lancer un conteneur Ubuntu
    docker run ubuntu:24.10
    
    # Lancer un conteneur en mode interactif avec terminal
    docker run -it ubuntu:24.10
    
    # Lancer un conteneur interactif et le supprimer automatiquement à la fermeture
    docker run -it --rm ubuntu:24.10
    docker run -it --rm ubuntu
```

* * *

2️⃣ Lister les conteneurs
-------------------------

    # Conteneurs en cours d'exécution
    docker ps
    
    # Tous les conteneurs, y compris ceux arrêtés
    docker ps -a
    

* * *

3️⃣ Gérer les conteneurs
------------------------

    # Démarrer un conteneur existant
    docker start 
    
    # Arrêter un conteneur
    docker stop 
    
    # Supprimer un conteneur
    docker rm 
    
    # Accéder à un conteneur en mode terminal
    docker exec -it  bash
    
    # Créer un fichier dans un conteneur
    docker exec  touch main.js
    

* * *

4️⃣ Installer des logiciels dans un conteneur
---------------------------------------------

    # Mettre à jour la liste des paquets
    apt update
    
    # Installer Vim
    apt install -y vim
    
    # Installer PHP
    apt install -y php
    

* * *

5️⃣ Observations et bonnes pratiques
------------------------------------

*   `-it` : active le terminal interactif pour interagir avec le conteneur
    
*   `--rm` : supprime automatiquement le conteneur à la fermeture
    
*   Les conteneurs doivent être arrêtés avant suppression
    
*   `docker exec` : manipule directement le système de fichiers d’un conteneur en cours
    
*   Pour un conteneur persistant, utiliser `docker start` pour le relancer
    

* * *

6️⃣ Conclusion
--------------

Aujourd’hui, j’ai consolidé ma compréhension de **Docker** :

*   Gestion complète des conteneurs Ubuntu
    
*   Installation et configuration de logiciels à l’intérieur d’un conteneur
    
*   Meilleure maîtrise des options pour un usage interactif et reproductible
    

Ce savoir-faire est essentiel pour créer des environnements de développement portables, automatisables et prêts pour la production.

* * *

📂 À venir
----------

*   Tester la création de **Dockerfile** pour automatiser la configuration de conteneurs
    
*   Explorer la **connexion réseau entre conteneurs**
    
*   Expérimenter le **volume Docker** pour la persistance des données
    

    
    ---
   
