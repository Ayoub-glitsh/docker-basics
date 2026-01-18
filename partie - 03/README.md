



# 🐳 Apprentissage Docker – Volumes Mappés (Bind Mounts)
    
Aujourd’hui, j’ai appris à utiliser les **volumes mappés (bind mounts)** dans Docker afin de partager des fichiers entre la machine hôte (Windows) et un conteneur Ubuntu.
    
 ---
    
## 🎯 Objectif
  - Mapper un dossier local vers un conteneur Docker  
  - Vérifier la persistance des fichiers  
  - Modifier un fichier depuis le conteneur et voir les changements sur l’hôte  
    
    ---
    
## 1️⃣ Préparation du dossier local (Windows)
  ```bash
    mkdir test
    cd test
    type nul > index.html
    echo coucou >> index.html
    type index.html
```  

* * *

2️⃣ Lancer un conteneur avec un volume mappé
--------------------------------------------

    docker run -it --rm -v C:\Users\HP\Desktop\test:/test-container ubuntu
    

➡️ Le dossier local est monté dans le conteneur à :

    /test-container
    

* * *

3️⃣ Accès et lecture des fichiers dans le conteneur
---------------------------------------------------

    cd test-container
    ls
    cat index.html
    

* * *

4️⃣ Installation d’un éditeur dans le conteneur
-----------------------------------------------

    apt update
    apt install nano
    

* * *

5️⃣ Modification du fichier depuis le conteneur
-----------------------------------------------

    nano index.html
    cat index.html
    

Contenu modifié :

    

coucou Ayoub


    

* * *

6️⃣ Vérification sur la machine hôte (Windows)
----------------------------------------------

    type index.html
    

✅ Le fichier est modifié côté hôte, ce qui confirme que le **volume mappé fonctionne correctement**.

* * *

📌 Ce que j’ai appris aujourd’hui
---------------------------------

*   Un **bind mount** permet de partager un dossier entre l’hôte et le conteneur
    
*   Les fichiers sont synchronisés en temps réel
    
*   Les données persistent même après l’arrêt du conteneur
    
*   Très utile pour le développement et les tests
    

* * *

✅ Conclusion
------------

Les volumes mappés sont essentiels pour travailler efficacement avec Docker, notamment pour modifier des fichiers localement tout en exécutant l’application dans un conteneur.

    
    
