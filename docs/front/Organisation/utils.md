---
sidebar_position: 9
---

# Utils

Dans le projet **TakeCareAI**, les fonctions utilitaires sont centralisées dans le dossier `src/utils`. Ces fonctions encapsulent des logiques communes ou complexes qui peuvent être réutilisées dans différentes parties de l'application, comme le traitement de données ou la manipulation de formats spécifiques.

## Structure des Dossiers

Les fonctions utilitaires sont organisées dans le dossier `src/utils`, chaque fichier étant dédié à une fonctionnalité particulière.

```plaintext
src
└── utils
    ├── parseMarkdown.ts  // Fonction pour analyser et formater du contenu Markdown
    └── [autres fichiers de fonctions utilitaires]
```

### Exemple de Fichier : parseMarkdown.ts

Le fichier parseMarkdown.ts contient une fonction dédiée au traitement de contenu Markdown. Cette fonction est utilisée, par exemple, dans la partie chatbot de l’application pour afficher des réponses formatées avec des styles Markdown (gras, italique, listes, etc.).

## Fonctionnement et Utilisation

Les fonctions utilitaires sont conçues pour être simples à utiliser et faciles à intégrer. Par exemple, parseMarkdown peut être appelée directement avec une chaîne de caractères Markdown pour générer un rendu lisible dans l’application.

### Exemple d’Utilisation

Voici un exemple d’utilisation de la fonction parseMarkdown dans un composant React Native :

```tsx
// src/components/ChatMessage.tsx
import React from "react";
import { Text } from "react-native";
import { parseMarkdown } from "../utils/parseMarkdown";

const ChatMessage = ({ message }) => {
  const formattedMessage = parseMarkdown(message);

  return <Text>{formattedMessage}</Text>;
};

export default ChatMessage;
```

## Objectifs et Avantages

    1.	Réutilisabilité : Les fonctions utilitaires peuvent être appelées depuis n’importe quelle partie de l’application, évitant ainsi la duplication de code.
    2.	Lisibilité du code : En isolant les logiques complexes dans des fonctions utilitaires, le code des composants devient plus simple et facile à lire.
    3.	Centralisation : Toutes les logiques communes sont regroupées, facilitant leur gestion et leur modification.
    4.	Facilité de test : Les fonctions utilitaires peuvent être testées indépendamment, garantissant leur fiabilité.

## Ajouter une Nouvelle Fonction Utilitaire

Pour ajouter une nouvelle fonction utilitaire dans l’application :

1. Créez un fichier sous src/utils/[nom-de-la-fonction].ts.
2. Définissez la logique principale de la fonction.
3. Exportez la fonction pour qu’elle puisse être utilisée dans toute l’application.
4. Ajoutez des tests unitaires pour valider son comportement.

### Exemple : Ajouter une Fonction formatDate

    1.	Créez le fichier src/utils/formatDate.ts.
    2.	Définissez une fonction qui formate une date en chaîne de caractères lisible.
    3.	Exportez la fonction pour l’utiliser dans les composants d’affichage de dates.

```tsx
export const formatDate = (date: Date): string => {
  return date.toLocaleDateString("fr-FR", {
    weekday: "long",
    year: "numeric",
    month: "long",
    day: "numeric",
  });
};
```

### Exemple d’Utilisation de formatDate

```tsx
// src/components/DateDisplay.tsx
import React from "react";
import { Text } from "react-native";
import { formatDate } from "../utils/formatDate";

const DateDisplay = ({ date }) => {
  return <Text>{formatDate(date)}</Text>;
};

export default DateDisplay;
```

## Conclusion

En centralisant les fonctions utilitaires dans un dossier dédié, le projet TakeCareAI bénéficie d’une organisation claire et maintenable. Ces fonctions améliorent la réutilisabilité du code, simplifient les logiques complexes et garantissent une meilleure lisibilité du projet.
