# 🐳 Apprentissage Docker – Volumes & Bind Mounts

## 🎯 Objectif

Cette documentation résume ce que j’ai appris sur **les volumes Docker** et **les volumes mappés (Bind Mounts)**. Elle est destinée aux **débutants** qui souhaitent comprendre comment persister des données et partager des fichiers entre l’hôte et un conteneur.

---

## 🧠 Concepts clés

### 🔹 Docker Volume

Un **volume Docker** est un espace de stockage géré par Docker.

* Persistant même après la suppression du conteneur
* Stocké dans `/var/lib/docker/volumes/`
* Recommandé pour les bases de données et données applicatives

### 🔹 Bind Mount (Volume mappé)

Un **bind mount** permet de lier un dossier local (Windows/Linux) à un dossier dans le conteneur.

* Synchronisation en temps réel
* Très utile pour le développement

---

## 🛠️ Commandes apprises

### 📦 Gestion des volumes

```bash
docker volume create mon_volume
docker volume ls
docker volume rm mon_volume
docker volume inspect mon_volume
```

---

### 🚀 Utilisation d’un volume dans un conteneur

#### Monter un volume Docker

```bash
docker run -it --rm -v mon_volume:/test ubuntu
```

#### Monter un dossier local (Bind Mount)

```bash
docker run -it --rm -v C:\Users\HP\Desktop\test:/test-container ubuntu
```

---

## 🔄 Exemple pratique (Bind Mount)

1. Création d’un fichier local `index.html`
2. Montage du dossier local dans le conteneur
3. Modification du fichier depuis le conteneur
4. Le fichier est automatiquement modifié sur la machine hôte

👉 Cela prouve que le **partage de fichiers fonctionne dans les deux sens**.

---

## ✅ Avantages des volumes

* Persistance des données
* Séparation données / conteneur
* Facilite le développement et les tests

---

## ⚠️ Erreurs rencontrées et corrigées

* Mauvais nom d’image (`unbuntu` ❌ → `ubuntu` ✅)
* Confusion entre `volume` et `bind mount`
* Suppression de volume par ID incomplet

---

## 📌 Conclusion

Les volumes sont **essentiels** pour travailler efficacement avec Docker. Les **bind mounts** sont idéaux pour le développement, tandis que les **volumes Docker** sont préférables en production.

---

## 🔗 Ressources utiles

* Documentation officielle Docker
* GitHub Open Source Projects

---

✍️ *Document rédigé par Ayoub – Apprentissage Docker*
