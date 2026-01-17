  


# Apprentissage Complet Docker 🐳
    
 Ce dépôt regroupe tous les concepts, commandes et bonnes pratiques pour apprendre Docker de A à Z : des bases jusqu’aux fonctionnalités avancées.
    
---
    
 ## 🎯 Objectifs
  - Maîtriser les commandes de base et avancées de Docker  
  - Comprendre les volumes et leur gestion  
  - Utiliser Docker Hub pour partager des images  
  - Mapper des ports et connecter des conteneurs  
  - Créer et gérer des réseaux personnalisés  
  - Écrire des Dockerfiles et construire des images personnalisées  
  - Déployer et organiser des conteneurs de manière professionnelle  
    
    ---
    
    ## 1️⃣ Concepts de base
    - **Image** : modèle statique pour créer un conteneur  
    - **Conteneur** : instance d’une image en cours d’exécution  
    - **Docker Hub** : registre public d’images  
    - **Volume** : espace pour stocker des données persistantes  
    - **Réseau** : permet la communication entre conteneurs  
    
    ---
    
    ## 2️⃣ Commandes de base
    ```bash
    # Vérifier l'installation
    docker --version
    docker info
    
    # Lancer un conteneur
    docker run ubuntu:24.10
    docker run -it ubuntu:24.10
    docker run -it --rm ubuntu
    
    # Lister les conteneurs
    docker ps
    docker ps -a
    
    # Gérer les conteneurs
    docker start 
    docker stop 
    docker rm 
    docker exec -it  bash
    
    # Gestion des images
    docker images
    docker rmi 
    docker build -t monimage:1.0 .
    

* * *

3️⃣ Commandes avancées
----------------------

    # Lister les volumes
    docker volume ls
    
    # Créer un volume
    docker volume create monvolume
    
    # Supprimer un volume
    docker volume rm monvolume
    
    # Mapper un volume dans un conteneur
    docker run -v monvolume:/data ubuntu
    
    # Mapper un port local vers un conteneur
    docker run -p 8080:80 nginx
    
    # Connecter un conteneur à un réseau personnalisé
    docker network create monreseau
    docker run --network monreseau ubuntu
    
    # Inspecter un conteneur
    docker inspect 
    docker logs 
    docker stats 
    

* * *

4️⃣ Docker Hub
--------------

*   **Pousser une image vers Docker Hub** :
    

    docker login
    docker tag monimage moncompte/monimage:1.0
    docker push moncompte/monimage:1.0
    

*   **Récupérer une image depuis Docker Hub** :
    

    docker pull nginx
    

* * *

5️⃣ Réseaux Docker
------------------

*   Types de réseau :
    
    *   **bridge** : réseau par défaut pour les conteneurs isolés
        
    *   **host** : le conteneur partage le réseau de l’hôte
        
    *   **overlay** : réseau pour plusieurs hôtes (Swarm)
        
*   Créer un réseau personnalisé :
    

    docker network create monreseau
    docker run --network monreseau ubuntu
    

* * *

6️⃣ Dockerfile et création d’images personnalisées
--------------------------------------------------

*   Exemple Dockerfile :
    

    # Image de base
    FROM ubuntu:24.10
    
    # Installer des logiciels
    RUN apt update && apt install -y vim php
    
    # Copier un fichier dans l’image
    COPY ./app /app
    
    # Définir la commande par défaut
    CMD ["bash"]
    

*   Construire l’image :
    

    docker build -t monimage:1.0 .
    

*   Lancer un conteneur avec cette image :
    

    docker run -it --rm monimage:1.0
    

* * *

7️⃣ Bonnes pratiques
--------------------

*   Utiliser `--rm` pour les conteneurs temporaires
    
*   Garder les images légères
    
*   Documenter les Dockerfiles
    
*   Isoler les conteneurs pour les tests et la production
    
*   Utiliser les volumes pour persister les données
    

* * *

8️⃣ Ressources complémentaires
------------------------------

*   [Documentation officielle Docker](https://docs.docker.com/)
    
*   [Docker Hub](https://hub.docker.com/)
    
*   [Tutoriels Docker 101](https://www.docker.com/101-tutorial)
    
*   [Play with Docker](https://labs.play-with-docker.com/)
    

* * *

✅ Objectif final
----------------

*   Créer des environnements de développement **reproductibles**
    
*   Déployer des applications conteneurisées
    
*   Gérer des conteneurs, images, volumes et réseaux de manière professionnelle
    

    
  
