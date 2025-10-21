# API REST Express avec TypeScript

Ce projet est une API REST simple développée avec Express.js et TypeScript, permettant la gestion des utilisateurs avec un stockage en mémoire.

## 🚀 Fonctionnalités

- Architecture MVC (Model-View-Controller)
- Gestion des utilisateurs (ajout et liste)
- Validation des données
- Stockage en mémoire
- TypeScript pour un typage fort
- Variables d'environnement avec dotenv

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

3. Configurez les variables d'environnement :
```bash
cp .env.example .env
# Modifiez le fichier .env selon vos besoins
```

4. Lancez le serveur de développement :
```bash
npm run dev
```

Le serveur démarre par défaut sur http://localhost:3000

## 📌 Points d'accès (Endpoints)

### GET /users
- Description : Récupère la liste de tous les utilisateurs
- Réponse : Liste des utilisateurs au format JSON

Test avec curl :
```bash
curl http://localhost:3000/users
```

Réponse attendue :
```json
{
  "users": []
}
```

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

Test avec curl :
```bash
curl -X POST http://localhost:3000/users \
  -H "Content-Type: application/json" \
  -d '{"name": "John Doe", "email": "john@example.com"}'
```

Réponse attendue :
```json
{
  "message": "Utilisateur John Doe ajouté avec succès !",
  "email": "john@example.com"
}
```

## 🔧 Structure du Projet

```
.
├── .env              # Variables d'environnement
├── nodemon.json      # Configuration de nodemon
├── package.json      # Dépendances et scripts
├── tsconfig.json     # Configuration TypeScript
└── src/
    ├── index.ts      # Point d'entrée
    ├── controllers/  # Logique métier
    │   └── user.controller.ts
    └── routes/      # Définition des routes
        └── user.routes.ts
```

## 🛠️ Technologies Utilisées

- Express.js - Framework web
- TypeScript - Superset JavaScript typé
- Nodemon - Rechargement automatique
- ts-node - Exécution de TypeScript
- dotenv - Gestion des variables d'environnement

## 📝 Scripts Disponibles

- `npm run dev` : Lance le serveur en mode développement
- `npm start` : Lance le serveur en mode production
- `npm run build` : Compile le code TypeScript

## ✅ Tests et Validation

Pour tester l'API complètement, exécutez la séquence suivante :

1. Vérifiez que le serveur est en marche :
```bash
curl http://localhost:3000
```

2. Récupérez la liste des utilisateurs (vide au début) :
```bash
curl http://localhost:3000/users
```

3. Ajoutez un utilisateur :
```bash
curl -X POST http://localhost:3000/users \
  -H "Content-Type: application/json" \
  -d '{"name": "John Doe", "email": "john@example.com"}'
```

4. Vérifiez que l'utilisateur a été ajouté :
```bash
curl http://localhost:3000/users
```

5. Testez la validation des données (devrait échouer) :
```bash
curl -X POST http://localhost:3000/users \
  -H "Content-Type: application/json" \
  -d '{"name": "John Doe"}'
```
