---
sidebar_position: 7
---

# Hooks

Dans le projet **TakeCareAI**, les **hooks personnalisés** de React sont utilisés pour encapsuler des logiques réutilisables, comme l'affichage de notifications ou la gestion des données. Cette approche améliore la lisibilité du code et permet de centraliser des fonctionnalités communes.

## Structure des Dossiers

Les hooks personnalisés sont organisés dans le dossier `src/hooks`. Chaque hook est défini dans un fichier séparé et gère une fonctionnalité spécifique.

```plaintext
src
└── hooks
    ├── useToast.tsx  // Hook pour afficher des notifications
    └── [autres fichiers de hooks personnalisés]
```

### Exemple de Fichier : useToast.tsx

Le fichier useToast.tsx encapsule la logique liée à l’affichage de notifications, permettant de déclencher des messages contextuels à partir de n’importe quel composant.

## Fonctionnement et Utilisation

Un hook personnalisé est une fonction JavaScript ou TypeScript qui utilise les hooks natifs de React pour encapsuler des comportements réutilisables. Par exemple, le hook useToast peut s’appuyer sur des bibliothèques tierces ou sur des solutions maison pour afficher des notifications.

### Exemple d’Utilisation

Voici comment utiliser le hook useToast dans un composant React Native :

```tsx
// src/views/ExempleComponent/index.tsx
import React from "react";
import { Button } from "react-native";
import { useToast } from "../hooks/useToast";

const ExampleComponent = () => {
  const toast = useToast();

  const handlePress = () => {
    toast({
      type: "success",
      title: "Success",
      message: "Action réussie !",
    });
  };

  return <Button title="Afficher une notification" onPress={handlePress} />;
};

export default ExampleComponent;
```

## Contenu Typique d’un Hook

Un hook comme useToast peut inclure :

    - Une fonction principale pour afficher des notifications.
    - Des options personnalisables comme la durée ou le type de notification (succès, erreur, etc.).
    - Des intégrations tierces avec des bibliothèques comme react-native-toast-message.

## Objectifs et Avantages

    1.	Réutilisabilité : Les hooks personnalisés encapsulent des logiques communes qui peuvent être réutilisées dans différents composants.
    2.	Lisibilité du code : En isolant la logique complexe dans des hooks, les composants deviennent plus faciles à lire et à maintenir.
    3.	Centralisation de la logique : Les hooks permettent de centraliser des comportements comme l’affichage de notifications ou la gestion des états locaux.
    4.	Flexibilité : Les hooks peuvent être configurés pour accepter des paramètres dynamiques, les rendant adaptés à différents cas d’utilisation.

## Ajouter un Nouveau Hook

Pour ajouter un nouveau hook dans l’application :

    1. Créez un fichier sous src/hooks/[nom-du-hook].tsx.
    2. Définissez la logique principale du hook.
    3. Exportez le hook pour qu’il soit utilisable dans toute l’application.

## Conclusion

L’utilisation de hooks personnalisés dans le projet TakeCareAI garantit une meilleure organisation du code et encourage la réutilisation de logiques communes. Cette approche permet de développer des fonctionnalités rapidement tout en maintenant une structure propre et maintenable.
