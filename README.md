<p align="center"><img src="./app/assets/images/HorizonLogo.png" width="150px" height="150px" alt="Horizon RP"></p>

<h1 align="center">Horizon Launcher</h1>

<p align="center">Le launcher officiel du serveur Minecraft roleplay <strong>Horizon RP</strong>.</p>

<p align="center">
    <a href="https://github.com/HorizonStudioFR/HorizonLauncher/releases/latest">
        <img src="https://img.shields.io/github/v/release/HorizonStudioFR/HorizonLauncher?style=for-the-badge&label=T%C3%A9l%C3%A9charger" alt="Télécharger">
    </a>
    <a href="https://discord.gg/invite/wFavYrCyKj">
        <img src="https://img.shields.io/badge/Discord-Horizon%20RP-7289da.svg?style=for-the-badge&logo=discord" alt="Discord">
    </a>
</p>

---

Rejoignez Horizon RP sans rien installer à la main : le launcher s'occupe de Java, de Forge, des mods et de leurs mises à jour.

## Installer

Téléchargez l'installeur de votre système dans la **[dernière release](https://github.com/HorizonStudioFR/HorizonLauncher/releases/latest)** :

| Système | Fichier |
|---|---|
| Windows | `Horizon-Launcher-setup-<version>.exe` |
| macOS (Apple Silicon) | `Horizon-Launcher-setup-<version>-arm64.dmg` |
| macOS (Intel) | `Horizon-Launcher-setup-<version>-x64.dmg` |
| Linux | `.AppImage` ou `.deb` |

Lancez-le, connectez-vous avec votre compte Microsoft, puis cliquez sur **Jouer**. Le premier lancement télécharge le jeu et ses mods ; les suivants ne récupèrent que ce qui a changé. Le launcher se met ensuite à jour tout seul.

## Fonctionnalités

* 🔒 **Comptes** : plusieurs comptes Microsoft (OAuth 2.0) ; les identifiants ne sont jamais stockés et vont directement aux serveurs officiels.
* 📂 **Fichiers vérifiés** : chaque fichier est contrôlé avant le lancement ; un fichier corrompu ou manquant est retéléchargé.
* ☕ **Java automatique** : la bonne version de Java est installée pour vous si besoin.
* ⚙️ **Réglages** : mémoire allouée et options JVM.
* 🚀 **Mises à jour automatiques** du launcher et du contenu du serveur.

## Développement

**Prérequis** : [Node.js](https://nodejs.org/) 22.

```console
git clone https://github.com/HorizonStudioFR/HorizonLauncher.git
cd HorizonLauncher
npm install
npm start          # lance l'application en mode développement
```

Compiler les installeurs :

| Plateforme | Commande |
|---|---|
| Plateforme actuelle | `npm run dist` |
| Windows x64 | `npm run dist:win` |
| macOS | `npm run dist:mac` |
| Linux x64 | `npm run dist:linux` |

**Publier une version** : mettre à jour `version` dans `package.json`, puis pousser un tag `vX.Y.Z` ; la CI (`.github/workflows/build.yml`) construit les installeurs Windows, macOS et Linux et les joint à la release, avec les fichiers de mise à jour automatique (`latest*.yml`).

Le contenu du serveur (mods, configurations) est décrit par un index `distribution.json` dont l'adresse est définie dans `app/assets/js/distromanager.js` (`REMOTE_DISTRO_URL`).

## Crédits

Fork de [Helios Launcher](https://github.com/dscalzi/HeliosLauncher) de Daniel Scalzi, sous licence MIT. Merci à lui pour cette base remarquable.

## Communauté

Aide, annonces et vie du serveur : **[Discord Horizon RP](https://discord.gg/invite/wFavYrCyKj)**.
