# CodeCampus

Plateforme de cours de programmation en français, conçue pour être hébergée comme site statique et mise en cache pour une utilisation hors connexion.

## Contenu

- `index.html` : interface, cours et atelier intégrés
- `manifest.webmanifest` : métadonnées d'installation PWA
- `service-worker.js` : mise en cache pour le fonctionnement hors ligne après une première visite en ligne
- `assets/icon.svg` : icône de l'application
- `render.yaml` : configuration de déploiement Render Blueprint

## Tester sur son ordinateur

Le double-clic sur `index.html` permet de tester les fonctionnalités de base. Le service worker et l'installation PWA ne fonctionnent toutefois que depuis un contexte sécurisé (`https://`) ou un serveur local.

## Publier sur GitHub

1. Crée un nouveau dépôt GitHub, par exemple `codec-campus`.
2. Décompresse ce dossier sur ton ordinateur.
3. Envoie tous les fichiers et le dossier `assets` à la racine du dépôt (pas le ZIP lui-même).
4. Valide le commit sur la branche principale.

## Déployer sur Render

1. Crée un compte sur Render et relie-le à GitHub.
2. Choisis **New + → Blueprint** et sélectionne le dépôt contenant `render.yaml`, ou crée un **Static Site**.
3. Pour un Static Site, utilise la racine du dépôt comme répertoire publié (`.`) et aucune commande de build.
4. Lance le déploiement puis ouvre l'URL HTTPS fournie par Render.
5. Ouvre le site une première fois avec une connexion Internet. Le service worker met en cache l'application pour les visites hors ligne suivantes.

## Limites actuelles

- L'atelier HTML/CSS/JavaScript utilise le navigateur.
- La simulation Python ne remplace pas un interpréteur Python complet.
- La partie SQL explique certaines requêtes mais n'intègre pas encore de moteur SQL local.
- La progression est stockée dans `localStorage` sur l'appareil et le navigateur courant ; elle n'est pas synchronisée entre appareils.
- Pour mettre à jour le cache après une modification, le service worker utilise le nom de cache `codec-campus-v1`. Incrémente ce nom dans `service-worker.js` si tu souhaites forcer un renouvellement du cache.
