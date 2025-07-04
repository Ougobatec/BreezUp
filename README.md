# 🌬️ BreezUp – Réseau social léger & réactif

**BreezUp** est un réseau social minimaliste inspiré de Twitter/X, conçu pour fonctionner efficacement même sur des environnements à faibles ressources. Il permet la publication de messages courts, l'interaction entre utilisateurs et une navigation fluide et rapide.


## 🚀 Objectifs du projet

* Offrir une alternative légère aux réseaux sociaux traditionnels.
* Garantir une excellente expérience utilisateur sur mobile.
* Optimiser l'application pour les environnements contraints (faibles débits, matériels limités).
* Concevoir une architecture modulaire, scalable et facilement déployable.


## 🛠️ Stack technique

### Back-end (Node.js + Express)
* **Node.js**, **Express.js** : API RESTful légère et performante
* **MongoDB** + **Mongoose** : base de données NoSQL flexible
* **JWT (JSON Web Tokens)** : authentification sécurisée
* **Docker** : containerisation pour le développement et la production
* Sécurisation : CORS, gestion fine des erreurs
* **Architecture monolithique modulaire** regroupant les modèles suivants :

  * `User`
  * `Post`
  * `Comment`
  * `Subscription`
  * `Notification`
  * `Message`
  * `Report`

### Front-end (React + Next.js)
* **React.js**, **Next.js** : rendu rapide, SSR & SSG
* **Tailwind CSS** : design rapide et responsive
* **Axios** : communication fluide avec l'API
* **React Router / Next Router** : navigation fluide
* Mobile-first et responsive par défaut


## 🔐 Gestion des sessions
* Authentification via JWT
* Stockage sécurisé des tokens (HTTP-only)
* Redirection automatique selon l’état de session


## 📦 Fonctionnalités principales (MVP)

| ID   | Fonctionnalité               | Description                       |
| ---- | ---------------------------- | --------------------------------- |
| Fx1  | Création de compte           | Inscription avec validation       |
| Fx2  | Authentification sécurisée   | Connexion via JWT                 |
| Fx3  | Publication de messages      | Messages limités à 280 caractères |
| Fx4  | Affichage des messages       | Sur le profil utilisateur         |
| Fx5  | Fil d’actualités             | Messages des utilisateurs suivis  |
| Fx6  | Like de post                 | Interaction simple                |
| Fx7  | Commentaires                 | Réponses aux posts                |
| Fx8  | Réponses à commentaires      | Discussions en thread             |
| Fx9  | Suivi d’utilisateurs         | Système de followers              |
| Fx10 | Page de profil               | Nom, bio, photo                   |
| Fx11 | Liste des messages du profil | Historique personnel              |


## 💡 Fonctionnalités secondaires (facultatives)

* Tags & recherche par tags
* Ajout d’images/vidéos
* Notifications (mentions, likes, abonnements)
* Messagerie privée
* Signalement de contenus
* Modération (suspensions/bannissements)
* Interface multi-langue
* Thèmes personnalisés


## 📐 Architecture

BreezUp est basé sur une **architecture monolithique modulaire**, avec un **unique backend Express** regroupant tous les modèles et fonctionnalités de l'application.

* **Frontend (Next.js)** : interface utilisateur, rendu SSR
* **Backend (Express.js)** : API REST centralisée avec tous les modèles métier
* **MongoDB** : base de données partagée
* Communication via **Axios** (client) → **API REST**


## 🧑‍🎨 Interfaces & UX

* Design mobile-first
* Interfaces claires, intuitives
* Feedback utilisateur rapide


## 🗓️ Méthodologie de travail

* Répartition des tâches par fonctionnalité
* Versioning via Git
* Tests manuels et unitaires


## 📦 Lancer le projet

### Pré-requis

Chaque service nécessite un fichier `.env` **et** `.env.production` à la racine :

* Dans `breezup-backend` et `breezup-frontend`, **copier** le fichier `.env.template` en `.env` (et `.env.production` si besoin) puis **remplir les variables** selon votre configuration.
* Adapter le fichier `nginx.conf` si vous utilisez NGINX pour le déploiement, en fonction des ports/services utilisés.


### Choisir le mode de lancement :

#### ▶️ En local (développement sans Docker) :

```bash
cd breezup-backend
npm run dev

cd ../breezup-frontend
npm run dev
```

#### 🐳 Avec Docker (déploiement local conteneurisé) :

```bash
docker-compose up --build -d
```

La base de données MongoDB sera accessible via Docker sur le port `27017` ou en local sur le port `27019` (voir `docker-compose.yml`).


## 👥 Équipe projet

* [Axel CALENDREAU](https://github.com/calaxo)
* [Hugo BATTAGLIA](https://github.com/Ougobatec)
* [Maxime LIRIO](https://github.com/MaximeLIRIO)
* [Oskar MASTALERZ](https://github.com/M-Oskar-dev)