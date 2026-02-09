<p align="center"><img src="./app/assets/images/HorizonLogo.png" width="150px" height="150px" alt="Horizon RP"></p>

<h1 align="center">Horizon Launcher</h1>

<p align="center">Le launcher officiel pour le serveur Minecraft Roleplay <strong>Horizon RP</strong>.</p>

<p align="center">
    <a href="https://discord.gg/invite/wFavYrCyKj">
        <img src="https://img.shields.io/badge/Discord-Horizon%20RP-7289da.svg?style=for-the-badge&logo=discord" alt="Discord">
    </a>
</p>

---

Horizon Launcher est conçu pour offrir une expérience simplifiée aux joueurs d'Horizon RP. Rejoignez notre serveur sans vous soucier de l'installation de Java, de Forge ou des mods : nous nous occupons de tout pour vous.

## Fonctionnalités

* 🔒 **Gestion complète des comptes.**
  * Ajoutez plusieurs comptes et passez de l'un à l'autre facilement.
  * Support complet de l'authentification Microsoft (OAuth 2.0).
  * Les identifiants ne sont jamais stockés et sont transmis directement aux serveurs officiels.
* 📂 **Gestion efficace des ressources.**
  * Recevez les mises à jour du client dès qu'elles sont publiées.
  * Les fichiers sont validés avant chaque lancement. Les fichiers corrompus ou manquants sont retéléchargés automatiquement.
* ☕ **Validation automatique de Java.**
  * Si votre version de Java est incompatible, le launcher installe la bonne version *pour vous*.
  * Vous n'avez pas besoin d'avoir Java installé au préalable pour utiliser le launcher.
* ⚙️ **Paramètres intuitifs.**
  * Gérez facilement l'allocation de RAM et les options JVM.
* 🚀 **Mises à jour automatiques.**
  * Le launcher se met à jour tout seul pour vous garantir la meilleure expérience.

## Développement

Cette section détaille la configuration d'un environnement de développement de base.

### Prérequis

* [Node.js](https://nodejs.org/en/) v22

### Installation

```console
> git clone https://github.com/Ylizioops/HorizonLauncher.git
> cd HorizonLauncher
> npm install
```

### Lancer l'application

```console
> npm start
```

### Compiler les installeurs

Pour votre plateforme actuelle :

```console
> npm run dist
```

Pour une plateforme spécifique :

| Plateforme  | Commande             |
| ----------- | -------------------- |
| Windows x64 | `npm run dist:win`   |
| macOS       | `npm run dist:mac`   |
| Linux x64   | `npm run dist:linux` |

---

## Crédits & Remerciements

Ce projet est un fork de [Helios Launcher](https://github.com/dscalzi/HeliosLauncher) développé par Daniel Scalzi. Nous tenons à le remercier pour son travail remarquable sur la base de ce launcher.

## Communauté

Rejoignez-nous sur Discord pour obtenir de l'aide, suivre les annonces et participer à la vie du serveur :

👉 **[Discord Horizon RP](https://discord.gg/invite/wFavYrCyKj)**