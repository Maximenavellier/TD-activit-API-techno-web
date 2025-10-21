# TD-activit-API-techno-web

Ce projet est une API REST simple développée avec Express.js et TypeScript, permettant la gestion des utilisateurs avec un stockage en mémoire.

## 🚀 Fonctionnalités

- Architecture MVC (Model-View-Controller)
- Gestion des utilisateurs (ajout et liste)
- Validation des données
- Stockage en mémoire
- TypeScript pour un typage fort

## 📋 Prérequis

- Node.js (version 14 ou supérieure)
- npm (gestionnaire de paquets Node.js)

## 🛠️ Installation

1. Clonez le repository :
```bash
git clone [URL_DU_REPO]
cd td6
```

2. Installez les dépendances :
```bash
npm install
```

3. Lancez le serveur de développement :
```bash
npm run dev
```

Le serveur démarre par défaut sur http://localhost:3000

## 📌 Points d'accès (Endpoints)

### GET /users
- Description : Récupère la liste de tous les utilisateurs
- Réponse : Liste des utilisateurs au format JSON

### POST /users
- Description : Ajoute un nouvel utilisateur
- Corps de la requête :
  ```json
  {
    "name": "string",
    "email": "string"
  }
  ```
- Réponse : Message de confirmation avec l'email de l'utilisateur

## 🔧 Structure du Projet

```
.
├── nodemon.json         # Configuration de nodemon pour le rechargement automatique
├── package.json        # Dépendances et scripts npm
├── tsconfig.json      # Configuration TypeScript
└── src/
    ├── index.ts       # Point d'entrée de l'application
    ├── controllers/   # Logique métier
    │   └── user.controller.ts
    └── routes/       # Définition des routes
        └── user.routes.ts
```

## 🛠️ Technologies Utilisées

- Express.js - Framework web
- TypeScript - Superset JavaScript typé
- Nodemon - Rechargement automatique en développement
- ts-node - Exécution de TypeScript

## 📝 Scripts Disponibles

- `npm run dev` : Lance le serveur en mode développement avec rechargement automatique
- `npm start` : Lance le serveur en mode production
- `npm run build` : Compile le code TypeScript en JavaScript

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à ouvrir une issue ou soumettre une pull request.

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.
