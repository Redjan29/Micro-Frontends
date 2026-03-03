# CP5 — Le Catalogue

## Objectif

Créer le micro-frontend `mfe-catalog` et l’intégrer dans le `shell` avec Module Federation.

## Démarrage rapide

Lancer les 4 applications dans 4 terminaux séparés :

```bash
# T1 (3003)
cd mfe-catalog
npm install
npm start

# T2 (3001)
cd mfe-header
npm install
npm start

# T3 (3002)
cd mfe-lobby
npm install
npm start

# T4 (3000)
cd shell
npm install
npm start
```

## Mission

1. `mfe-catalog/webpack.config.js`
	- Configurer Module Federation (`name`, `filename`, `exposes`, `shared`)
2. `mfe-catalog/src/components/Catalog.jsx`
	- Émettre l’événement `cart:add` via `eventBus` lors d’un ajout au panier
3. `shell/webpack.config.js`
	- Déclarer `mfe-catalog` en remote (`http://localhost:3003/remoteEntry.js`)
4. `shell/src/App.jsx`
	- Importer et afficher `Catalog`

## Critères de validation

- `http://localhost:3000` affiche 6 produits dans la boutique
- Au clic sur “Ajouter”, la console affiche :
  - `[EventBus] cart:add { id, name, price }`

## Livraison

- Commit sur la branche du checkpoint
- Push sur le remote
