# Earth Defender - TypeScript Edition

<p align="center">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/HTML5-Canvas-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5 Canvas">
  <img src="https://img.shields.io/badge/Apache-HTTPD-D22128?style=for-the-badge&logo=apache&logoColor=white" alt="Apache HTTPD">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
</p>

Jeu d'arcade spatial en TypeScript dans lequel le joueur protège la Terre contre des aliens.

## Fonctionnalités vérifiées

Le moteur du jeu gère :

- un canvas de 900 x 600 pixels ;
- un joueur contrôlé au clavier ;
- la Terre avec des points de vie ;
- des aliens générés progressivement ;
- des lasers ;
- les collisions entre objets ;
- un compteur d'aliens éliminés ;
- une augmentation progressive de la cadence d'apparition ;
- un fond étoilé ;
- un écran de fin via rechargement de la partie lorsque le jeu se termine.

## Contrôles

D'après `Input.ts` :

| Touche | Action |
|---|---|
| `Q` | déplacement vers la gauche |
| `D` | déplacement vers la droite |
| `Espace` | tir |

## Architecture TypeScript

```text
src/
├── Classes/
│   ├── Assets.ts
│   ├── Game.ts
│   ├── Input.ts
│   ├── Position.ts
│   └── GameObject/
│       ├── Alien.ts
│       ├── Earth.ts
│       ├── GameObject.ts
│       ├── Laser.ts
│       ├── Player.ts
│       └── Star.ts
└── Script.ts

build/
public/images/
index.html
tsconfig.json
Dockerfile
```

Les sources TypeScript sont compilées depuis `src/` vers `build/` avec des modules ESNext.

## Compilation locale

Prérequis : TypeScript installé sur la machine.

```bash
git clone https://github.com/loic31000/Earth-Defender-Project.git
cd Earth-Defender-Project
tsc
```

La page `index.html` charge ensuite `build/Script.js`.

Vous pouvez servir le dossier avec un serveur HTTP local ou une extension comme Live Server.

## Docker

Le `Dockerfile` utilise `httpd:2.4-alpine` et sert directement les fichiers du dépôt.

```bash
docker build -t earth-defender .
docker run --rm -p 1212:80 --name earth-defender earth-defender
```

Ouvrez ensuite `http://localhost:1212`.

## État du projet

Les fichiers JavaScript compilés sont déjà présents dans `build/`. Le dépôt ne contient actuellement ni tests automatisés ni fichier de licence.
