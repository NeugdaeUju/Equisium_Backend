# Equisium — Backend

API backend du gestionnaire d'élevage de chevaux pour le jeu Equideow. Permet de suivre la progression d'un cheval de sa naissance jusqu'au BLUP 100, en vue de la reproduction.

Application privée, à usage personnel et partagée à un cercle restreint.

## Stack

- Node.js / Express 5
- TypeScript
- MongoDB (via Mongoose) — hébergé sur MongoDB Atlas
- Authentification par JWT

## Prérequis

- Node.js 20+
- Un cluster MongoDB Atlas avec une base de données `equisium`

## Installation

```bash
git clone https://github.com/NeugdaeUju/Equisium_Backend.git
cd Equisium_Backend
npm install
```

## Configuration

Copier `.env.example` en `.env` et renseigner les valeurs réelles :

```bash
cp .env.example .env
```

Variables requises :

| Variable | Description |
|---|---|
| `PORT` | Port d'écoute du serveur (3000 par défaut) |
| `MONGODB_URL` | URI de connexion à la base MongoDB Atlas `equisium` |
| `JWT_SECRET` | Secret de signature des tokens JWT (générer une valeur aléatoire forte) |
| `CORS_ORIGIN` | URL autorisée à appeler l'API (URL du frontend) |

## Lancer le projet

```bash
# Mode développement (hot reload)
npm run dev

# Build de production
npm run build
npm start
```

## Structure du projet

```
src/
├── app.ts              # Configuration Express, middlewares, montage des routes
├── server.ts            # Point d'entrée, démarrage du serveur HTTP
├── controllers/         # Logique métier par ressource
├── routes/               # Définition des endpoints par ressource
├── models/               # Schémas Mongoose
├── middleware/          # Middlewares (authentification, etc.)
└── type/                  # Déclarations de types partagées
```

## État actuel

- [x] Authentification (signup / login) avec JWT
- [ ] Gestion des chevaux (CRUD)
- [ ] Gestion des races et compétences associées
- [ ] Calcul de progression BLUP
- [ ] Gestion des spécialisations (Classique / Western)

## Licence

Projet privé — usage personnel.