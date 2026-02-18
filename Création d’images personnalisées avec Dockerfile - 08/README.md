
# 🐳 Cours Docker – Créer une image personnalisée
<center>
<img src="../img/Dockerfile.png" alt="Docker Image" />
</center> 
    
   ## 📅 Cours d’aujourd’hui
  **Thème : Créer une image Docker personnalisée**
    
  Ce cours a pour objectif d’apprendre à créer sa propre image Docker à l’aide d’un **Dockerfile**, en partant d’une image existante et en y ajoutant des outils personnalisés.
    
  ---
    
  ## 🎯 Objectifs du cours
    
  - Comprendre le rôle d’une image Docker
  - Apprendre à écrire un Dockerfile
  - Créer une image Docker personnalisée
  - Installer des dépendances dans une image
  - Builder une image Docker localement
    
    ---
    
  ## 📘 Notions clés
    
  ### 🔹 Image Docker
  Une image Docker est un modèle immuable utilisé pour créer des conteneurs.  
    Elle est construite à partir d’un **Dockerfile**.
    
---
    
  ### 🔹 Dockerfile
  Un **Dockerfile** est un fichier texte qui contient une suite d’instructions permettant à Docker de construire une image.
    
  Instructions vues aujourd’hui :
    - `FROM`
    - `RUN`
    
---
    
  ## 🧱 Création d’une image personnalisée
    
  ### 📄 Dockerfile utilisé
    
  ```Dockerfile
    FROM celtak/ubuntu-ping-ip
    RUN apt update
    RUN apt install -y nodejs
```
    
### 🔍 Explication des instructions

*   `FROM celtak/ubuntu-ping-ip`  
    → Définit l’image de base (Ubuntu)
    
*   `RUN apt update`  
    → Met à jour la liste des paquets
    
*   `RUN apt install -y nodejs`  
    → Installe Node.js dans l’image
    

* * *

⚙️ Construction de l’image
--------------------------

Commande utilisée :

    docker build -t ubuntu_nodejs .
    

*   `-t ubuntu_nodejs` : nom de l’image
    
*   `.` : dossier courant contenant le Dockerfile
    

* * *

✅ Résultat obtenu
-----------------

*   ✔️ Image Docker personnalisée créée
    
*   ✔️ Node.js installé dans l’image
    
*   ✔️ Image prête à être utilisée pour des projets Node.js
    
*   ✔️ Compréhension du processus de build Docker
    

* * *

🧪 Vérification
---------------

    docker images
    

Permet de vérifier que l’image `ubuntu_nodejs` a bien été créée.

* * *

