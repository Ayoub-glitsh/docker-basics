


  # 🐳 Docker – Volumes mappés et managés avec Docker Compose
    
  ## 📅 Thème de la session
  **Docker : gestion des volumes mappés (bind mount) et volumes managés dans `compose.yml`**
    
  Cette session avait pour objectif de comprendre **comment partager et persister les données** entre la machine hôte et un conteneur Docker à l’aide de **Docker Compose**.
    
  ---
    
  ## 🎯 Objectifs de la session
    
  - Comprendre le rôle des volumes Docker
  - Différencier volume mappé et volume managé
  - Configurer les volumes dans un fichier `compose.yml`
  - Vérifier la persistance des données
  - Gérer le cycle de vie des volumes
    
    ---
    
    ## 📘 Notions clés
    
    ### 🔹 Volume Docker
    Un volume permet de **conserver les données** même si le conteneur est arrêté ou supprimé.
    
    ---
    
    ## 1️⃣ Volume mappé (Bind Mount)
    
    Un **volume mappé** relie un dossier local de la machine hôte à un dossier dans le conteneur.
    
    ### Exemple dans `compose.yml`
    
    ```yml
    services:
      my_ubuntu:
        image: celtak/ubuntu-ping-ip
        container_name: celtak_ubuntu
        stdin_open: true
        tty: true
        volumes:
          - ./data:/data-dans-le-conteneur
    

### 🔍 Explication

*   `./data` → dossier sur la machine hôte
    
*   `/data-dans-le-conteneur` → dossier dans le conteneur
    

➡️ Tout fichier créé dans l’un apparaît automatiquement dans l’autre.

* * *

2️⃣ Volume managé (Named Volume)
--------------------------------

Un **volume managé** est créé et géré par Docker.  
Il n’est pas directement lié à un dossier visible sur la machine.

### Exemple dans `compose.yml`

    services:
      my_ubuntu:
        image: celtak/ubuntu-ping-ip
        container_name: celtak_ubuntu
        volumes:
          - test_volume:/test-volume-dans-le-conteneur
    
    volumes:
      test_volume:
    

### 🔍 Explication

*   `test_volume` → volume Docker managé
    
*   `/test-volume-dans-le-conteneur` → chemin dans le conteneur
    

➡️ Les données persistent même après suppression du conteneur.

* * *

3️⃣ Commandes utilisées pendant la session
------------------------------------------

    docker compose up -d
    docker ps
    docker exec -it celtak_ubuntu bash
    docker compose stop
    docker compose rm
    docker volume ls
    

* * *

4️⃣ Vérification de la persistance des données
----------------------------------------------

*   Création d’un fichier dans le conteneur :
    

    touch main.js
    

*   Le fichier est :
    
    *   visible dans le dossier local (volume mappé)
        
    *   conservé même après suppression du conteneur (volume managé)
        

* * *

✅ Résultats de la session
-------------------------

*   ✔️ Compréhension des volumes Docker
    
*   ✔️ Utilisation de volumes mappés pour le développement
    
*   ✔️ Utilisation de volumes managés pour la persistance
    
*   ✔️ Maîtrise de la configuration dans `compose.yml`
    

* * *



