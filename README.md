# 🚀 Earth Defender - TypeScript Edition

![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)

Un jeu de défense spatial orienté Arcade développé entièrement en **TypeScript natif**. Protégez la Terre contre les vagues d'astéroïdes et d'envahisseurs extraterrestres !

---

## 🎮 Fonctionnalités du Jeu

* **Gameplay Arcade :** Système de score, vagues d'ennemis progressives et gestion des points de vie de la Terre.
* **Architecture TypeScript :** Utilisation des classes et du typage strict pour une gestion propre des entités (Joueur, Ennemis, Projectiles).
* **Graphismes & Animations :** Rendu fluide basé sur l'API HTML5 Canvas et gestion des collisions en temps réel.

---

## ⚙️ Installation et Lancement

Le projet étant développé en TypeScript, les fichiers sources (`.ts`) doivent être compilés en JavaScript (`.js`) pour être exécutés par le navigateur.

### Option 1 : Lancement Local (Sans Docker)

Pour lancer le jeu localement, vous devez avoir TypeScript installé globalement sur votre machine.

   Ouvrez votre terminal à la racine du projet et lancez le compilateur en mode surveillance (watch) :
   ```bash
   tsc -w
```

Cette commande va lire votre fichier `tsconfig.json` et compiler automatiquement vos fichiers `.ts` dès que vous effectuez une modification.

2. **Lancer le serveur :**
Utilisez l'extension **Live Server** de VS Code sur votre fichier `index.html` pour lancer et tester le jeu sur votre navigateur.

---

### Option 2 : Lancement Conteneurisé (Avec Docker)

Cette méthode utilise Docker pour installer le compilateur requis, compiler automatiquement le code TypeScript et servir le jeu via un serveur web Apache léger.

1. **Construire l'image Docker du jeu :**

```bash
docker build -t game-project .
```

2. **Créer et lancer le conteneur (sur le port 1212 pour éviter les conflits) :**

```bash
docker run -d -p 1212:80 --name earth-defender game-project
```

3. **Accéder au jeu :**
Ouvrez votre navigateur sur [http://localhost:1212](http://localhost:1212).

---

## 🛠️ Aide-mémoire Docker

* **Arrêter le jeu :** `docker stop earth-defender`
* **Relancer le jeu :** `docker start earth-defender`
* **Forcer la reconstruction (Clean build) :** `
docker rm -f earth-defender && docker build --no-cache -t game-project . && docker run -d -p 1212:80 --name earth-defender game-project`
