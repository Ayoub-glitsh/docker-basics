<p align="center">
  <img src="images/docker.png" alt="Docker" width="300">
</p>

---

# 🐳 Apprentissage Docker – Mapping des Ports (Port Mapping)

## 📌 Objectif

Comprendre comment exposer un service qui tourne dans un conteneur Docker vers la machine hôte à l’aide du **mapping des ports**.

---

## 🔍 Concepts clés appris

* Un conteneur Docker a ses **propres ports internes**
* Par défaut, ces ports ne sont **pas accessibles depuis l’hôte**
* L’option `-p` permet de faire le lien entre :

  * **Port de la machine hôte**
  * **Port du conteneur**

---

## 📥 Images utilisées

```bash
docker pull nginx
```

---

## ▶️ Lancer un conteneur sans mapping de port

```bash
docker run --rm nginx
```

### Résultat

* Nginx démarre correctement
* ❌ Impossible d’y accéder depuis le navigateur
* Le port 80 du conteneur **n’est pas exposé**

➡️ Le service fonctionne **uniquement à l’intérieur du conteneur**

---

## 🌐 Mapping d’un port (exposition du service)

```bash
docker run --rm -p 9000:80 nginx
```

### Explication

* `9000` → port de la machine hôte (Windows)
* `80` → port du conteneur (Nginx)
* Format :

```text
-p <port_hôte>:<port_conteneur>
```

---

## ✅ Résultat obtenu

* Nginx est accessible depuis le navigateur
* URL utilisée :

```text
http://localhost:9000
```

* La page par défaut de **Nginx** s’affiche correctement
* Les requêtes HTTP apparaissent dans les logs du conteneur

---

## 🧠 Ce que j’ai compris

* Sans `-p`, un service Docker est **isolé**
* Avec `-p`, le conteneur devient **accessible depuis l’extérieur**
* Plusieurs ports peuvent être mappés si nécessaire
* Le mapping est indispensable pour :

  * Serveurs web
  * APIs
  * Bases de données
  * Applications backend

---

## 📝 Commandes retenues

```bash
# Télécharger une image
docker pull nginx

# Lancer nginx sans exposition de port
docker run --rm nginx

# Lancer nginx avec mapping de port
docker run --rm -p 9000:80 nginx
```

---


