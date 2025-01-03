---
sidebar_position: 1
---

# Introduction à TakeCareAI

**TakeCareAI** est une application mobile **React Native** utilisant l'intelligence artificielle pour fournir des diagnostics de santé rapides et précis via un chatbot nommé **AndrewTheDoc**. Elle permet aussi de récupérer et de suivre en temps réel les données de santé des utilisateurs à partir de leurs téléphones et montres connectés.

## Prérequis pour démarrer

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- **Node.js** version 18.0 ou supérieure :
- **React Native** pour développer des applications mobiles multiplateformes (iOS et Android).
- Un IDE comme **Visual Studio Code**, avec des extensions pour **TypeScript** et **React Native**.

### Étape 1 : Cloner le dépôt Git

Récupérez le code source en clonant le dépôt Git de **TakeCareAI** dans le répertoire de votre choix. Exécutez la commande suivante :

```bash
git clone https://github.com/TakeCareOrg/TakeCareAPP.git
cd TakeCareAPP
```

### Étape 2 : Démarrer le serveur Metro

Metro est un bundleur JavaScript utilisé par React Native pour compiler le code. Pour démarrer Metro, exécutez la commande suivante à la racine du projet TakeCareAI :

```bash
# avec npm
npm start

# OU avec Yarn
yarn start
```

### Étape 3 : Lancer l'application

Laissez Metro Bundler fonctionner dans son propre terminal. Ouvrez un nouveau terminal à la racine du projet TakeCareAI et exécutez l'une des commandes suivantes pour lancer l'application sur **Android** ou **iOS**.

#### Pour Android

```bash
# avec npm
npm run android

# OU avec Yarn
yarn android
```

#### Pour iOS

```bash
# avec npm
npm run ios

# OU avec Yarn
yarn ios
```

Si tout est correctement configuré, l'application TakeCareAI devrait s'exécuter dans l'émulateur Android ou le simulateur iOS.

### Étape 4 : Modifier l'application

Maintenant que l'application fonctionne, vous pouvez la personnaliser en modifiant les fichiers source.

1. Ouvrez `App.tsx` dans votre éditeur de texte préféré et faites des modifications.
2. **Pour Android** : Appuyez deux fois sur la touche <kbd>R</kbd> ou sélectionnez **"Reload"** dans le **Developer Menu** (<kbd>Ctrl</kbd> + <kbd>M</kbd> sous Windows et Linux, ou <kbd>Cmd ⌘</kbd> + <kbd>M</kbd> sous macOS) pour voir vos modifications !

   **Pour iOS** : Appuyez sur <kbd>Cmd ⌘</kbd> + <kbd>R</kbd> dans le simulateur iOS pour recharger l'application et voir vos modifications.

## Félicitations ! 🎉

Vous avez réussi à exécuter et modifier l'application TakeCareAI. 🎈

### Ressources utiles

Pour en savoir plus sur React Native et approfondir votre apprentissage :

- [Site officiel de React Native](https://reactnative.dev) - pour en savoir davantage sur React Native.
- [Premiers pas avec React Native](https://reactnative.dev/docs/environment-setup) - vue d'ensemble de React Native et de la configuration de votre environnement.
- [Apprendre les bases](https://reactnative.dev/docs/getting-started) - une introduction guidée aux bases de React Native.

---

Ce guide vous aidera à configurer et démarrer le développement sur **TakeCareAI**, pour offrir des diagnostics de santé modernes grâce à l'IA.
